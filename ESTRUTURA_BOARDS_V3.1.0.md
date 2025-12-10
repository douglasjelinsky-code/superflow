# 🏗️ Estrutura de Boards - V3.1.0

## 📊 Arquitetura do Sistema

O sistema agora trabalha com **DOIS TIPOS** de boards simultaneamente:

```
┌─────────────────────────────────────────────┐
│         SISTEMA DE BOARDS V3.1.0            │
├─────────────────────────────────────────────┤
│                                             │
│  🏢 BOARDS COMPARTILHADOS                   │
│  ├── São Paulo (is_private: false)         │
│  ├── Rio de Janeiro (is_private: false)    │
│  └── Belo Horizonte (is_private: false)    │
│                                             │
│  🔒 BOARDS PRIVADOS                         │
│  ├── TAREFAS - Usuário 1 (user_id: 001)   │
│  ├── TAREFAS - Usuário 2 (user_id: 002)   │
│  └── TAREFAS - Usuário 3 (user_id: 003)   │
│                                             │
└─────────────────────────────────────────────┘
```

---

## 🏢 Board Compartilhado (Cidade)

### Estrutura de Dados
```javascript
{
  id: 'board-saopaulo-001',
  name: 'São Paulo',
  description: 'Gestão de vigilantes de São Paulo',
  color: '#10b981',              // Verde padrão
  is_private: false,             // ← COMPARTILHADO
  user_id: null,                 // ← SEM DONO ESPECÍFICO
  archived: false
}
```

### Características
- **is_private:** `false` ou `undefined`
- **user_id:** `null` ou `undefined`
- **Visibilidade:** Todos os usuários
- **Ícone:** 🏢
- **Label:** "(Compartilhado)"

### Filtro (Lógica)
```javascript
// Mostrar se is_private for false ou undefined
if (board.is_private === false || board.is_private === undefined) {
    return true; // TODOS VEEM
}
```

---

## 🔒 Board Privado (TAREFAS)

### Estrutura de Dados
```javascript
{
  id: 'board-tarefas-1733508234567',
  name: 'TAREFAS',
  description: 'Minhas tarefas pessoais',
  color: '#8b5cf6',              // Roxo
  is_private: true,              // ← PRIVADO
  user_id: 'user-123456',        // ← DONO DO BOARD
  archived: false
}
```

### Características
- **is_private:** `true`
- **user_id:** ID do usuário dono
- **Visibilidade:** Apenas o dono
- **Ícone:** 🔒
- **Label:** "(Privado)"

### Filtro (Lógica)
```javascript
// Mostrar apenas se pertencer ao usuário atual
if (board.is_private === true && board.user_id === currentUser.id) {
    return true; // APENAS O DONO VÊ
}
```

---

## 🔄 Fluxo de Criação de Boards

### 1. Board Compartilhado (Cidade)
```javascript
// Administrador cria manualmente
const newBoard = {
  id: generateId(),
  name: 'Curitiba',              // Nome da cidade
  description: 'Vigilantes de Curitiba',
  color: '#10b981',
  is_private: false,             // ← IMPORTANTE
  user_id: null,                 // ← IMPORTANTE
  archived: false
};

await API.createBoard(newBoard);
```

### 2. Board Privado (TAREFAS)
```javascript
// Sistema cria automaticamente no primeiro login
async function createDefaultBoard() {
    const boardId = 'board-tarefas-' + Date.now();
    const defaultBoard = {
        id: boardId,
        name: 'TAREFAS',
        description: 'Minhas tarefas pessoais',
        color: '#8b5cf6',
        is_private: true,          // ← IMPORTANTE
        user_id: currentUser.id,   // ← IMPORTANTE
        archived: false
    };
    await API.createBoard(defaultBoard);
    
    // Criar 3 listas padrão
    await API.createList({...});   // "A Fazer"
    await API.createList({...});   // "Em Andamento"
    await API.createList({...});   // "Concluído"
}
```

---

## 🎯 Lógica de Exibição

### Função loadBoards()
```javascript
async function loadBoards() {
    // 1. Buscar TODOS os boards
    const allBoards = await API.getBoards();
    
    // 2. Filtrar boards visíveis para o usuário atual
    AppState.boards = allBoards.filter(b => {
        // REGRA 1: Boards compartilhados (todos veem)
        if (b.is_private === false || b.is_private === undefined) {
            return true;
        }
        
        // REGRA 2: Boards privados (apenas o dono vê)
        return b.is_private === true && b.user_id === AppState.currentUser.id;
    });
    
    // 3. Verificar se usuário tem board privado
    const hasPrivateBoard = AppState.boards.some(b => 
        b.is_private === true && b.user_id === AppState.currentUser.id
    );
    
    // 4. Criar board TAREFAS se não existir
    if (!hasPrivateBoard) {
        await createDefaultBoard();
        // Recarregar boards
        const newBoards = await API.getBoards();
        AppState.boards = newBoards.filter(/* mesma lógica */);
    }
    
    // 5. Atualizar seletor
    updateBoardSelector();
}
```

### Função updateBoardSelector()
```javascript
function updateBoardSelector() {
    const select = document.getElementById('boardSelect');
    select.innerHTML = AppState.boards.map(board => {
        // Determinar tipo
        const isPrivate = board.is_private === true;
        const icon = isPrivate ? '🔒' : '🏢';
        const label = isPrivate ? 'Privado' : 'Compartilhado';
        
        // Renderizar option
        return `<option value="${board.id}">
            ${icon} ${board.name} (${label})
        </option>`;
    }).join('');
}
```

---

## 📊 Exemplo de Dados no Sistema

### Usuário 1: João (Supervisor)

**Boards visíveis:**
```
[
  {
    id: 'board-saopaulo',
    name: 'São Paulo',
    is_private: false,
    user_id: null
  },
  {
    id: 'board-rio',
    name: 'Rio de Janeiro',
    is_private: false,
    user_id: null
  },
  {
    id: 'board-tarefas-joao',
    name: 'TAREFAS',
    is_private: true,
    user_id: 'user-joao-123'  // ← ID de João
  }
]
```

**Seletor de boards:**
```
🏢 São Paulo (Compartilhado)
🏢 Rio de Janeiro (Compartilhado)
🔒 TAREFAS (Privado)
```

### Usuário 2: Maria (Gerente)

**Boards visíveis:**
```
[
  {
    id: 'board-saopaulo',
    name: 'São Paulo',
    is_private: false,
    user_id: null
  },
  {
    id: 'board-rio',
    name: 'Rio de Janeiro',
    is_private: false,
    user_id: null
  },
  {
    id: 'board-tarefas-maria',
    name: 'TAREFAS',
    is_private: true,
    user_id: 'user-maria-456'  // ← ID de Maria
  }
]
```

**Seletor de boards:**
```
🏢 São Paulo (Compartilhado)
🏢 Rio de Janeiro (Compartilhado)
🔒 TAREFAS (Privado)
```

**IMPORTANTE:** Maria **NÃO VÊ** o board TAREFAS de João!

---

## 🔐 Segurança e Isolamento

### Garantias do Sistema

1. **Isolamento de Dados**
   ```javascript
   // Board privado de João
   { is_private: true, user_id: 'user-joao' }
   
   // Maria NÃO vê porque:
   board.user_id !== currentUser.id
   // 'user-joao' !== 'user-maria'
   ```

2. **Compartilhamento de Cidades**
   ```javascript
   // Board de São Paulo
   { is_private: false, user_id: null }
   
   // TODOS veem porque:
   board.is_private === false
   ```

3. **Validação no Filtro**
   ```javascript
   // Condição para boards privados
   return b.is_private === true && b.user_id === currentUser.id;
   //                               ↑
   //                    GARANTE ISOLAMENTO
   ```

---

## 🎨 Visualização no Seletor

### Aparência Final

```html
<select id="boardSelect">
  <option value="board-saopaulo">🏢 São Paulo (Compartilhado)</option>
  <option value="board-rio">🏢 Rio de Janeiro (Compartilhado)</option>
  <option value="board-tarefas">🔒 TAREFAS (Privado)</option>
</select>
```

### CSS (Opcional - Futura Melhoria)
```css
/* Diferenciar visualmente */
option[data-private="true"] {
    font-style: italic;
    color: #8b5cf6;
}

option[data-private="false"] {
    font-weight: 500;
    color: #10b981;
}
```

---

## 📋 Checklist de Validação

### ✅ Testando Boards Compartilhados

- [ ] Usuário 1 cria vigilante em "São Paulo"
- [ ] Usuário 2 faz login
- [ ] Usuário 2 vê o vigilante criado por Usuário 1
- [ ] Usuário 2 pode editar o vigilante
- [ ] Ambos veem o histórico de alterações

### ✅ Testando Boards Privados

- [ ] Usuário 1 cria tarefa em "TAREFAS"
- [ ] Usuário 2 faz login
- [ ] Usuário 2 NÃO vê a tarefa do Usuário 1
- [ ] Usuário 2 tem seu próprio board "TAREFAS" vazio
- [ ] Cada usuário vê apenas suas próprias tarefas

### ✅ Testando Criação Automática

- [ ] Novo usuário faz primeiro login
- [ ] Board "TAREFAS" é criado automaticamente
- [ ] Board vem com 3 listas: "A Fazer", "Em Andamento", "Concluído"
- [ ] Segundo login NÃO cria duplicado

---

## 🚀 Resumo Técnico

| Aspecto | Board Compartilhado | Board Privado |
|---------|---------------------|---------------|
| **is_private** | `false` | `true` |
| **user_id** | `null` | ID do usuário |
| **Visibilidade** | Todos | Apenas dono |
| **Ícone** | 🏢 | 🔒 |
| **Cor padrão** | Verde #10b981 | Roxo #8b5cf6 |
| **Criação** | Manual (admin) | Automática (sistema) |
| **Uso** | Cidades/Regiões | Tarefas pessoais |

---

**Desenvolvido por:** TaskFlow Team  
**Versão:** 3.1.0  
**Data:** 2025-12-06
