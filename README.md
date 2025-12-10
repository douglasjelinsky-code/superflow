# 🛡️ SUPER FLOW - Sistema de Gestão de Vigilantes

Sistema moderno e completo de gerenciamento de vigilantes com controle de escalas, status e histórico de movimentações. Interface elegante com tema verde e fundo escuro, desenvolvido com HTML, CSS e JavaScript vanilla.

![SUPER FLOW](https://img.shields.io/badge/Status-Pronto-brightgreen)
![Version](https://img.shields.io/badge/Versão-3.2.0-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 🆕 **V3.1.0: SISTEMA COMPLETO COM BOARDS COMPARTILHADOS E PRIVADOS**

👋 **[→ COMECE AQUI! RESUMO SUPER RÁPIDO](LEIA_ME_PRIMEIRO.md)**  
⚡ **[INÍCIO RÁPIDO EM 3 MINUTOS](INICIO_RAPIDO_V3.1.0.md)**  
📋 **[IMPLEMENTAÇÃO CONCLUÍDA - DETALHES](IMPLEMENTACAO_CONCLUIDA_V3.1.0.md)**

### 🏢 Boards Compartilhados (Cidades)
- ✅ **Visíveis para todos** - Boards de cidades são compartilhados entre usuários
- 🌍 **Colaboração** - Todos podem visualizar e editar vigilantes das cidades
- 🏢 **Ícone identificador** - Marcados com 🏢 no seletor de boards

### 🔒 Board Privado (Tarefas)
- ✅ **Board TAREFAS pessoal** - Cada usuário tem seu board privado de tarefas
- 🔐 **100% Privado** - Somente você vê suas tarefas
- 🎁 **Criado automaticamente** - Aparece no primeiro login
- 🔒 **Ícone identificador** - Marcado com 🔒 no seletor de boards
- 📋 **3 listas padrão**: "A Fazer", "Em Andamento", "Concluído"

### 👥 Sistema de Usuários
- 🔐 **Login e Registro** - Cada usuário tem sua conta individual
- 🚪 **Logout Seguro** - Sessão protegida com sessionStorage
- 👤 **Experiência personalizada** - Boards compartilhados + board privado pessoal

**Para começar:** Acesse `login.html` e crie sua conta!

---

## ✨ Características Principais

### 🎯 Funcionalidades Implementadas

- ✅ **Gestão Completa de Vigilantes**
  - Cards compactos e otimizados (70px de altura)
  - Matrícula, Nome e Status visíveis imediatamente
  - Sistema de status com 6 categorias coloridas
  - Informações detalhadas: função e data de admissão

- ✅ **Sistema de Status Colorido**
  - 🟢 **Em Serviço** - Verde (#10b981)
  - 🔵 **Livre** - Azul (#3b82f6)
  - 🟡 **Férias** - Laranja (#f59e0b)
  - 🔴 **Afastado** - Vermelho (#ef4444)
  - ⚫ **Demitido** - Cinza (#6b7280)
  - 🟣 **Em Admissão** - Roxo (#8b5cf6)

- ✅ **Histórico Completo de Movimentações**
  - Registro automático de todas as ações
  - Movimentações entre listas
  - Alterações de dados
  - Mudanças de status
  - Filtros por tipo de ação
  - Timeline visual com ícones coloridos

- ✅ **Checklists Personalizados**
  - Criar quantos checklists precisar
  - Nomes personalizados (Treinamentos, Certificações, etc.)
  - Múltiplos itens por checklist
  - Totalmente flexível

- ✅ **Gerenciamento de Boards e Listas**
  - Criar, editar e deletar boards
  - Listas ilimitadas e customizáveis
  - Organização visual em colunas
  - Contador de vigilantes por lista

- ✅ **Drag and Drop**
  - Arrastar vigilantes entre listas
  - Registro automático no histórico
  - Feedback visual durante o arraste
  - Atualização instantânea

- ✅ **Importação e Exportação de Dados**
  - **⭐ Exportar para Excel (.XLSX)** - Planilha profissional com 4 abas
  - **⭐ Importar Excel (.XLSX)** - Suporta datas automáticas e formatação
  - **Modelo Excel (.XLSX)** - Template organizado para preencher
  - **Exportar Histórico (.XLSX)** - Movimentações formatadas
  - **Backup JSON** - Estrutura completa
  - Múltiplas abas: Vigilantes, Resumo, Por Equipe, Instruções
  - Formatação automática de datas (DD/MM/AAAA)
  - Colunas separadas: Treinamentos, Documentos, Equipamentos
  - Feedback em tempo real
  - Validação inteligente

- ✅ **Sistema de Busca Inteligente**
  - Busca em tempo real (300ms debounce)
  - Busca por nome do vigilante
  - Busca por matrícula
  - Busca por nome da lista/posto
  - Busca por CCU e número do posto
  - Destaque visual dos resultados
  - Contador de resultados encontrados
  - Botão para limpar busca

- ✅ **Interface Moderna**
  - Design responsivo (desktop, tablet, mobile)
  - Tema escuro com acentos em verde
  - Animações suaves e transições
  - Notificações toast elegantes

## 🗂️ Estrutura de Dados

### Tabelas do Sistema

#### **boards**
Armazena informações dos boards
- `id` (text) - Identificador único
- `name` (text) - Nome do board
- `description` (text) - Descrição do board
- `color` (text) - Cor do tema (hex)
- `archived` (bool) - Status de arquivamento

#### **lists**
Armazena as listas de cada board
- `id` (text) - Identificador único
- `board_id` (text) - Referência ao board
- `name` (text) - Nome da lista
- `ccu` (text) - Código CCU do posto
- `numero_posto` (text) - Número do posto
- `position` (number) - Ordem de exibição

#### **cards** (Vigilantes)
Armazena os dados dos vigilantes
- `id` (text) - Identificador único
- `list_id` (text) - Referência à lista atual
- `board_id` (text) - Referência ao board
- `matricula` (text) - Matrícula do vigilante
- `nome_vigilante` (text) - Nome completo
- `telefone` (text) - Telefone de contato
- `funcao` (text) - Função/cargo
- `data_admissao` (text) - Data de admissão
- `status` (text) - Status atual (EM_SERVICO, LIVRE, FERIAS, etc)
- `escala` (text) - Escala de trabalho (12x36, 6x1, etc)
- `horario` (text) - Horário de trabalho
- `descricao` (rich_text) - Observações gerais
- `checklists` (array) - Checklists personalizados
- `position` (number) - Ordem na lista
- `archived` (bool) - Status de arquivamento

#### **history** (Histórico)
Registra todas as movimentações e alterações
- `id` (text) - Identificador único do registro
- `card_id` (text) - ID do vigilante relacionado
- `board_id` (text) - ID do board
- `action_type` (text) - Tipo: CRIADO, MOVIDO, EDITADO, STATUS_ALTERADO, DELETADO
- `old_value` (text) - Valor anterior
- `new_value` (text) - Novo valor
- `field_changed` (text) - Campo alterado
- `description` (text) - Descrição da ação
- `timestamp` (datetime) - Data e hora da ação

## 🎨 Layout dos Cards

### Card Compacto (70px de altura)

```
┌──────────────────────────────────────────────────────┐
│ #12345  João Silva Santos        [EM SERVIÇO]       │
│ 🛡️ Vigilante    📅 15/01/2023                       │
└──────────────────────────────────────────────────────┘
```

**Linha 1:** Matrícula + Nome + Status (badge colorido)  
**Linha 2:** Função + Data de Admissão

### Informações Detalhadas (ao clicar)

- ✏️ Matrícula
- 👤 Nome Completo
- 📞 Telefone de Contato
- 🛡️ Função (Vigilante, Supervisor, etc)
- 📅 Data de Admissão
- 🏷️ Status (seletor com 6 opções)
- 📆 **Escala** (12x36, 6x1, Diurno, etc)
- ⏰ **Horário** (Ex: 07:00 às 19:00)
- 📝 Observações detalhadas
- ✅ Checklists personalizados (ilimitados)
- 🔄 **MOVER CARD** - Transferir vigilante para outro posto

## 📊 Histórico de Movimentações

### Tipos de Registro

| Ícone | Tipo | Descrição | Cor |
|-------|------|-----------|-----|
| ➕ | CRIADO | Vigilante adicionado | Verde |
| ↔️ | MOVIDO | Movido entre listas | Azul |
| ✏️ | EDITADO | Dados atualizados | Laranja |
| 🚩 | STATUS_ALTERADO | Status modificado | Roxo |
| 🗑️ | DELETADO | Vigilante removido | Vermelho |

### Filtros Disponíveis

- **Todos** - Exibe todas as movimentações
- **Movidos** - Apenas transferências entre listas
- **Editados** - Apenas alterações de dados
- **Status** - Apenas mudanças de status

### Exemplo de Registro

```
↔️ João Silva (12345) foi movido de "TIGRE" para "LEÃO"
   Antigo: TIGRE → Novo: LEÃO
   ⏰ 06/12/2024 14:35:22
```

## 🚀 Como Usar

### 1. Criando Listas de Escalas

1. Clique em **"Adicionar Lista"**
2. Digite o nome (Ex: "🐯 TIGRE", "🦁 LEÃO", "🐻 URSO")
3. **(Opcional)** Preencha o **CCU** (Ex: 2564)
4. **(Opcional)** Preencha o **Número do Posto** (Ex: 400 0004590001001)
5. Clique em **"Salvar"**
6. Crie quantas listas precisar para organizar as equipes

**Nota:** Os campos CCU e Número do Posto aparecerão de forma compacta abaixo do nome da lista.

### 2. Adicionando Vigilantes

1. Em qualquer lista, clique em **"Adicionar Vigilante"**
2. Preencha os campos obrigatórios:
   - **Matrícula**: Número de identificação
   - **Nome**: Nome completo do vigilante
   - **Função**: Cargo/função
   - **Data de Admissão**: Data de contratação
   - **Status**: Situação atual
3. Preencha os campos opcionais:
   - **Telefone**: Contato do vigilante (Ex: (47) 99999-9999)
   - **Observações**: Informações adicionais
4. Crie **checklists** personalizados (opcional)
5. Clique em **"Salvar"**

### 3. Criando Checklists Personalizados

Os checklists são totalmente flexíveis:

**Exemplo 1: Treinamentos**
```
Nome: Treinamentos Obrigatórios
Itens:
- NR-10 Básico
- Primeiros Socorros
- Combate a Incêndio
- Reciclagem Anual
```

**Exemplo 2: Documentação**
```
Nome: Documentos
Itens:
- CNH Atualizada
- Certificado de Vigilante
- Atestado Médico
- Registro na PF
```

**Exemplo 3: Equipamentos**
```
Nome: EPI's Entregues
Itens:
- Colete
- Lanterna
- Rádio
- Apito
```

### 4. Movendo Vigilantes

**Opção 1: Drag and Drop**
- Clique e segure o card
- Arraste para a lista desejada
- Solte para finalizar
- ✅ Movimento registrado automaticamente no histórico

**Opção 2: Mover Card (Dentro do Modal)**
1. Clique no vigilante para editar
2. Na seção **"Ações do Card"**, localize **"Mover Card Para"**
3. Selecione o posto de destino na lista suspensa
4. Clique em **"Mover Para Este Posto"**
5. ✅ Card será transferido e registrado no histórico

### 4.1. Clonar Vigilante (Duplicar)

**Criar uma cópia idêntica de um vigilante na mesma lista:**
1. Passe o mouse sobre o card do vigilante
2. Clique no botão **📋 Copiar** que aparece no canto superior direito
3. ✅ Uma cópia será criada automaticamente na mesma lista com todos os dados

**Dica:** Use esta função para criar modelos de vigilantes ou quando um vigilante assume múltiplas funções.

### 5. Alterando Status

1. Clique no card do vigilante
2. Selecione o novo status:
   - **Em Serviço** - Vigilante ativo
   - **Livre** - Disponível para escala
   - **Férias** - Período de férias
   - **Afastado** - Afastamento médico/outros
   - **Demitido** - Não faz mais parte da equipe
   - **Em Admissão** - Processo de integração
3. Clique em **"Salvar"**
4. ✅ Mudança registrada no histórico

### 6. Usando a Busca

**Localização:** Campo de busca no board-header, ao lado do botão "Adicionar Lista".

**Você pode buscar por:**
- 🔍 **Nome do Vigilante** - Digite o nome completo ou parte dele
- 🔍 **Matrícula** - Digite o número da matrícula
- 🔍 **Nome da Lista/Posto** - Digite o nome do posto
- 🔍 **CCU** - Digite o código CCU
- 🔍 **Número do Posto** - Digite o número do posto

**Como funciona:**
1. Digite no campo de busca no cabeçalho
2. ⚡ Resultados aparecem em tempo real (após 300ms)
3. ✅ Cards e listas encontrados ficam **destacados em verde**
4. ⚪ Cards e listas não encontrados ficam **desbotados**
5. 📊 Contador mostra quantos resultados foram encontrados
6. ❌ Clique no **X** para limpar a busca

**Exemplos de busca:**
- `João` - Encontra todos os vigilantes com "João" no nome
- `12345` - Encontra o vigilante com matrícula 12345
- `TIGRE` - Encontra a lista TIGRE e todos os seus vigilantes
- `2564` - Encontra listas com CCU 2564

**Dica:** A busca é inteligente e busca em múltiplos campos simultaneamente!

### 7. Consultando o Histórico

1. Role a página até a seção **"Histórico de Movimentações"**
2. Use os **filtros** para encontrar ações específicas:
   - **Todos**: Visualizar tudo
   - **Movidos**: Ver transferências
   - **Editados**: Ver atualizações
   - **Status**: Ver mudanças de situação
3. Cada registro mostra:
   - Ícone colorido do tipo de ação
   - Descrição completa
   - Valores antigos e novos (quando aplicável)
   - Data e hora exata

### 8. Exportando Dados

1. Clique no ícone **"Exportar"** (📥) no cabeçalho
2. Escolha o tipo de exportação:
   - **⭐ Excel (.XLSX)** - Planilha profissional formatada (RECOMENDADO)
   - **Modelo de Importação Excel** - Template formatado para preencher
   - **Histórico Excel** - Todas as movimentações em XLSX
   - **Backup JSON** - Estrutura completa para backup
3. Clique no botão correspondente
4. ✅ Arquivo baixado automaticamente

**Arquivos gerados:**
- `NomeBoard_Completo_AAAAMMDD.xlsx` - Excel com 4 abas (Vigilantes, Resumo, Por Equipe, Instruções)
- `Modelo_Importacao_Vigilantes.xlsx` - Template com instruções
- `NomeBoard_Historico_AAAAMMDD.xlsx` - Histórico formatado
- `NomeBoard_Completo_AAAAMMDD.json` - Backup completo

**Campos no Excel de Exportação (15 colunas):**
- Matrícula, Nome Completo, **Telefone**, Função, Data Admissão, Status
- **Escala**, **Horário**
- Lista/Equipe, **CCU**, **Número Posto**
- Observações, Treinamentos, Documentos, Equipamentos

### 8. Importando Dados

#### Método 1: Usando o Modelo Excel (Recomendado)

1. Clique no ícone **"Exportar"** no cabeçalho
2. Clique em **"Baixar Modelo XLSX"**
3. Abra o arquivo no Excel ou LibreOffice
4. Leia a aba **"LEIA PRIMEIRO"** com instruções
5. Vá para a aba **"VIGILANTES"** e preencha os dados
6. Salve o arquivo
7. Clique em **"Importar"** no sistema
8. Selecione seu arquivo preenchido
9. Clique em **"Importar Excel"**
10. ✅ Vigilantes importados com histórico registrado

📖 **Veja o arquivo [GUIA_EXCEL.md](GUIA_EXCEL.md) para instruções detalhadas**

#### Método 2: Importar de Sistema Existente

1. Clique em **"Importar"**
2. Escolha **JSON** se vier do Trello
3. Selecione o arquivo
4. Clique em **"Importar JSON"**
5. ✅ Dados convertidos automaticamente

#### Formato da Planilha de Importação Excel

**Colunas da aba VIGILANTES (15 colunas):**
```
MATRÍCULA | NOME COMPLETO | TELEFONE | FUNÇÃO | DATA ADMISSÃO | STATUS | ESCALA | HORÁRIO | LISTA/EQUIPE | CCU | NÚMERO POSTO | OBSERVAÇÕES | TREINAMENTOS | DOCUMENTOS | EQUIPAMENTOS
```

**Campos obrigatórios:**
- `MATRÍCULA` - Número único
- `NOME COMPLETO` - Nome do vigilante
- `FUNÇÃO` - Cargo
- `DATA ADMISSÃO` - Formato: DD/MM/AAAA (Ex: 15/01/2024)
- `STATUS` - EM_SERVICO, LIVRE, FERIAS, AFASTADO, DEMITIDO, EM_ADMISSAO

**Campos opcionais:**
- `TELEFONE` - Ex: (47) 99999-9999
- `ESCALA` - Ex: 12x36, 6x1, Diurno, Noturno
- `HORÁRIO` - Ex: 07:00 às 19:00, 19:00 às 07:00
- `LISTA/EQUIPE` - Nome ou CCU da lista de destino
- `CCU` - Código do posto
- `NÚMERO POSTO` - Número de identificação do posto
- `OBSERVAÇÕES` - Informações adicionais
- `TREINAMENTOS`, `DOCUMENTOS`, `EQUIPAMENTOS` - Itens separados por vírgula

**Campos opcionais:**
- `Observacoes` - Texto livre
- `Checklist_Nome_X` - Nome do checklist
- `Checklist_Itens_X` - Itens separados por `;`

## 📁 Estrutura de Arquivos

```
taskflow/
├── index.html              # Interface principal
├── css/
│   └── style.css          # Estilos completos (cards, histórico, etc)
├── js/
│   ├── api.js             # API RESTful (boards, lists, cards, history)
│   └── app.js             # Lógica completa (exportação, importação)
├── data/                   # Dados importados
│   ├── joinville.csv
│   ├── joinville.json.txt
│   └── workspace.json.txt
├── README.md              # Documentação principal
└── GUIA_IMPORTACAO.md     # Guia detalhado de importação
```

## 📤 Exportação de Dados

### Tipos de Exportação

#### 1. **Exportar para Excel (CSV)**

Gera planilha com todos os vigilantes do board atual.

**Colunas exportadas:**
- Matrícula
- Nome Completo
- Função
- Data de Admissão
- Status (traduzido)
- Lista Atual
- Observações
- Checklists (formatados)

**Uso:**
- Relatórios para RH
- Backup dos dados
- Análise em Excel
- Compartilhamento com outras áreas

**Exemplo de saída:**
```csv
Matricula,Nome_Completo,Funcao,Data_Admissao,Status,Lista_Atual,Observacoes,Checklists
12345,"João Silva","Vigilante","2024-01-15","Em Serviço","TIGRE","Experiência 5 anos","Treinamentos: NR-10; Primeiros Socorros"
```

#### 2. **Exportar JSON Completo**

Exporta estrutura completa do board em formato JSON.

**Inclui:**
- Informações do board
- Todas as listas
- Todos os vigilantes com detalhes completos
- Checklists estruturados
- Data da exportação

**Uso:**
- Backup completo
- Migração de dados
- Integração com outros sistemas
- Versionamento de dados

**Exemplo de estrutura:**
```json
{
  "board": {
    "name": "JOINVILLE",
    "description": "Board de vigilantes",
    "exportDate": "2024-12-06T14:30:00Z"
  },
  "lists": [
    {"id": "list-1", "name": "TIGRE", "position": 1}
  ],
  "vigilantes": [
    {
      "matricula": "12345",
      "nome": "João Silva",
      "funcao": "Vigilante",
      "status": "EM_SERVICO",
      "checklists": [
        {
          "name": "Treinamentos",
          "items": ["NR-10", "Primeiros Socorros"]
        }
      ]
    }
  ]
}
```

#### 3. **Exportar Histórico**

Exporta todas as movimentações e alterações em CSV.

**Colunas:**
- Data/Hora
- Tipo de Ação
- Vigilante
- Descrição
- Valor Anterior
- Valor Novo
- Campo Alterado

**Uso:**
- Auditoria
- Relatórios de gestão
- Análise de rotatividade
- Compliance

**Exemplo:**
```csv
Data_Hora,Tipo_Acao,Vigilante,Descricao,Valor_Anterior,Valor_Novo
"2024-12-06 14:30","MOVIDO","João Silva (12345)","Movido de TIGRE para LEÃO","TIGRE","LEÃO"
```

#### 4. **Baixar Modelo de Importação**

Gera planilha CSV modelo pronta para preencher.

**Inclui:**
- Cabeçalhos corretos
- Linha de instruções
- Exemplo preenchido
- Comentários explicativos

**Uso:**
- Importação de novos vigilantes
- Padronização de dados
- Treinamento de usuários

## 🎯 Casos de Uso

### 📋 Gestão de Escalas

**Cenário**: Empresa de vigilância com 3 equipes

**Listas criadas:**
- 🐯 **TIGRE** - Equipe A (turno manhã)
- 🦁 **LEÃO** - Equipe B (turno tarde)
- 🐻 **URSO** - Equipe C (turno noite)
- 🏖️ **FÉRIAS** - Vigilantes em férias
- 🏥 **AFASTADOS** - Vigilantes afastados

**Benefícios:**
- Visualização rápida de quem está em cada equipe
- Status colorido facilita identificação
- Histórico completo de mudanças de escala

### 🔄 Controle de Rotatividade

**Uso do Histórico:**
- Identificar vigilantes que trocam muito de equipe
- Rastrear tempo em cada posição
- Auditar mudanças de status
- Gerar relatórios de permanência

### 📚 Gestão de Treinamentos

**Checklists por Vigilante:**
```
✅ Treinamentos Obrigatórios
  - [x] NR-10
  - [x] Primeiros Socorros
  - [ ] Reciclagem (pendente)

✅ Certificações
  - [x] Curso de Vigilante
  - [x] Porte de Arma
  - [ ] Extensão de Porte (vence em 30 dias)
```

### 📊 Indicadores

**Monitoramento via Histórico:**
- Taxa de movimentação por período
- Tempo médio em cada status
- Frequência de edições de dados
- Alterações de status mais comuns

## 🔧 API RESTful

### Endpoints de Vigilantes (Cards)

```javascript
// Listar vigilantes
GET /tables/cards?limit=1000

// Criar vigilante
POST /tables/cards
Body: {
  matricula, nome_vigilante, funcao, 
  data_admissao, status, descricao, checklists
}

// Atualizar vigilante
PATCH /tables/cards/{id}
Body: {campos a atualizar}

// Deletar vigilante
DELETE /tables/cards/{id}
```

### Endpoints de Histórico

```javascript
// Listar histórico
GET /tables/history?limit=500

// Adicionar registro
POST /tables/history
Body: {
  card_id, board_id, action_type,
  old_value, new_value, field_changed,
  description, timestamp
}
```

## 🎨 Paleta de Cores

### Status dos Vigilantes

```css
/* Em Serviço */
--status-em-servico: #10b981;

/* Livre */
--status-livre: #3b82f6;

/* Férias */
--status-ferias: #f59e0b;

/* Afastado */
--status-afastado: #ef4444;

/* Demitido */
--status-demitido: #6b7280;

/* Em Admissão */
--status-em-admissao: #8b5cf6;
```

### Ações do Histórico

```css
/* Criado */
--history-created: rgba(16, 185, 129, 0.2);

/* Movido */
--history-moved: rgba(59, 130, 246, 0.2);

/* Editado */
--history-edited: rgba(245, 158, 11, 0.2);

/* Status Alterado */
--history-status: rgba(139, 92, 246, 0.2);

/* Deletado */
--history-deleted: rgba(239, 68, 68, 0.2);
```

## 💡 Dicas e Boas Práticas

### 📌 Organização de Listas

**Sugestão de estrutura:**
```
1. 🐯 TIGRE (Equipe A)
2. 🦁 LEÃO (Equipe B)
3. 🐻 URSO (Equipe C)
4. 🆓 LIVRES (Disponíveis)
5. 🏖️ FÉRIAS (Em férias)
6. 🏥 AFASTADOS (Afastamento)
7. ⏳ EM ADMISSÃO (Novatos)
8. ❌ DESLIGADOS (Histórico)
```

### 🔍 Uso Eficiente do Histórico

**Filtros recomendados:**
- **Início do mês**: Filtrar "Movidos" para revisar escalas
- **Fim do mês**: Filtrar "Status" para relatórios
- **Auditoria**: Usar "Todos" e buscar por nome

### ✅ Checklists Eficientes

**Nomes descritivos:**
- ✅ "Treinamentos 2024"
- ✅ "Documentos Válidos"
- ✅ "EPI's Entregues"
- ❌ "Checklist 1" (muito genérico)

### 🎯 Status Adequados

| Situação | Status Correto |
|----------|----------------|
| Trabalhando normalmente | Em Serviço |
| Folga programada | Livre |
| Período de férias | Férias |
| Licença médica | Afastado |
| Não retornou | Demitido |
| Primeiro mês | Em Admissão |

## 🐛 Solução de Problemas

### Cards não aparecem
- ✅ Verifique se há um board ativo
- ✅ Confirme que está na lista correta
- ✅ Recarregue a página (F5)

### Histórico vazio
- ✅ Faça uma ação (mover, editar) para gerar registros
- ✅ Verifique se o filtro está em "Todos"
- ✅ Confirme que há um board selecionado

### Drag and drop não funciona
- ✅ Use navegador moderno (Chrome, Firefox, Edge)
- ✅ Desative extensões que possam interferir
- ✅ Tente em modo anônimo

### Checklists não salvam
- ✅ Preencha nome e itens
- ✅ Verifique se clicou em "Salvar" no modal
- ✅ Confirme que não há erros no console (F12)

## 📊 Dados de Exemplo

O sistema já vem com dados pré-cadastrados:

**Board**: JOINVILLE
**Listas**: 🐯 TIGRE, 🦁 LEÃO, 🐻 URSO, ✅ Concluídos

**Vigilantes de Exemplo**:
- **#83348** Natalina Neves Rodri - Em Serviço
- **#5455** Luciano de Oliveira - Em Serviço
- **#7589** Thiago Amarante Leite - Férias

## 🔐 Segurança

- ✅ Dados armazenados no sistema RESTful interno
- ✅ Sem transmissão para servidores externos
- ✅ Soft delete para recuperação de dados
- ✅ Histórico completo de auditoria
- ✅ Validação de entrada em todos os formulários

## 📱 Compatibilidade

### Navegadores
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

### Dispositivos
- ✅ Desktop (1920x1080+)
- ✅ Laptop (1366x768+)
- ✅ Tablet (768x1024+)
- ✅ Mobile (375x667+)

## 🚀 Próximas Funcionalidades

### Em Desenvolvimento

- [ ] **Relatórios**
  - Exportar histórico para Excel
  - Gráfico de distribuição por status
  - Tempo médio em cada lista

- [ ] **Notificações**
  - Alerta de vencimento de documentos
  - Lembretes de reciclagem de treinamentos
  - Notificação de mudanças importantes

- [ ] **Filtros Avançados**
  - Buscar por matrícula ou nome
  - Filtrar por status
  - Filtrar por função
  - Filtrar por data de admissão

- [ ] **Dashboard**
  - Estatísticas gerais
  - Gráficos de distribuição
  - Indicadores de produtividade

- [ ] **Anexos**
  - Upload de documentos
  - Fotos de perfil
  - Certificados digitalizados

## 📝 Changelog

### Versão 2.2.1 (2024-12-06) 🎯 CCU E NÚMERO DO POSTO
- 🏢 **Campos nas Listas/Equipes**
  - CCU (Centro de Custo) editável
  - Número do Posto editável
  - Exibição pequena abaixo do nome da lista
  - Campos opcionais
- 📊 **Exportação atualizada**
  - Colunas CCU e Número Posto na aba Vigilantes
  - Aba "Por Equipe" com CCU e Número Posto
  - 12 colunas na planilha principal
- 📥 **Importação inteligente**
  - Busca lista por nome ou CCU
  - Colunas CCU e Número Posto no modelo
  - Compatível com versões anteriores
- 📖 **Documentação**
  - ATUALIZACAO_CCU_POSTO.md com guia completo
  - Exemplos de uso e casos reais

### Versão 2.2.0 (2024-12-06) 🎉 EXCEL PROFISSIONAL
- 📊 **Exportação Excel (.XLSX) completa**
  - 4 abas: Vigilantes, Resumo, Por Equipe, Instruções
  - Formatação profissional com larguras ajustadas
  - Estatísticas automáticas
  - Colunas separadas para Treinamentos, Documentos, Equipamentos
- 📥 **Importação Excel (.XLSX) inteligente**
  - Suporte a formato brasileiro de data (DD/MM/AAAA)
  - Parser automático de datas do Excel
  - Importa de qualquer aba
  - Validação e normalização de dados
- 📋 **Modelo Excel (.XLSX) organizado**
  - Aba de instruções completas
  - Aba de dados formatada
  - Exemplos práticos
  - Status para copiar e colar
- 📖 **Guia Excel completo**
  - GUIA_EXCEL.md com 9KB de instruções
  - Dicas profissionais do Excel
  - Solução de problemas
  - Passo a passo ilustrado

### Versão 2.1.0 (2024-12-06)
- 📤 **Sistema completo de exportação**
  - Exportar para Excel (CSV)
  - Exportar JSON completo
  - Exportar histórico de movimentações
  - Download de modelo de importação
- 📥 **Importação aprimorada**
  - Suporte a checklists na importação
  - Validação automática de dados
  - Registro no histórico ao importar
  - Pular linhas de instrução automaticamente
- 📖 **Documentação completa**
  - Guia detalhado de importação (GUIA_IMPORTACAO.md)
  - Exemplos práticos
  - Solução de problemas

### Versão 2.0.0 (2024-12-06)
- 🎉 **Redesign completo focado em vigilantes**
- ✨ Cards compactos (70px) com matrícula, nome e status
- 🎨 Sistema de 6 status com cores diferenciadas
- 📊 Histórico completo de movimentações e alterações
- ✅ Checklists personalizados e ilimitados
- 🔄 Registro automático de todas as ações
- 📥 Importação adaptada para dados de vigilantes
- 📱 Interface responsiva aprimorada

### Versão 1.0.0 (2024-12-05)
- 🎉 Lançamento inicial
- ✨ Sistema básico de boards, listas e cards
- 🎨 Tema verde/escuro
- 🖱️ Drag and drop

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se livre para usar, modificar e distribuir.

---

**Desenvolvido com 💚 para otimizar a gestão de equipes de vigilância!**

Para publicar o site e torná-lo acessível online, utilize a aba **Publish** da plataforma.
