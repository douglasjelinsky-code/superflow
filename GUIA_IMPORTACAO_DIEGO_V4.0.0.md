# 📊 GUIA DE IMPORTAÇÃO - PLANILHA DIEGO.XLSX

**Versão**: 4.0.0  
**Data**: 08/12/2025  
**Desenvolvedor**: Douglas Jekinsky

---

## ✅ **SISTEMA JÁ ESTÁ 100% ADAPTADO!**

O sistema **Super Flow** está completamente preparado para importar e exportar planilhas no formato **DIEGO.xlsx**.

---

## 📋 **FORMATO DA PLANILHA DIEGO.XLSX**

### **Colunas Obrigatórias (em ordem):**

| # | **COLUNA** | **DESCRIÇÃO** | **EXEMPLO** |
|---|------------|---------------|-------------|
| 1 | **MATRÍCULA** | ID único do vigilante | `12345` |
| 2 | **NOME COMPLETO** | Nome completo | `João Silva Santos` |
| 3 | **TELEFONE** | Telefone (opcional) | `(47) 99999-9999` |
| 4 | **FUNÇÃO** | Cargo/posto | `Vigilante`, `Supervisor` |
| 5 | **DATA ADMISSÃO** | Data de entrada | `15/01/2024` |
| 6 | **STATUS** | Situação atual | `EM_SERVICO`, `FERIAS` |
| 7 | **ESCALA** | Escala de trabalho | `12x36`, `6x1` |
| 8 | **HORÁRIO** | Horário de trabalho | `07:00 às 19:00` |
| 9 | **LISTA/EQUIPE** | Nome da equipe | `TIGRE`, `LEÃO` |
| 10 | **CCU** | Centro de custo | `2564` |
| 11 | **NÚMERO POSTO** | Número do posto | `400 0004590001001` |
| 12 | **OBSERVAÇÕES** | Observações gerais | `Vigilante experiente` |
| 13 | **TREINAMENTOS** | Lista de treinamentos | `NR-10, Primeiros Socorros` |
| 14 | **DOCUMENTOS** | Documentos do vigilante | `CNH, RG, CPF` |
| 15 | **EQUIPAMENTOS** | EPIs entregues | `Rádio, Colete, Lanterna` |

---

## 📝 **VALORES VÁLIDOS PARA STATUS:**

Você pode usar **QUALQUER** desses valores (o sistema converte automaticamente):

### **1️⃣ EM SERVIÇO:**
- `EM_SERVICO`
- `EM SERVIÇO`
- `ATIVO`
- `ATIVA`
- `SERVICO`

### **2️⃣ FÉRIAS:**
- `FERIAS`
- `FÉRIAS`

### **3️⃣ AFASTADO:**
- `AFASTADO`
- `AFASTADA`
- `LICENÇA`
- `LICENCA`

### **4️⃣ DEMITIDO:**
- `DEMITIDO`
- `DEMITIDA`
- `DESLIGADO`

### **5️⃣ LIVRE:**
- `LIVRE`

### **6️⃣ EM ADMISSÃO:**
- `EM_ADMISSAO`
- `EM ADMISSÃO`
- `ADMISSAO`

---

## 🎯 **COMO IMPORTAR A PLANILHA DIEGO.XLSX**

### **PASSO 1: Prepare o Board Correto**

1. **Faça login no sistema** (`login.html`)
2. **Selecione o board correto** no seletor de boards (canto superior)
   - Se você tem múltiplos boards (ex: `EMPRESA A`, `EMPRESA B`, `FILIAL SUL`)
   - **Escolha o board onde deseja importar**
3. **Crie as listas (equipes) necessárias** ANTES de importar:
   - Clique em **"+ Adicionar Posto/Lista"**
   - Exemplo: crie listas chamadas `TIGRE`, `LEÃO`, `COBRA`, etc.
   - **As listas devem ter o MESMO NOME da coluna "LISTA/EQUIPE" da planilha**

---

### **PASSO 2: Importe a Planilha**

1. **Clique no botão "📥 Importar"** (canto superior direito)
2. **Escolha a opção "Excel (.xlsx)"**
3. **Selecione o arquivo `DIEGO.xlsx`**
4. **Clique em "Importar Excel"**
5. **Aguarde a mensagem de sucesso**
6. **Pronto!** Os vigilantes serão distribuídos nas listas corretas

---

### **PASSO 3: Verifique os Dados**

- Os vigilantes são **automaticamente distribuídos** nas listas conforme a coluna **"LISTA/EQUIPE"**
- Se a lista não existir, eles vão para a **primeira lista disponível**
- Todos os campos são preenchidos automaticamente:
  - ✅ Matrícula, Nome, Telefone, Função
  - ✅ Data de Admissão, Status
  - ✅ Escala, Horário
  - ✅ Observações
  - ✅ Checklists (Treinamentos, Documentos, Equipamentos)

---

## 🔄 **COMO EXPORTAR PARA O MESMO FORMATO**

1. **Clique no botão "📤 Exportar"** (canto superior direito)
2. **Escolha "Excel (.xlsx)"**
3. **O arquivo será baixado com TODAS as colunas da planilha DIEGO.xlsx**
4. **O arquivo exportado terá 4 abas:**
   - `Vigilantes` → Todos os dados (mesmo formato DIEGO.xlsx)
   - `Resumo` → Estatísticas por status
   - `Por Equipe` → Distribuição por lista
   - `Instruções` → Guia de uso

---

## 📌 **REGRAS DE IMPORTAÇÃO**

### ✅ **O QUE É OBRIGATÓRIO:**
- **MATRÍCULA** → Deve ser único
- **NOME COMPLETO** → Deve estar preenchido
- **STATUS** → Deve ser um dos valores válidos

### ⚠️ **O QUE É OPCIONAL:**
- Telefone
- Escala, Horário
- CCU, Número Posto
- Observações
- Treinamentos, Documentos, Equipamentos

### 🔄 **CONVERSÃO AUTOMÁTICA:**
- **Datas**: `DD/MM/AAAA` → `AAAA-MM-DD` (ISO 8601)
- **Status**: `ATIVO` → `EM_SERVICO` (normalizado)
- **Checklists**: Separadas por vírgula → Listas do sistema

---

## 🎯 **MAPEAMENTO INTELIGENTE DE LISTAS**

O sistema busca a lista correta usando **3 critérios**:

1. **Nome exato** da lista (ex: `TIGRE`)
2. **CCU** correspondente (ex: lista com CCU `2564`)
3. **Primeira lista disponível** (se não encontrar)

**💡 DICA:** Crie as listas ANTES de importar e use os mesmos nomes da planilha!

---

## 🚀 **TESTE RÁPIDO**

### **1. Baixe o Modelo:**
1. Clique em **"📥 Importar"**
2. Clique em **"📥 Baixar Modelo Excel"**
3. Um arquivo `Modelo_Importacao_Vigilantes.xlsx` será baixado
4. Este modelo já tem o formato correto!

### **2. Preencha o Modelo:**
- Copie os dados da planilha `DIEGO.xlsx`
- Cole no modelo baixado
- Salve o arquivo

### **3. Importe:**
- Volte ao sistema
- Clique em **"📥 Importar"** → **"Excel (.xlsx)"**
- Selecione o modelo preenchido
- Importe!

---

## ❓ **PROBLEMAS COMUNS**

### **❌ "Erro ao importar Excel"**
- **Causa:** Arquivo corrompido ou formato inválido
- **Solução:** Salve novamente como `.xlsx` (não `.xls`)

### **❌ "Vigilante não apareceu na lista correta"**
- **Causa:** Nome da lista diferente da planilha
- **Solução:** 
  1. Edite o vigilante
  2. Clique em "Mover Vigilante"
  3. Escolha a lista correta

### **❌ "Status apareceu como 'EM_SERVICO' ao invés de 'ATIVO'"**
- **Não é erro!** O sistema normaliza para o padrão interno
- Na exportação, o status será exibido corretamente

---

## 📊 **EXEMPLO PRÁTICO**

### **Planilha DIEGO.xlsx:**
```
MATRÍCULA | NOME COMPLETO        | TELEFONE         | FUNÇÃO    | DATA ADMISSÃO | STATUS     | ESCALA | HORÁRIO            | LISTA/EQUIPE | CCU  | NÚMERO POSTO
----------|----------------------|------------------|-----------|---------------|------------|--------|--------------------|--------------|------|-------------
12345     | João Silva Santos    | (47) 99999-9999  | Vigilante | 15/01/2024    | EM_SERVICO | 12x36  | 07:00 às 19:00     | TIGRE        | 2564 | 400 0004590001001
```

### **Resultado no Sistema:**
- ✅ Card criado com ID `12345`
- ✅ Nome: `João Silva Santos`
- ✅ Telefone: `(47) 99999-9999`
- ✅ Função: `Vigilante`
- ✅ Data: `2024-01-15`
- ✅ Status: `EM_SERVICO` (bolinha verde)
- ✅ Inserido na lista **"TIGRE"**
- ✅ Observações, checklists preenchidos

---

## 🎉 **TUDO PRONTO!**

Agora você pode:
- ✅ Importar planilhas no formato DIEGO.xlsx
- ✅ Exportar para o mesmo formato
- ✅ Baixar modelo em branco
- ✅ Converter status automaticamente
- ✅ Distribuir automaticamente por listas

**🔥 Sistema 100% compatível com o formato DIEGO.xlsx!**

---

**Desenvolvido por**: Douglas Jekinsky  
**Data**: 08/12/2025  
**Versão**: 4.0.0
