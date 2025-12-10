# 📊 GUIA DE IMPORTAÇÃO EXCEL CUSTOMIZADO
**Data:** 2025-12-08  
**Sistema:** SUPER FLOW  
**Desenvolvedor:** DOUGLAS JEKINSKY

---

## 🎯 OBJETIVO

Adaptar a importação e exportação de Excel do sistema para o formato da sua planilha específica (DOUGLAS.xlsx).

---

## 📋 PASSO 1: ANALISAR A PLANILHA

### Como Visualizar a Estrutura da Sua Planilha

1. **Abra o arquivo:**
   ```
   visualizar-planilha.html
   ```

2. **O que você verá:**
   - Número de abas na planilha
   - Nome de cada aba
   - Total de linhas e colunas
   - Estrutura detalhada de cada coluna
   - Exemplos de dados

3. **Anote as informações importantes:**
   - ✅ Nome das colunas (ex: Nome, Matrícula, Data_Admissao, etc.)
   - ✅ Tipo de dados em cada coluna (texto, número, data)
   - ✅ Formato das datas (se houver)
   - ✅ Quais colunas são obrigatórias
   - ✅ Nome da(s) aba(s) que contém os dados

---

## 📊 ESTRUTURA ESPERADA NO SISTEMA ATUAL

O sistema SUPER FLOW atualmente espera as seguintes colunas:

### Campos Obrigatórios
```
- Nome_Vigilante (texto)
- Matricula (texto ou número)
- Posto (texto)
- Status (texto: EM_SERVICO, LIVRE, FERIAS, etc.)
```

### Campos Opcionais
```
- CCU (texto)
- Numero_Posto (texto ou número)
- Data_Admissao (data no formato YYYY-MM-DD)
- Telefone (texto)
- Checklists (texto separado por vírgula)
```

---

## 🔄 PASSO 2: MAPEAR AS COLUNAS

### Exemplo de Mapeamento

Se sua planilha tem:
```
Coluna na Planilha → Coluna no Sistema
────────────────────────────────────
Nome              → Nome_Vigilante
CPF               → Matricula
Local             → Posto
Situação          → Status
Centro Custo      → CCU
Posto Nº          → Numero_Posto
Admissão          → Data_Admissao
Contato           → Telefone
```

---

## 💻 PASSO 3: INFORMAÇÕES QUE PRECISO

Para adaptar o sistema, me envie:

### 1️⃣ Estrutura das Colunas
```
Copie e cole aqui as informações que aparecem em:
"📋 Estrutura das Colunas"

Exemplo:
1. Nome - Tipo: string - Exemplo: João Silva
2. Matricula - Tipo: number - Exemplo: 12345
3. Posto - Tipo: string - Exemplo: Shopping Center
...
```

### 2️⃣ Nome da Aba Principal
```
Qual aba contém os dados dos vigilantes?
Exemplo: "Planilha1" ou "Vigilantes" ou "Dados"
```

### 3️⃣ Mapeamento de Status
```
Quais são os status na sua planilha e como devem ser mapeados?

Exemplo:
- Na planilha: "Em Serviço" → No sistema: "EM_SERVICO"
- Na planilha: "Disponível" → No sistema: "LIVRE"
- Na planilha: "Férias" → No sistema: "FERIAS"
...
```

### 4️⃣ Formato de Data (se houver)
```
Como as datas estão formatadas na planilha?
Exemplo: DD/MM/YYYY ou MM/DD/YYYY ou YYYY-MM-DD
```

---

## 🛠️ PASSO 4: ADAPTAÇÃO DO CÓDIGO

Após receber as informações, vou:

1. ✅ Modificar a função `importExcel()` em `js/app.js`
2. ✅ Adaptar o mapeamento de colunas
3. ✅ Ajustar conversão de datas (se necessário)
4. ✅ Criar validações específicas
5. ✅ Modificar a exportação para o mesmo formato
6. ✅ Criar template de download adaptado

---

## 📥 PASSO 5: COMO IMPORTAR NO BOARD CORRETO

### Método Atual (Precisará de Adaptação)

1. **Selecione o Board Correto**
   ```
   1. Faça login no sistema
   2. No seletor de boards (header), escolha o board desejado
      Exemplo: "🏢 São Paulo" ou "🏢 Rio de Janeiro"
   ```

2. **Abra o Modal de Importação**
   ```
   1. Clique no botão 📤 (Importar) no header
   2. Selecione a opção "Importar Excel"
   ```

3. **Escolha o Arquivo**
   ```
   1. Clique em "Escolher arquivo"
   2. Selecione sua planilha DOUGLAS.xlsx
   3. Clique em "Importar Excel"
   ```

4. **Sistema Irá:**
   ```
   ✅ Ler a aba especificada
   ✅ Mapear as colunas automaticamente
   ✅ Converter formatos (datas, status, etc.)
   ✅ Criar cards para cada linha
   ✅ Distribuir nas listas do board
   ✅ Registrar no histórico
   ```

### Seleção da Lista de Destino

Atualmente, o sistema importa para listas baseado no campo:
```
- Se Status = "EM_SERVICO" → Lista "Em Serviço"
- Se Status = "LIVRE" → Lista "Livre"
- Se Status = "FERIAS" → Lista "Férias"
etc.
```

**Podemos adaptar isso para sua necessidade!**

---

## 🎯 EXEMPLO PRÁTICO

### Cenário: Importar 50 vigilantes para o board "São Paulo"

```
1. Login no sistema
2. Selecionar board: 🏢 São Paulo
3. Clicar em 📤 Importar
4. Escolher: Importar Excel
5. Selecionar: DOUGLAS.xlsx
6. Clicar: Importar Excel
7. Sistema processa e distribui:
   - 20 vigilantes → Lista "Em Serviço"
   - 15 vigilantes → Lista "Livre"
   - 10 vigilantes → Lista "Férias"
   - 5 vigilantes → Lista "Afastado"
8. ✅ Sucesso: "50 vigilantes importados!"
```

---

## 🔍 INFORMAÇÕES QUE VOU PRECISAR

### Template de Resposta

Por favor, abra `visualizar-planilha.html` e me envie:

```
1. NOME DAS ABAS:
   - Aba 1: _________________
   - Aba 2: _________________
   - Aba principal (dados): _________________

2. COLUNAS DA ABA PRINCIPAL:
   (Copie da seção "📋 Estrutura das Colunas")
   
   1. _______________ - Tipo: _______ - Exemplo: _______
   2. _______________ - Tipo: _______ - Exemplo: _______
   3. _______________ - Tipo: _______ - Exemplo: _______
   ...

3. MAPEAMENTO DESEJADO:
   Coluna Planilha → Coluna Sistema
   _______________ → Nome_Vigilante
   _______________ → Matricula
   _______________ → Posto
   _______________ → Status
   _______________ → CCU
   _______________ → Numero_Posto
   _______________ → Data_Admissao
   _______________ → Telefone

4. VALORES DE STATUS NA PLANILHA:
   - Status 1: _____________ → EM_SERVICO
   - Status 2: _____________ → LIVRE
   - Status 3: _____________ → FERIAS
   - Status 4: _____________ → AFASTADO
   - Status 5: _____________ → DEMITIDO
   - Status 6: _____________ → EM_ADMISSAO

5. FORMATO DE DATA (se houver):
   - Formato na planilha: _____________
   - Exemplo: _____________

6. NÚMERO DE LINHAS NA PLANILHA:
   - Total aproximado: _____________
```

---

## 🚀 PRÓXIMOS PASSOS

### O Que Fazer Agora

1. ✅ **Abrir visualizar-planilha.html**
   ```
   Clique no arquivo e veja a estrutura
   ```

2. ✅ **Preencher o template acima**
   ```
   Anote todas as informações solicitadas
   ```

3. ✅ **Me enviar as informações**
   ```
   Cole as informações preenchidas
   ```

4. ✅ **Aguardar adaptação**
   ```
   Vou modificar o código para sua planilha
   ```

5. ✅ **Testar importação**
   ```
   Após adaptação, testaremos juntos
   ```

---

## 📊 EXEMPLO DE ESTRUTURA QUE POSSO ADAPTAR

### Formato Atual (Sistema)
```csv
Nome_Vigilante,Matricula,Posto,Status,CCU,Numero_Posto,Data_Admissao,Telefone
João Silva,12345,Shopping A,EM_SERVICO,CC001,101,2024-01-15,11999998888
Maria Santos,12346,Condominio B,LIVRE,CC002,102,2024-02-20,11888887777
```

### Formato Customizado (Sua Planilha) - EXEMPLO
```csv
Nome,CPF,Local,Situacao,Centro_Custo,Posto_Num,Data_Entrada,Contato
João Silva,123.456.789-00,Shopping A,Trabalhando,CC001,101,15/01/2024,11999998888
Maria Santos,987.654.321-00,Condominio B,Disponível,CC002,102,20/02/2024,11888887777
```

**Vou criar o mapeamento automático!**

---

## ⚠️ OBSERVAÇÕES IMPORTANTES

### Antes de Importar

1. ✅ **Backup dos dados atuais**
   - Exporte os dados atuais antes de importar
   - Use: Exportar → Backup JSON

2. ✅ **Selecione o board correto**
   - Verifique se está no board certo antes de importar
   - Dados vão para o board atualmente selecionado

3. ✅ **Revise a planilha**
   - Remova linhas vazias
   - Verifique se todas as colunas obrigatórias estão preenchidas
   - Confira se os status estão corretos

4. ✅ **Teste com poucos dados primeiro**
   - Crie uma planilha de teste com 5-10 linhas
   - Importe e valide se está correto
   - Depois importe a planilha completa

---

## 🎯 RESULTADO ESPERADO

Após a adaptação, você poderá:

1. ✅ Importar sua planilha DOUGLAS.xlsx diretamente
2. ✅ Colunas mapeadas automaticamente
3. ✅ Datas convertidas corretamente
4. ✅ Status mapeados para os valores do sistema
5. ✅ Cards criados no board correto
6. ✅ Distribuição automática nas listas
7. ✅ Exportação no mesmo formato da importação

---

## 📞 SUPORTE

### Precisa de Ajuda?

1. **Visualizar estrutura:**
   ```
   Abra: visualizar-planilha.html
   ```

2. **Problemas na visualização:**
   ```
   - Limpe o cache (Ctrl+Shift+R)
   - Verifique se o arquivo planilha_modelo.xlsx está na mesma pasta
   ```

3. **Dúvidas sobre mapeamento:**
   ```
   Me envie a estrutura das colunas e te ajudo!
   ```

---

**Status:** ⏳ **AGUARDANDO INFORMAÇÕES DA PLANILHA**

**Ação Necessária:**
1. Abra `visualizar-planilha.html`
2. Anote a estrutura das colunas
3. Me envie as informações do template acima

💚 **Assim que receber, adapto o código imediatamente!**

---

**Desenvolvedor:** DOUGLAS JEKINSKY  
**Versão do Guia:** 1.0
