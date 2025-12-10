# 📖 Como Usar os Boards - Guia Prático

## 🎯 Entendendo os Dois Tipos de Boards

Seu sistema agora tem **dois tipos** de boards trabalhando juntos:

### 🏢 Boards de Cidades (Compartilhados)
- **Para quê:** Gerenciar vigilantes da empresa
- **Quem vê:** Todos os usuários da equipe
- **Exemplo:** São Paulo, Rio de Janeiro, Belo Horizonte

### 🔒 Board TAREFAS (Privado)
- **Para quê:** Suas tarefas pessoais
- **Quem vê:** Somente você
- **Exemplo:** TAREFAS (criado automaticamente)

---

## 🚀 Primeiro Acesso

### 1. Criar Sua Conta
```
1. Abra login.html
2. Clique em "Criar conta"
3. Preencha:
   - Nome completo
   - Email
   - Senha
4. Clique em "Criar Conta"
```

### 2. Fazer Login
```
1. Digite seu email
2. Digite sua senha
3. Clique em "Entrar"
```

### 3. O Que Você Verá

**No seletor de boards:**
```
┌─────────────────────────────────────┐
│ 🏢 São Paulo (Compartilhado)    ▼  │
├─────────────────────────────────────┤
│ 🏢 São Paulo (Compartilhado)       │
│ 🏢 Rio de Janeiro (Compartilhado)  │
│ 🔒 TAREFAS (Privado)               │
└─────────────────────────────────────┘
```

---

## 🏢 Usando Boards Compartilhados (Cidades)

### Cenário: Gerenciar Vigilantes de São Paulo

#### Passo 1: Selecionar o Board
```
1. Clique no seletor de boards
2. Escolha "🏢 São Paulo (Compartilhado)"
```

#### Passo 2: Ver as Listas (Equipes)
Você verá listas como:
- TIGRE
- LEÃO
- ÁGUIA
- PANTERA

#### Passo 3: Adicionar um Vigilante
```
1. Clique em "+" dentro de uma lista (ex: TIGRE)
2. Preencha os dados:
   ┌─────────────────────────────────┐
   │ Matrícula: 12345               │
   │ Nome: João Silva               │
   │ Telefone: (11) 98765-4321      │
   │ Função: Vigilante              │
   │ Data Admissão: 2024-01-15      │
   │ Status: Em Serviço             │
   │ Escala: 12x36                  │
   │ Horário: 07:00 às 19:00        │
   └─────────────────────────────────┘
3. Clique em "Salvar"
```

#### Passo 4: Colaboração
- ✅ Outros usuários **VEEM** este vigilante
- ✅ Outros usuários **PODEM EDITAR**
- ✅ Todos veem o **HISTÓRICO** de mudanças

---

## 🔒 Usando Board Privado (TAREFAS)

### Cenário: Organizar Suas Tarefas Pessoais

#### Passo 1: Selecionar o Board TAREFAS
```
1. Clique no seletor de boards
2. Escolha "🔒 TAREFAS (Privado)"
```

#### Passo 2: Ver as Listas Padrão
Você verá 3 listas:
- ✅ A Fazer
- ⏳ Em Andamento
- ✅ Concluído

#### Passo 3: Adicionar uma Tarefa
```
1. Clique em "+" dentro de "A Fazer"
2. Preencha conforme necessário:
   ┌─────────────────────────────────┐
   │ Matrícula: (deixe em branco)   │
   │ Nome: Revisar relatórios       │
   │ Descrição: Revisar relatórios  │
   │              mensais da equipe │
   └─────────────────────────────────┘
3. Clique em "Salvar"
```

**Dica:** Não precisa preencher todos os campos! Use apenas o que faz sentido para suas tarefas.

#### Passo 4: Mover Tarefa Entre Listas
```
1. Arraste a tarefa de "A Fazer"
2. Solte em "Em Andamento"
3. Quando terminar, arraste para "Concluído"
```

#### Passo 5: Privacidade
- 🔒 **Somente VOCÊ** vê suas tarefas
- 🔒 Outros usuários **NÃO VEEM**
- 🔒 Cada usuário tem seu próprio board TAREFAS

---

## 🎨 Identificando os Boards

### No Seletor
```
🏢 = Board compartilhado (todos veem)
🔒 = Board privado (só você)
```

### Exemplos Visuais

#### Board Compartilhado
```
┌────────────────────────────────────┐
│ 🏢 São Paulo (Compartilhado)       │
│                                    │
│ ┌──────────┐ ┌──────────┐        │
│ │  TIGRE   │ │  LEÃO    │        │
│ ├──────────┤ ├──────────┤        │
│ │ • João   │ │ • Maria  │        │ ← Todos veem
│ │ • Pedro  │ │ • Carlos │        │
│ └──────────┘ └──────────┘        │
└────────────────────────────────────┘
```

#### Board Privado
```
┌────────────────────────────────────┐
│ 🔒 TAREFAS (Privado)               │
│                                    │
│ ┌──────────┐ ┌──────────┐        │
│ │ A Fazer  │ │ Fazendo  │        │
│ ├──────────┤ ├──────────┤        │
│ │ • Tarefa1│ │ • Tarefa3│        │ ← Só você vê
│ │ • Tarefa2│ └──────────┘        │
│ └──────────┘                      │
└────────────────────────────────────┘
```

---

## 💡 Casos de Uso Práticos

### Caso 1: João - Supervisor de Operações

**Manhã - 08:00**
1. João faz login
2. Abre board "🏢 São Paulo"
3. Move vigilante "Carlos" de TIGRE para LEÃO
4. ✅ Todos veem a mudança

**Tarde - 14:00**
1. João abre board "🔒 TAREFAS"
2. Adiciona: "Aprovar férias da equipe TIGRE"
3. Move para "Em Andamento"
4. 🔒 Ninguém mais vê esta tarefa

---

### Caso 2: Maria - Gerente Regional

**Manhã - 09:00**
1. Maria faz login
2. Abre board "🏢 Rio de Janeiro"
3. Adiciona novo vigilante "Ana" na equipe ÁGUIA
4. ✅ Toda equipe vê a nova vigilante

**Tarde - 15:00**
1. Maria abre board "🔒 TAREFAS"
2. Vê suas próprias tarefas:
   - Reunião com RH (A Fazer)
   - Revisar relatório (Em Andamento)
3. 🔒 NÃO vê as tarefas de João

---

## 🔄 Fluxo de Trabalho Recomendado

### Gestão de Vigilantes (Boards Compartilhados)

```
┌─────────────────────────────────────────┐
│ 1. Selecionar cidade (ex: São Paulo)   │
│ 2. Verificar equipes/listas             │
│ 3. Adicionar/editar vigilantes          │
│ 4. Mover entre equipes (drag-and-drop)  │
│ 5. Alterar status conforme necessário   │
│ 6. Consultar histórico de mudanças      │
└─────────────────────────────────────────┘
```

### Gestão de Tarefas (Board Privado)

```
┌─────────────────────────────────────────┐
│ 1. Abrir board "🔒 TAREFAS"             │
│ 2. Adicionar tarefas em "A Fazer"       │
│ 3. Iniciar: mover para "Em Andamento"   │
│ 4. Concluir: mover para "Concluído"     │
│ 5. Revisar tarefas concluídas           │
└─────────────────────────────────────────┘
```

---

## ❓ Perguntas Frequentes

### 1. Posso criar mais boards de cidades?
**Sim!** Clique em "➕ Adicionar Board" e deixe como compartilhado.

### 2. Posso ter mais de um board privado?
Atualmente, o sistema cria apenas o board "TAREFAS" automaticamente. Você pode criar mais, mas serão compartilhados.

### 3. Como sei se um board é privado ou compartilhado?
Pelo ícone:
- 🏢 = Compartilhado
- 🔒 = Privado

### 4. Outros usuários podem ver minhas tarefas?
**NÃO!** Seu board TAREFAS é 100% privado.

### 5. Posso deletar o board TAREFAS?
Não é recomendado. Se deletar, o sistema criará novamente no próximo login.

### 6. Como adiciono um usuário à equipe?
Todos os usuários cadastrados veem os boards compartilhados automaticamente.

### 7. Posso mover vigilantes entre boards?
Não diretamente. Use a função "Copiar Card" e depois delete o original.

### 8. O que acontece se eu editar um vigilante em um board compartilhado?
Todos os usuários verão a edição em tempo real após recarregar.

---

## 🎯 Dicas e Boas Práticas

### Para Boards Compartilhados (Cidades)

✅ **FAÇA:**
- Use para gerenciar vigilantes da empresa
- Mantenha dados atualizados
- Consulte o histórico de mudanças
- Comunique grandes alterações à equipe

❌ **NÃO FAÇA:**
- Não use para tarefas pessoais
- Não delete vigilantes sem avisar a equipe

### Para Board Privado (TAREFAS)

✅ **FAÇA:**
- Use para suas tarefas individuais
- Organize por prioridade
- Mova para "Concluído" quando terminar
- Use campos relevantes (não precisa preencher todos)

❌ **NÃO FAÇA:**
- Não adicione informações de vigilantes aqui
- Não use para dados que a equipe precisa ver

---

## 📚 Documentos Relacionados

- 📗 [BOARDS_COMPARTILHADOS_E_PRIVADOS.md](BOARDS_COMPARTILHADOS_E_PRIVADOS.md) - Guia completo
- 📘 [ATUALIZACAO_V3.1.0.md](ATUALIZACAO_V3.1.0.md) - Detalhes técnicos
- 📙 [QUICK_START.md](QUICK_START.md) - Início rápido
- 📕 [README.md](README.md) - Documentação completa

---

## 🎊 Comece Agora!

1. **Abra:** [login.html](login.html)
2. **Crie sua conta**
3. **Explore os boards compartilhados**
4. **Use seu board TAREFAS**
5. **Colabore com sua equipe!**

---

**Versão:** 3.1.0  
**Data:** 2025-12-06  
**Dúvidas?** Consulte a documentação completa!
