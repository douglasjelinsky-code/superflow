# ⚡ Quick Start - Sistema de Vigilantes

Guia rápido para começar a usar o sistema em 5 minutos!

---

## 🚀 Começando do Zero

### 1️⃣ Criar Suas Listas (1 minuto)

```
1. Clique em "Adicionar Lista"
2. Digite o nome: "🐯 TIGRE"
3. Salvar
4. Repita para: "🦁 LEÃO", "🐻 URSO"
```

✅ **Pronto!** Suas escalas estão criadas.

---

### 2️⃣ Adicionar Primeiro Vigilante (2 minutos)

```
1. Na lista TIGRE, clique "+ Adicionar Vigilante"
2. Preencha:
   Matrícula: 001
   Nome: João Silva Santos
   Função: Vigilante
   Data Admissão: 2024-01-15
   Status: Em Serviço
3. Salvar
```

✅ **Pronto!** Primeiro vigilante cadastrado.

---

### 3️⃣ Mover Vigilante (10 segundos)

```
1. Arraste o card de João Silva
2. Solte na lista LEÃO
```

✅ **Pronto!** Vigilante movido e registrado no histórico.

---

## 📥 Importar Vários Vigilantes de uma Vez

### Método Rápido (3 minutos)

```
1. Clique em "Exportar" (📥)
2. Clique em "Baixar Modelo CSV"
3. Abra o arquivo no Excel
4. Delete as 2 primeiras linhas (instruções e exemplo)
5. Preencha com seus vigilantes
6. Salvar como CSV
7. Clique em "Importar" (📤)
8. Selecione o arquivo
9. Importar CSV
```

✅ **Pronto!** Todos os vigilantes importados.

---

## 📊 Formato Mínimo da Planilha

| Matricula | Nome_Completo | Funcao | Data_Admissao | Status |
|-----------|---------------|--------|---------------|--------|
| 001 | João Silva | Vigilante | 2024-01-15 | EM_SERVICO |
| 002 | Maria Santos | Supervisor | 2024-02-20 | EM_SERVICO |
| 003 | Pedro Costa | Vigilante | 2024-03-10 | FERIAS |

**Dica:** Copie estes dados, cole no Excel e salve como CSV!

---

## 🎯 Status Válidos

Use exatamente assim (copie e cole):

- `EM_SERVICO` - Trabalhando
- `LIVRE` - Disponível
- `FERIAS` - De férias
- `AFASTADO` - Afastado
- `DEMITIDO` - Desligado
- `EM_ADMISSAO` - Novo contratado

---

## ✅ Adicionar Checklists

### Na planilha de importação:

```csv
Matricula,Nome_Completo,...,Checklist_Nome_1,Checklist_Itens_1
001,"João Silva",...,"Treinamentos","NR-10; Primeiros Socorros"
```

### No sistema (ao criar/editar):

```
1. Clique no vigilante
2. Clique "+ Adicionar Checklist"
3. Nome: Treinamentos
4. Itens: (um por linha)
   NR-10 Básico
   Primeiros Socorros
   Combate a Incêndio
5. Salvar
```

---

## 📤 Exportar Dados

### Para Excel:
```
1. Exportar → Baixar CSV
2. Abrir no Excel
```

### Backup Completo:
```
1. Exportar → Baixar JSON
2. Guardar o arquivo
```

### Histórico:
```
1. Exportar → Baixar Histórico
2. Abrir no Excel
```

---

## 🔍 Ver Histórico

```
1. Role a página até o final
2. Veja todas as movimentações
3. Use os filtros: Todos | Movidos | Editados | Status
```

---

## ⚡ Atalhos Rápidos

| Ação | Como Fazer |
|------|------------|
| Adicionar Vigilante | Clique "+ Adicionar Vigilante" na lista |
| Mover Vigilante | Arraste e solte |
| Editar Vigilante | Clique no card |
| Ver Histórico | Role até o final da página |
| Exportar Dados | Clique no ícone 📥 |
| Importar Dados | Clique no ícone 📤 |

---

## 🆘 Problemas Comuns

### ❌ "Data inválida"
Use: `2024-12-06` (AAAA-MM-DD)

### ❌ "Status inválido"  
Use: `EM_SERVICO` (com underscore e maiúsculas)

### ❌ "Arquivo não importa"
Salve como CSV, não XLSX

### ❌ "Checklists não aparecem"
Separe itens com `;` (ponto e vírgula)

---

## 📖 Precisa de Mais Detalhes?

- **Importação completa**: Leia `GUIA_IMPORTACAO.md`
- **Ver exemplo visual**: Abra `exemplo-planilha.html`
- **Documentação completa**: Leia `README.md`

---

## 🎓 Exemplo Completo Pronto para Copiar

### Planilha CSV:

```csv
Matricula,Nome_Completo,Funcao,Data_Admissao,Status,Observacoes,Checklist_Nome_1,Checklist_Itens_1
001,"João Silva Santos","Vigilante","2024-01-15","EM_SERVICO","Vigilante experiente","Treinamentos","NR-10; Primeiros Socorros"
002,"Maria Oliveira","Supervisor","2024-02-20","EM_SERVICO","Supervisora turno manhã","Certificações","Supervisor; Gestão"
003,"Pedro Costa","Vigilante","2024-03-10","FERIAS","Férias até 20/12","Documentos","CNH; RG; CPF"
```

**Como usar:**
1. Copie o texto acima
2. Cole em um arquivo novo no Excel
3. Salve como CSV
4. Importe no sistema

---

## ✅ Checklist de Primeiros Passos

- [ ] Criar listas de escalas
- [ ] Adicionar primeiro vigilante manualmente
- [ ] Testar drag and drop
- [ ] Baixar modelo CSV
- [ ] Importar planilha com vigilantes
- [ ] Ver histórico de movimentações
- [ ] Exportar dados para backup
- [ ] Adicionar checklists em um vigilante

---

## 🎯 Você Está Pronto!

Com estes passos básicos, você já pode:

✅ Gerenciar vigilantes  
✅ Organizar escalas  
✅ Importar e exportar dados  
✅ Rastrear movimentações  
✅ Criar checklists personalizados  

**🚀 Comece agora mesmo!**

---

_Para suporte detalhado, consulte os outros arquivos de documentação._
