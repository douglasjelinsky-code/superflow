# 🏢🔒 Sistema de Boards: Compartilhados e Privados

## 📋 Visão Geral

O sistema agora suporta **DOIS TIPOS** de boards simultaneamente:

1. **🏢 BOARDS COMPARTILHADOS** (Cidades) - Visíveis para todos os usuários
2. **🔒 BOARDS PRIVADOS** (Tarefas) - Exclusivos de cada usuário

---

## 🏢 Boards Compartilhados (Cidades)

### O que são?
São boards acessíveis por **TODOS** os usuários do sistema.

### Para que servem?
- Gerenciar vigilantes por cidade/região
- Compartilhar informações entre equipes
- Colaboração em tempo real
- Escalas de trabalho comuns

### Características
- ✅ **Visibilidade:** Todos os usuários veem
- ✅ **Edição:** Qualquer usuário pode editar
- ✅ **Identificação:** Ícone 🏢 no seletor
- ✅ **Uso:** Gestão de vigilantes por cidade/posto

### Exemplos de Boards Compartilhados
- 🏢 São Paulo
- 🏢 Rio de Janeiro
- 🏢 Belo Horizonte
- 🏢 Brasília

---

## 🔒 Board Privado (TAREFAS)

### O que é?
Um board **EXCLUSIVO** de cada usuário, completamente privado.

### Para que serve?
- Gerenciar suas tarefas pessoais
- Organizar seu trabalho individual
- Lista de afazeres (To-Do List)
- Anotações e lembretes

### Características
- 🔒 **100% Privado:** Somente VOCÊ vê
- 🎁 **Criação Automática:** Aparece no primeiro login
- 📋 **3 Listas Padrão:**
  - ✅ A Fazer
  - ⏳ Em Andamento
  - ✅ Concluído
- 🔒 **Identificação:** Ícone 🔒 no seletor
- 🟣 **Cor Roxa:** #8b5cf6

### Board TAREFAS - Como Funciona?

1. **Primeiro Login**
   - Sistema verifica se você já tem board privado
   - Se não tiver, cria automaticamente o board "TAREFAS"
   - Board vem com 3 listas prontas

2. **Segundo Login em Diante**
   - Sistema detecta que você já tem board privado
   - NÃO cria duplicado
   - Carrega seu board TAREFAS existente

3. **Uso do Board TAREFAS**
   - Adicione cards como tarefas pessoais
   - Mova entre "A Fazer" → "Em Andamento" → "Concluído"
   - Use os campos conforme necessário (sem obrigatoriedade de preencher todos)

---

## 🎯 Como Identificar o Tipo de Board?

### No Seletor de Boards
```
🏢 São Paulo (Compartilhado)
🏢 Rio de Janeiro (Compartilhado)
🔒 TAREFAS (Privado)
```

### Legenda de Ícones
- **🏢** = Board Compartilhado (todos veem)
- **🔒** = Board Privado (só você vê)

---

## 💡 Casos de Uso

### Exemplo de Fluxo de Trabalho

**João - Supervisor Regional**

1. **Login no Sistema**
   - João faz login pela primeira vez
   - Sistema cria automaticamente o board "🔒 TAREFAS (Privado)" para ele

2. **Boards Disponíveis para João:**
   - 🏢 São Paulo (Compartilhado)
   - 🏢 Rio de Janeiro (Compartilhado)
   - 🔒 TAREFAS (Privado)

3. **Uso do Board São Paulo (Compartilhado):**
   - João gerencia vigilantes da cidade de São Paulo
   - Outros supervisores também veem e editam
   - Colaboração em tempo real

4. **Uso do Board TAREFAS (Privado):**
   - João adiciona:
     - "Revisar relatórios mensais" (A Fazer)
     - "Aprovar férias da equipe" (A Fazer)
     - "Reunião com RH" (Em Andamento)
     - "Relatório de abril" (Concluído)
   - NINGUÉM MAIS vê essas tarefas, são exclusivas de João

**Maria - Gerente de Operações**

1. **Login no Sistema**
   - Maria faz login pela primeira vez
   - Sistema cria automaticamente o board "🔒 TAREFAS (Privado)" para ela

2. **Boards Disponíveis para Maria:**
   - 🏢 São Paulo (Compartilhado)
   - 🏢 Rio de Janeiro (Compartilhado)
   - 🔒 TAREFAS (Privado)

3. **Maria NÃO VÊ as tarefas de João**
   - Cada board TAREFAS é 100% independente
   - Maria tem suas próprias tarefas privadas

---

## 🔧 Implementação Técnica

### Estrutura do Board

```javascript
{
  id: 'board-xxx',
  name: 'São Paulo',           // ou 'TAREFAS'
  description: '...',
  color: '#10b981',             // verde para cidades, roxo para TAREFAS
  is_private: false,            // false = compartilhado, true = privado
  user_id: null,                // null = compartilhado, 'user-123' = privado
  archived: false
}
```

### Lógica de Filtragem

```javascript
// Mostrar boards compartilhados + board privado do usuário atual
const visibleBoards = allBoards.filter(board => {
  // Boards compartilhados (todos veem)
  if (board.is_private === false || board.is_private === undefined) {
    return true;
  }
  // Boards privados (apenas o dono vê)
  return board.is_private === true && board.user_id === currentUser.id;
});
```

### Criação do Board TAREFAS

```javascript
// Verificar se usuário já tem board privado
const hasPrivateBoard = boards.some(b => 
  b.is_private === true && b.user_id === currentUser.id
);

// Se não tiver, criar
if (!hasPrivateBoard) {
  await createDefaultBoard(); // Cria board TAREFAS privado
}
```

---

## ❓ Perguntas Frequentes

### 1. Posso criar mais boards privados além do TAREFAS?
Atualmente, o sistema cria automaticamente apenas UM board privado por usuário (TAREFAS). Você pode criar mais boards, mas eles serão compartilhados.

### 2. Como diferenciar cards de vigilantes de cards de tarefas?
- **Board de Cidade:** Cards têm campos como Matrícula, Função, Data de Admissão, Status
- **Board TAREFAS:** Use os campos conforme necessário, sem obrigatoriedade

### 3. Posso excluir o board TAREFAS?
Tecnicamente sim, mas não é recomendado. Se excluir, o sistema criará novamente no próximo login.

### 4. Outros usuários podem ver meu board TAREFAS?
**NÃO.** O board TAREFAS é 100% privado. Ninguém além de você pode visualizar.

### 5. Como criar um board compartilhado (cidade)?
Clique em "➕ Adicionar Board", preencha o nome (ex: "Curitiba") e deixe `is_private` como `false` ou não marque como privado.

### 6. Como mudar a cor do meu board TAREFAS?
Acesse as configurações do board (ícone ⚙️) e altere a cor. Por padrão é roxo (#8b5cf6).

---

## 🎓 Resumo

| Tipo | Ícone | Visibilidade | Exemplo | Criação |
|------|-------|--------------|---------|---------|
| **Compartilhado** | 🏢 | Todos os usuários | São Paulo, Rio | Manual |
| **Privado** | 🔒 | Apenas você | TAREFAS | Automática |

---

## 🚀 Próximos Passos

1. **Crie sua conta** em `login.html`
2. **Explore os boards compartilhados** (cidades)
3. **Use seu board TAREFAS** para organizar seu trabalho
4. **Colabore com a equipe** nos boards compartilhados

---

**Versão:** 3.1.0  
**Data:** 2025-12-06  
**Sistema:** TaskFlow - Gestão de Vigilantes e Tarefas
