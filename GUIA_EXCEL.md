# 📊 Guia Excel - Sistema de Vigilantes

Guia completo para usar planilhas Excel (.XLSX) no sistema.

---

## ⭐ POR QUE EXCEL (.XLSX) É MELHOR?

### ✅ Vantagens do Excel sobre CSV:

| Recurso | Excel (.XLSX) | CSV |
|---------|---------------|-----|
| **Múltiplas abas** | ✅ Sim | ❌ Não |
| **Formatação** | ✅ Cores, negrito, bordas | ❌ Só texto |
| **Fórmulas** | ✅ Sim | ❌ Não |
| **Instruções na mesma planilha** | ✅ Sim | ❌ Não |
| **Dados organizados** | ✅ Muito melhor | ⚠️ Básico |
| **Abre direto no Excel** | ✅ Sim | ⚠️ Pode ter problemas |
| **Formatação de datas** | ✅ Automática | ❌ Manual |

---

## 📥 EXPORTAR DADOS PARA EXCEL

### Passo a Passo:

```
1. Clique no botão "Exportar" (📥) no cabeçalho
2. Clique em "Baixar Excel (.XLSX)" (botão grande e destacado)
3. Aguarde o download
4. Abra o arquivo no Excel
```

### O que você vai receber:

**📁 Arquivo: `NomeBoard_Completo_AAAAMMDD.xlsx`**

**4 abas organizadas:**

#### 📋 Aba 1: VIGILANTES
```
Todos os vigilantes com 10 colunas organizadas:
• MATRÍCULA
• NOME COMPLETO
• FUNÇÃO
• DATA ADMISSÃO
• STATUS
• LISTA/EQUIPE
• OBSERVAÇÕES
• TREINAMENTOS
• DOCUMENTOS
• EQUIPAMENTOS
```

#### 📊 Aba 2: RESUMO
```
Estatísticas por status:
• Em Serviço: 25 vigilantes (62.5%)
• Férias: 8 vigilantes (20%)
• Livre: 5 vigilantes (12.5%)
• Afastado: 2 vigilantes (5%)
```

#### 👥 Aba 3: POR EQUIPE
```
Distribuição por equipe:
• TIGRE: 15 vigilantes
• LEÃO: 12 vigilantes
• URSO: 13 vigilantes
```

#### 📖 Aba 4: INSTRUÇÕES
```
Instruções completas de uso
Data e hora da exportação
Informações do board
```

---

## 📤 IMPORTAR VIGILANTES DO EXCEL

### Método 1: Baixar Modelo (RECOMENDADO)

```
1. Clique em "Exportar" no sistema
2. Clique em "Baixar Modelo XLSX"
3. Abra o arquivo no Excel
4. Leia a aba "LEIA PRIMEIRO"
5. Vá para a aba "VIGILANTES"
6. Delete as linhas de exemplo
7. Preencha com seus dados
8. Salve o arquivo
9. Clique em "Importar" no sistema
10. Selecione o arquivo
11. Clique em "Importar Excel"
```

### O que vem no modelo:

**📁 Arquivo: `Modelo_Importacao_Vigilantes.xlsx`**

**2 abas:**

#### 📖 Aba 1: LEIA PRIMEIRO
```
Instruções completas
Status válidos para copiar e colar
Dicas de preenchimento
Avisos importantes
```

#### 📋 Aba 2: VIGILANTES
```
Colunas já formatadas
Linha de exemplo para entender
Larguras ajustadas
Pronto para preencher
```

---

## 📝 COMO PREENCHER A PLANILHA

### Coluna por Coluna:

#### 1️⃣ MATRÍCULA
```
O que é: Número único de identificação
Formato: Número ou texto
Exemplos: 
  ✅ 12345
  ✅ VIG001
  ✅ 2024-001
⚠️ Deve ser único!
```

#### 2️⃣ NOME COMPLETO
```
O que é: Nome completo do vigilante
Formato: Texto livre
Exemplos:
  ✅ João Silva Santos
  ✅ Maria Oliveira Costa
💡 Use nome completo para evitar confusão
```

#### 3️⃣ FUNÇÃO
```
O que é: Cargo ou função
Formato: Texto livre
Opções sugeridas:
  ✅ Vigilante
  ✅ Supervisor
  ✅ Líder de Equipe
  ✅ Vigilante Patrimonial
```

#### 4️⃣ DATA ADMISSÃO
```
O que é: Data de contratação
Formato: DD/MM/AAAA
Exemplos:
  ✅ 15/01/2024
  ✅ 20/06/2023
  ✅ 10/12/2024

⚠️ O Excel formata automaticamente!
Basta digitar: 15/01/2024
```

#### 5️⃣ STATUS
```
O que é: Situação atual do vigilante
Formato: Texto exato

COPIE E COLE UM DESTES:
  ✅ EM_SERVICO
  ✅ LIVRE
  ✅ FERIAS
  ✅ AFASTADO
  ✅ DEMITIDO
  ✅ EM_ADMISSAO

⚠️ Use EXATAMENTE como está escrito!
```

#### 6️⃣ OBSERVAÇÕES
```
O que é: Anotações gerais
Formato: Texto livre
Exemplos:
  ✅ "Vigilante experiente com 5 anos de atuação"
  ✅ "Necessita reciclagem de NR-10 em março"
  ✅ "Disponível para turno noturno"
```

#### 7️⃣ TREINAMENTOS
```
O que é: Cursos e capacitações
Formato: Itens separados por vírgula
Exemplos:
  ✅ NR-10 Básico, Primeiros Socorros, Combate a Incêndio
  ✅ Gestão de Equipes, Liderança
  ✅ Vigilante Patrimonial, Porte de Arma

💡 Separe com vírgula (,)
```

#### 8️⃣ DOCUMENTOS
```
O que é: Documentação do vigilante
Formato: Itens separados por vírgula
Exemplos:
  ✅ CNH B, RG, CPF, Certificado de Vigilante
  ✅ CNH Atualizada, Atestado Médico
  ✅ Registro na PF, Certidões Negativas

💡 Separe com vírgula (,)
```

#### 9️⃣ EQUIPAMENTOS
```
O que é: EPIs e materiais entregues
Formato: Itens separados por vírgula
Exemplos:
  ✅ Rádio, Colete, Lanterna, Apito
  ✅ Tablet, Uniforme, Crachá
  ✅ Cassetete, Algema, Spray

💡 Separe com vírgula (,)
```

---

## 🎯 EXEMPLO COMPLETO DE LINHA

```excel
MATRÍCULA: 12345
NOME COMPLETO: João Silva Santos
FUNÇÃO: Vigilante
DATA ADMISSÃO: 15/01/2024
STATUS: EM_SERVICO
OBSERVAÇÕES: Vigilante experiente com 5 anos de atuação na área
TREINAMENTOS: NR-10 Básico, Primeiros Socorros, Combate a Incêndio
DOCUMENTOS: CNH B, RG, CPF, Certificado de Vigilante
EQUIPAMENTOS: Rádio, Colete, Lanterna, Apito
```

---

## 📊 DICAS DO EXCEL

### ✅ Formatação Automática

**Datas:**
```
Digite: 15/01/2024
Excel formata: 15/01/2024
Sistema importa: Correto ✅
```

**Números de Matrícula:**
```
Se começar com zero (ex: 00123):
1. Clique com botão direito na coluna
2. Formatar células
3. Escolha "Texto"
4. Digite: 00123
Resultado: Mantém o zero ✅
```

### ✅ Copiar Status

**Facilite o preenchimento:**
```
1. Digite os status válidos em uma área vazia:
   EM_SERVICO
   LIVRE
   FERIAS
   AFASTADO
   DEMITIDO
   EM_ADMISSAO

2. Para cada vigilante:
   - Copie o status correto
   - Cole na célula
```

### ✅ Preenchimento Rápido

**Para campos repetidos:**
```
Exemplo: Função = "Vigilante"

1. Digite "Vigilante" na primeira célula
2. Selecione a célula
3. Arraste o quadradinho no canto inferior direito
4. Todas as células ficam com "Vigilante"
```

### ✅ Lista Suspensa (Dropdown)

**Criar dropdown de Status:**
```
1. Selecione a coluna STATUS
2. Menu "Dados" → "Validação de Dados"
3. Permitir: Lista
4. Fonte: EM_SERVICO,LIVRE,FERIAS,AFASTADO,DEMITIDO,EM_ADMISSAO
5. OK

Agora cada célula tem um dropdown! ⬇️
```

---

## ⚠️ ERROS COMUNS E SOLUÇÕES

### ❌ Erro: "Arquivo não importa"

**Causas:**
- Arquivo não é .xlsx
- Aba errada selecionada
- Arquivo corrompido

**Solução:**
```
1. Verifique se é .xlsx (não .xls ou .csv)
2. Salve novamente: Arquivo → Salvar Como → .xlsx
3. Certifique-se que tem uma aba chamada "VIGILANTES"
```

### ❌ Erro: "Status inválido"

**Causas:**
- Status escrito errado
- Espaços extras
- Letras minúsculas

**Solução:**
```
Use EXATAMENTE:
✅ EM_SERVICO (com underscore)
❌ EM SERVICO (sem underscore)
❌ em_servico (minúscula)
❌ Em Serviço (formatado)
```

### ❌ Erro: "Data inválida"

**Causas:**
- Formato errado
- Data como texto

**Solução:**
```
✅ Use formato brasileiro: DD/MM/AAAA
✅ Deixe o Excel formatar automaticamente
❌ Não force formato YYYY-MM-DD no Excel
```

### ❌ Matricula com zero sumiu (00123 virou 123)

**Solução:**
```
1. Antes de digitar, formate a coluna como "Texto"
2. Ou digite: '00123 (com apóstrofo antes)
3. Resultado: 00123 ✅
```

---

## 🎓 PASSO A PASSO COMPLETO

### Do zero até importar:

```
✅ 1. Baixar modelo
   Sistema → Exportar → Baixar Modelo XLSX

✅ 2. Abrir no Excel
   Duplo clique no arquivo baixado

✅ 3. Ler instruções
   Vá para aba "LEIA PRIMEIRO"

✅ 4. Ir para aba VIGILANTES
   Clique na aba "VIGILANTES"

✅ 5. Deletar exemplos
   Delete a linha 2 (exemplo)
   Mantenha linha 1 (cabeçalhos)

✅ 6. Preencher dados
   Digite seus vigilantes
   Uma linha = um vigilante

✅ 7. Revisar tudo
   Confira matrícula única
   Confira status corretos
   Confira datas

✅ 8. Salvar arquivo
   Arquivo → Salvar
   Ou Ctrl+S

✅ 9. Importar no sistema
   Sistema → Importar → Importar Excel
   Selecione o arquivo
   Importar Excel

✅ 10. Conferir resultado
   Veja se todos apareceram
   Confira os status (cores)
   Veja o histórico
```

---

## 💡 DICAS PROFISSIONAIS

### 1. Use Validação de Dados

Crie dropdowns para campos fixos:
- Status (6 opções fixas)
- Função (suas funções mais comuns)

### 2. Congele Cabeçalhos

```
1. Clique na linha 2
2. Menu "Exibir" → "Congelar Painéis"
3. Cabeçalhos ficam sempre visíveis ao rolar
```

### 3. Adicione Filtros

```
1. Selecione o cabeçalho (linha 1)
2. Menu "Dados" → "Filtro"
3. Agora pode filtrar por status, função, etc.
```

### 4. Use Cores

Marque vigilantes com atenção:
- Amarelo: Documentos vencendo
- Vermelho: Treinamentos atrasados
- Verde: Tudo em dia

### 5. Mantenha um Backup

```
Antes de importar:
1. Salve uma cópia
2. Nome: Importacao_BACKUP_DD-MM-AAAA.xlsx
3. Se der erro, você tem o backup!
```

---

## 📞 PRECISA DE AJUDA?

### Fluxo de Suporte:

```
1. Confira este guia novamente
2. Veja os exemplos na planilha modelo
3. Teste com 2-3 vigilantes primeiro
4. Se funcionar, importe o resto
```

### Checklist de Validação:

```
Antes de importar, confira:
☑️ Arquivo é .xlsx?
☑️ Aba "VIGILANTES" existe?
☑️ Linha 1 tem os cabeçalhos?
☑️ Matrículas são únicas?
☑️ Status estão corretos?
☑️ Datas no formato DD/MM/AAAA?
☑️ Nomes completos preenchidos?
☑️ Salvou o arquivo?
```

---

## 🎉 PRONTO!

Agora você está expert em usar planilhas Excel no sistema de vigilantes!

**Principais vantagens que você ganhou:**

✅ Planilhas organizadas e profissionais  
✅ Múltiplas abas com informações  
✅ Formatação automática de datas  
✅ Estatísticas e resumos  
✅ Instruções sempre disponíveis  
✅ Fácil de compartilhar com equipe  

**🚀 Comece agora baixando o modelo Excel!**

---

_Para dúvidas sobre importação básica, veja também: GUIA_IMPORTACAO.md_
