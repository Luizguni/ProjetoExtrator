# Projeto Extrator SAM

**Objetivo**  
Programa ABAP para extração de dados de Cliente, Fornecedor, Material Expeditável e Todos os Materiais, com geração de arquivos `.CSV`.

---

## 📦 Estruturas no Dicionário (SE11)

- **ZSAM_EXTRATOR**
  - Campos: `KUNNR`, `NAME1`, `STRAS`, `ORT01`, `STATE`, `REGION`, `COUNTRY`, `TEL_NUMBER`, `FAX_NUMBER`, `SMTP_ADDR`, `CONTACT_NAME`
  - Finalidade: execução da subrotina `extrair_cliente`

- **ZSAM_EXTRATOR_FORNECEDOR**
  - Campos: `LIFNR`, `NAME1`, `STRAS`, `ORT01`, `STATE`, `REGION`, `COUNTRY`, `TEL_NUMBER`, `FAX_NUMBER`, `SMTP_ADDR`, `CONTACT_NAME`
  - Finalidade: execução da subrotina `extrair_fornecedor`

- **ZSAM_EXTRATOR_MATERIAL_EXP**
  - Campos: `MATNR`, `MAKTX`, `MEINS`, `MATKL`, `EAN11`, `SITE_NAME`
  - Finalidade: execução da subrotina `extrair_material_exp`

- **ZSAM_EXTR_TODOS_MATERIAIS**
  - Campos: `MATNR`, `MAKTX`, `MEINS`, `MATKL`, `SITE_NAME`, `LIFNR`, `NAME1`
  - Finalidade: execução da subrotina `extrair_todos_materiais`

---

## ⚙️ Programa ABAP

- **Nome:** `ZEXTRATOR_SAM`
- **Parametros de seleção:**
  - `p_cli`, `p_forn`, `p_mexp`, `p_mall` (flags booleanas)
  - `p_path` (caminho do arquivo)
- **Subrotinas:**
  - `extrair_cliente` → gera `CLIENTE.csv`
  - `extrair_fornecedor` → gera `FORNECEDOR.csv`
  - `extrair_material_exp` → gera `MAT_EXP.csv`
  - `extrair_todos_materiais` → gera `TODOS_MAT.csv`
  - `gerar_csv` → lógica comum de gravação de CSV

---

## 🧪 Testes realizados

| Tipo de Extração       | Arquivo Gerado     | Registros Simulados | Status |
|------------------------|--------------------|----------------------|--------|
| Cliente                | `CLIENTE.csv`      | 1 registro           | ✅     |
| Fornecedor             | `FORNECEDOR.csv`   | 1 registro           | ✅     |
| Material Expeditável   | `MAT_EXP.csv`      | 1 registro           | ✅     |
| Todos os Materiais     | `TODOS_MAT.csv`    | 1 registro           | ✅     |
| Múltiplos tipos juntos | 4 arquivos gerados | —                    | ✅     |

---

## 📁 Ordem de Transporte

- **Pacote de entrega:** `ZSAM_EXTRATOR`
- **Ordem Workbench:** `BMFK900547`
- Objetos presentes:
  - `ZEXTRATOR_SAM` (PROG)
  - `ZSAM_EXTRATOR`, `ZSAM_EXTRATOR_FORNECEDOR`, `ZSAM_EXTRATOR_MATERIAL_EXP`, `ZSAM_EXTR_TODOS_MATERIAIS` (estruturas)

---

## 🚀 Como utilizar

1. Faça o **download/import** da ordem ou clone este repositório.
2. Acesse a transação `SE38` e execute `ZEXTRATOR_SAM`.
3. Marque os parâmetros desejados e informe o `p_path` (ex: `/usr/sap/tmp` ou caminho local).
4. Execute e verifique os arquivos `.CSV` na pasta especificada.

---

## 🛠️ Próximos passos

- Adicionar **log de execução** via tabela `ZTPAR_OPLOG`
- Gerar **headers nos arquivos `.CSV`**
- Agendar como **Job batch automático**
- Fácil integração com **transação Z customizada**

---

## 📞 Contato

Desenvolvedor: **Luiz Guni**  
E-mail: `luiz.guny@gmail.com`

---

### ✅ Como adicionar ao GitHub

1. Clone seu repositório:  
   ```bash
   git clone https://github.com/Luizguni/ProjetoExtrator.git
   cd ProjetoExtrator
