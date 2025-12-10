# 🎯 Atualização - CCU e Número do Posto

## ✨ NOVA FUNCIONALIDADE

Agora cada **Lista/Equipe** pode ter:
- **CCU** (Centro de Custo)
- **Número do Posto**

Ambos são **editáveis** e aparecem **pequenos** abaixo do nome da lista!

---

## 📋 ONDE APARECEM

### Na Interface:

```
┌─────────────────────────────────────┐
│  🐯 TIGRE                    [15]   │
│  CCU: 2564                          │
│  Nº 400 0004590001001               │
├─────────────────────────────────────┤
│  Cards dos vigilantes...            │
└─────────────────────────────────────┘
```

**Visual:**
- Fonte pequena (10px)
- Cor cinza claro
- Duas linhas:
  - `CCU: 2564`
  - `Nº 400 0004590001001`

---

## ✏️ COMO EDITAR

### Ao Criar Lista:

```
1. Clique em "Adicionar Lista"
2. Preencha:
   Nome: 🐯 TIGRE
   CCU: 2564
   Número do Posto: 400 0004590001001
3. Salvar
```

### Ao Editar Lista:

```
1. Clique no ícone de editar da lista (✏️)
2. Altere CCU ou Número do Posto
3. Salvar
```

---

## 📊 NA EXPORTAÇÃO EXCEL

### Aba: VIGILANTES

Agora inclui **2 colunas novas**:

| MATRÍCULA | NOME | ... | LISTA | **CCU** | **Nº POSTO** | ... |
|-----------|------|-----|-------|---------|--------------|-----|
| 12345 | João Silva | ... | TIGRE | **2564** | **400 0004590001001** | ... |
| 67890 | Maria Santos | ... | LEÃO | **2565** | **400 0004590001002** | ... |

### Aba: POR EQUIPE

Agora mostra CCU e Número do Posto:

| Equipe/Lista | **CCU** | **Número Posto** | Quantidade |
|--------------|---------|------------------|------------|
| TIGRE | **2564** | **400 0004590001001** | 15 |
| LEÃO | **2565** | **400 0004590001002** | 12 |
| URSO | **2566** | **400 0004590001003** | 13 |

---

## 📥 NA IMPORTAÇÃO EXCEL

### Modelo Atualizado:

O modelo Excel agora tem **2 colunas novas**:

```
Colunas da planilha:
1. MATRÍCULA
2. NOME COMPLETO
3. FUNÇÃO
4. DATA ADMISSÃO
5. STATUS
6. LISTA/EQUIPE
7. CCU ← NOVO!
8. NÚMERO POSTO ← NOVO!
9. OBSERVAÇÕES
10. TREINAMENTOS
11. DOCUMENTOS
12. EQUIPAMENTOS
```

### Como Preencher:

**CCU:**
```
Formato: Texto ou número
Exemplo: 2564
Opcional: Deixe em branco se não tiver
```

**Número do Posto:**
```
Formato: Texto
Exemplo: 400 0004590001001
Exemplo: N 400 0004590001001
Opcional: Deixe em branco se não tiver
```

### Exemplo de Linha:

```excel
MATRÍCULA: 12345
NOME: João Silva Santos
FUNÇÃO: Vigilante
DATA: 15/01/2024
STATUS: EM_SERVICO
LISTA: TIGRE
CCU: 2564 ← NOVO!
Nº POSTO: 400 0004590001001 ← NOVO!
OBSERVAÇÕES: Vigilante experiente
TREINAMENTOS: NR-10, Primeiros Socorros
DOCUMENTOS: CNH, RG, CPF
EQUIPAMENTOS: Rádio, Colete
```

---

## 🔍 LÓGICA DE IMPORTAÇÃO

Ao importar, o sistema:

1. **Busca a lista pelo nome**
   - Se encontrar "TIGRE" → usa essa lista

2. **Ou busca pelo CCU**
   - Se encontrar lista com CCU "2564" → usa essa lista

3. **Se não encontrar**
   - Usa a primeira lista disponível

**Isso permite:**
- Importar vigilantes para listas específicas
- Validar pelo CCU se os nomes mudarem
- Flexibilidade na importação

---

## 💡 CASOS DE USO

### 1. Controle de Postos

```
Cada equipe tem um posto com CCU:

TIGRE → CCU 2564 → Posto 400 0004590001001
LEÃO → CCU 2565 → Posto 400 0004590001002
URSO → CCU 2566 → Posto 400 0004590001003
```

### 2. Relatórios Financeiros

```
Exportar Excel → Aba "Por Equipe"
Você tem:
- Lista de todas as equipes
- CCU de cada uma
- Número de vigilantes
- Pode calcular custos por CCU
```

### 3. Importação Organizada

```
Sua planilha de RH tem CCU?
Importe direto!
O sistema vai colocar cada vigilante 
na lista correta pelo CCU.
```

---

## 📝 EXEMPLO COMPLETO

### Criar 3 Equipes:

```
Equipe 1:
Nome: 🐯 TIGRE
CCU: 2564
Nº Posto: 400 0004590001001

Equipe 2:
Nome: 🦁 LEÃO
CCU: 2565
Nº Posto: 400 0004590001002

Equipe 3:
Nome: 🐻 URSO
CCU: 2566
Nº Posto: 400 0004590001003
```

### Resultado Visual:

```
┌─────────────────────────┐  ┌─────────────────────────┐  ┌─────────────────────────┐
│ 🐯 TIGRE          [15]  │  │ 🦁 LEÃO           [12]  │  │ 🐻 URSO           [13]  │
│ CCU: 2564               │  │ CCU: 2565               │  │ CCU: 2566               │
│ Nº 400 0004590001001    │  │ Nº 400 0004590001002    │  │ Nº 400 0004590001003    │
├─────────────────────────┤  ├─────────────────────────┤  ├─────────────────────────┤
│ [Cards vigilantes]      │  │ [Cards vigilantes]      │  │ [Cards vigilantes]      │
└─────────────────────────┘  └─────────────────────────┘  └─────────────────────────┘
```

### Exportação:

**Excel → Aba VIGILANTES:**
| MAT | NOME | ... | LISTA | CCU | Nº POSTO | ... |
|-----|------|-----|-------|-----|----------|-----|
| 001 | João | ... | TIGRE | 2564 | 400 0004590001001 | ... |
| 002 | Maria | ... | LEÃO | 2565 | 400 0004590001002 | ... |
| 003 | Pedro | ... | URSO | 2566 | 400 0004590001003 | ... |

**Excel → Aba POR EQUIPE:**
| Lista | CCU | Nº Posto | Qtd |
|-------|-----|----------|-----|
| TIGRE | 2564 | 400 0004590001001 | 15 |
| LEÃO | 2565 | 400 0004590001002 | 12 |
| URSO | 2566 | 400 0004590001003 | 13 |

---

## 🎯 BENEFÍCIOS

✅ **Rastreamento completo** - CCU e Posto em cada lista  
✅ **Exportação organizada** - Dados prontos para relatórios  
✅ **Importação inteligente** - Sistema encontra lista certa  
✅ **Visual limpo** - Info pequena, não polui interface  
✅ **Flexível** - Campos opcionais, use se precisar  

---

## ⚙️ CONFIGURAÇÃO RECOMENDADA

### Para Empresas de Vigilância:

```
Para cada posto/local:
1. Crie uma lista com o nome do posto
2. Adicione o CCU do cliente
3. Adicione o número do posto
4. Aloque vigilantes nessa lista
5. Exporte para relatórios mensais
```

### Para Controle Interno:

```
Se usar CCU interno:
1. CCU pode ser código da equipe
2. Número do Posto pode ser ID do local
3. Use para rastreamento de custos
4. Facilita fechamento mensal
```

---

## 🔧 TÉCNICO

### Schema Atualizado:

```javascript
Table: lists
- id (text)
- board_id (text)
- name (text)
- ccu (text) ← NOVO
- numero_posto (text) ← NOVO
- position (number)
```

### Interface:

```html
<div class="list-info-small">
  <span>CCU: 2564</span>
  <span>Nº 400 0004590001001</span>
</div>
```

### CSS:

```css
.list-info-small {
  font-size: 10px;
  font-weight: 400;
  color: var(--text-muted);
}
```

---

## 📖 COMPATIBILIDADE

✅ **Listas antigas** - Continuam funcionando (CCU e Posto ficam vazios)  
✅ **Importação** - Campos opcionais, pode deixar em branco  
✅ **Exportação** - Mostra vazio se não tiver  
✅ **Histórico** - Não afeta registros existentes  

---

## ✅ CHECKLIST DE MIGRAÇÃO

Se você já tem listas criadas:

```
☐ 1. Edite cada lista
☐ 2. Adicione o CCU
☐ 3. Adicione o Número do Posto
☐ 4. Salve
☐ 5. Exporte para ver o resultado
☐ 6. Próximas importações já terão os dados!
```

---

## 🎉 PRONTO!

Agora você tem controle completo de CCU e Número do Posto!

**Principais usos:**
- Relatórios financeiros
- Controle de postos
- Rastreamento de custos
- Organização de equipes

**🚀 Atualize suas listas agora mesmo!**

---

_Versão 2.2.1 - Dezembro 2024_
