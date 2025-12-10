# 📥 Guia de Importação de Dados - Sistema de Vigilantes

Este guia explica como preparar e importar dados para o sistema usando planilhas CSV.

## 🎯 Passo a Passo

### 1️⃣ Baixar o Modelo

1. Abra o sistema
2. Clique no ícone **"Exportar"** (📥) no cabeçalho
3. Clique em **"Baixar Modelo CSV"**
4. Salve o arquivo `Modelo_Importacao_Vigilantes.csv`

### 2️⃣ Abrir no Excel/Google Sheets

**Excel:**
- Abra o Excel
- Arquivo → Abrir
- Selecione o arquivo baixado
- Se os dados não aparecerem organizados, use "Dados → Texto para Colunas"

**Google Sheets:**
- Acesse Google Sheets
- Arquivo → Importar
- Upload → Selecione o arquivo
- Separador: Vírgula
- Importar

### 3️⃣ Entender a Estrutura

O modelo possui estas colunas:

| Coluna | Descrição | Exemplo | Obrigatório |
|--------|-----------|---------|-------------|
| **Matricula** | Número de identificação | 12345 | ✅ Sim |
| **Nome_Completo** | Nome completo do vigilante | João Silva Santos | ✅ Sim |
| **Funcao** | Cargo/função | Vigilante | ✅ Sim |
| **Data_Admissao** | Data de contratação (AAAA-MM-DD) | 2024-01-15 | ✅ Sim |
| **Status** | Situação atual | EM_SERVICO | ✅ Sim |
| **Observacoes** | Anotações gerais | Experiência em vigilância | ❌ Não |
| **Checklist_Nome_1** | Nome do primeiro checklist | Treinamentos | ❌ Não |
| **Checklist_Itens_1** | Itens separados por `;` | NR-10; Primeiros Socorros | ❌ Não |
| **Checklist_Nome_2** | Nome do segundo checklist | Documentos | ❌ Não |
| **Checklist_Itens_2** | Itens separados por `;` | CNH; Certificado | ❌ Não |

### 4️⃣ Preencher os Dados

#### ✏️ Campo: Matricula
- **Formato**: Número ou texto
- **Exemplos**: `12345`, `VIG001`, `2024-001`
- ⚠️ **Importante**: Deve ser único para cada vigilante

#### 👤 Campo: Nome_Completo
- **Formato**: Texto livre
- **Exemplos**: `João Silva Santos`, `Maria Oliveira`
- ⚠️ **Dica**: Use nome completo para evitar confusões

#### 🛡️ Campo: Funcao
- **Opções recomendadas**:
  - `Vigilante`
  - `Supervisor`
  - `Líder de Equipe`
  - `Vigilante Patrimonial`
- **Exemplos**: `Vigilante`, `Supervisor`

#### 📅 Campo: Data_Admissao
- **Formato obrigatório**: `AAAA-MM-DD`
- **Exemplos corretos**: 
  - ✅ `2024-12-06`
  - ✅ `2023-01-15`
- **Exemplos incorretos**:
  - ❌ `06/12/2024` (formato errado)
  - ❌ `15-01-2023` (formato errado)

#### 🏷️ Campo: Status
- **Opções válidas** (exatamente como escrito):
  - `EM_SERVICO` - Trabalhando normalmente
  - `LIVRE` - Disponível para escalar
  - `FERIAS` - Em período de férias
  - `AFASTADO` - Afastamento (médico, etc)
  - `DEMITIDO` - Desligado da empresa
  - `EM_ADMISSAO` - Em processo de integração

⚠️ **Atenção**: Use exatamente estas palavras com MAIÚSCULAS e UNDERLINE (_)

#### 📝 Campo: Observacoes
- **Formato**: Texto livre
- **Exemplos**:
  ```
  Vigilante experiente, possui CNH categoria D
  ```
  ```
  Necessita reciclagem de NR-10 em março/2024
  ```

#### ✅ Campos: Checklists

Você pode adicionar **quantos checklists quiser**! Siga o padrão:

**Para o primeiro checklist:**
- `Checklist_Nome_1`: Nome do checklist
- `Checklist_Itens_1`: Itens separados por ponto e vírgula (`;`)

**Para o segundo checklist:**
- `Checklist_Nome_2`: Nome do checklist
- `Checklist_Itens_2`: Itens separados por ponto e vírgula (`;`)

**E assim por diante**: `Checklist_Nome_3`, `Checklist_Itens_3`, etc.

**Exemplos:**

```csv
Checklist_Nome_1,Checklist_Itens_1
Treinamentos,"NR-10 Básico; Primeiros Socorros; Combate a Incêndio"
```

```csv
Checklist_Nome_1,Checklist_Itens_1,Checklist_Nome_2,Checklist_Itens_2
Treinamentos,"NR-10 Básico; Primeiros Socorros","Documentos","CNH; Certificado; Atestado"
```

### 5️⃣ Exemplo Completo de Linha

```csv
Matricula,Nome_Completo,Funcao,Data_Admissao,Status,Observacoes,Checklist_Nome_1,Checklist_Itens_1,Checklist_Nome_2,Checklist_Itens_2
12345,"João Silva Santos","Vigilante","2024-01-15","EM_SERVICO","Vigilante experiente com CNH D","Treinamentos","NR-10 Básico; Primeiros Socorros; Combate a Incêndio","Documentos","CNH Atualizada; Certificado de Vigilante; Atestado Médico"
```

### 6️⃣ Validar os Dados

Antes de importar, verifique:

✅ **Datas no formato correto** (AAAA-MM-DD)  
✅ **Status escritos corretamente** (com MAIÚSCULAS e _)  
✅ **Matrícula única para cada vigilante**  
✅ **Nome completo preenchido**  
✅ **Função especificada**  
✅ **Itens de checklist separados por ponto e vírgula (`;`)**

### 7️⃣ Salvar o Arquivo

**Excel:**
- Arquivo → Salvar Como
- Tipo: **CSV (delimitado por vírgulas) (*.csv)**
- Salvar

**Google Sheets:**
- Arquivo → Fazer download
- **Valores separados por vírgula (.csv)**

⚠️ **Importante**: Salve no formato CSV, não XLSX!

### 8️⃣ Importar para o Sistema

1. Abra o sistema
2. Clique no ícone **"Importar"** (📤) no cabeçalho
3. Selecione a aba **"Importar CSV"**
4. Clique em "Selecionar arquivo"
5. Escolha seu arquivo CSV
6. Clique em **"Importar CSV"**
7. Aguarde a mensagem de conclusão
8. ✅ Pronto! Seus vigilantes foram importados

## 📊 Exemplo de Planilha Preenchida

| Matricula | Nome_Completo | Funcao | Data_Admissao | Status | Observacoes | Checklist_Nome_1 | Checklist_Itens_1 |
|-----------|---------------|--------|---------------|--------|-------------|------------------|-------------------|
| 001 | João Silva | Vigilante | 2024-01-15 | EM_SERVICO | Experiência 5 anos | Treinamentos | NR-10; Primeiros Socorros |
| 002 | Maria Santos | Supervisor | 2023-06-20 | EM_SERVICO | Líder de equipe | Certificações | Supervisor; Gestão |
| 003 | Pedro Souza | Vigilante | 2024-03-10 | FERIAS | Férias até 20/12 | Documentos | CNH; RG; CPF |
| 004 | Ana Costa | Vigilante | 2023-11-05 | LIVRE | Disponível | Treinamentos | Combate Incêndio |

## 🔍 Solução de Problemas

### ❌ Erro: "Data inválida"
**Causa**: Data no formato errado  
**Solução**: Use o formato `AAAA-MM-DD`  
**Exemplo**: `2024-12-06` ✅

### ❌ Erro: "Status inválido"
**Causa**: Status escrito incorretamente  
**Solução**: Use exatamente uma destas opções:
- `EM_SERVICO`
- `LIVRE`
- `FERIAS`
- `AFASTADO`
- `DEMITIDO`
- `EM_ADMISSAO`

### ❌ Checklists não aparecem
**Causa**: Itens não separados corretamente  
**Solução**: Use ponto e vírgula (`;`) entre itens  
**Exemplo**: `Item 1; Item 2; Item 3` ✅

### ❌ Arquivo não é reconhecido
**Causa**: Formato do arquivo incorreto  
**Solução**: Salve como CSV (não XLSX)

### ❌ Caracteres estranhos (ç, ã, é)
**Causa**: Problema de codificação  
**Solução ao salvar CSV no Excel**:
1. Arquivo → Salvar Como
2. Ferramentas → Opções da Web
3. Codificação: **UTF-8**
4. Salvar

## 💡 Dicas e Boas Práticas

### ✅ Organização

1. **Padronize as matrículas**
   - Use um padrão: `VIG001`, `VIG002`, etc.
   - Ou números sequenciais: `1`, `2`, `3`, etc.

2. **Mantenha os status atualizados**
   - Importe vigilantes ativos com `EM_SERVICO`
   - Use `LIVRE` para disponíveis
   - Registre `FERIAS` e `AFASTADO` quando aplicável

3. **Use checklists desde o início**
   - Treinamentos obrigatórios
   - Documentação necessária
   - Equipamentos entregues

### ✅ Backup

Antes de importar:
1. **Exporte os dados atuais** (botão Exportar)
2. Guarde como backup
3. Faça a importação
4. Se algo der errado, você tem os dados salvos

### ✅ Importação em Lotes

Para muitos vigilantes:
1. Importe 10-20 por vez
2. Verifique se está correto
3. Continue importando

### ✅ Validação Visual

Após importar:
1. Verifique se todos apareceram
2. Confira os status (cores)
3. Abra alguns cards para verificar detalhes
4. Consulte o histórico

## 📞 Precisa de Ajuda?

Se encontrar dificuldades:
1. Verifique este guia novamente
2. Baixe o modelo novamente
3. Compare seu arquivo com o exemplo
4. Teste com poucos registros primeiro

## 🎓 Exemplos Prontos

### Exemplo 1: Vigilante Básico
```csv
Matricula,Nome_Completo,Funcao,Data_Admissao,Status,Observacoes
V001,"Carlos Mendes","Vigilante","2024-06-15","EM_SERVICO","Novo funcionário"
```

### Exemplo 2: Com Treinamentos
```csv
Matricula,Nome_Completo,Funcao,Data_Admissao,Status,Observacoes,Checklist_Nome_1,Checklist_Itens_1
V002,"Roberto Lima","Vigilante","2023-03-20","EM_SERVICO","5 anos de experiência","Treinamentos","NR-10; Primeiros Socorros; Combate Incêndio"
```

### Exemplo 3: Completo
```csv
Matricula,Nome_Completo,Funcao,Data_Admissao,Status,Observacoes,Checklist_Nome_1,Checklist_Itens_1,Checklist_Nome_2,Checklist_Itens_2,Checklist_Nome_3,Checklist_Itens_3
V003,"Sandra Ferreira","Supervisor","2022-01-10","EM_SERVICO","Líder de equipe com certificações","Treinamentos","NR-10; Gestão; Liderança","Documentos","CNH B; RG; CPF; Certificado","Equipamentos","Rádio; Colete; Lanterna; Apito"
```

---

**📚 Mantenha este guia salvo para consultas futuras!**

**🎯 Boa importação!**
