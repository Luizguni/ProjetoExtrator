# zsam_extrator

Projeto ABAP para extração de dados no SAP e geração de arquivos CSV, com foco em clientes, fornecedores e materiais.

## ✅ Funcionalidades

- Extração de Clientes
- Extração de Fornecedores
- Extração de Materiais de Exportação
- Extração de Todos os Materiais
- Geração automática de arquivos CSV

## 📂 Parâmetros do programa

| Parâmetro | Descrição |
| --------- | --------- |
| `p_cli`   | Extrair clientes |
| `p_forn`  | Extrair fornecedores |
| `p_mexp`  | Extrair materiais de exportação |
| `p_mall`  | Extrair todos os materiais |
| `p_first` | Indicador de extração inicial |
| `p_delta` | Indicador de extração delta |
| `p_path`  | Caminho de saída do arquivo CSV |

## 🚀 Como usar

1. Ajuste os parâmetros desejados ao executar o report `ZSAM_EXTRATOR` no SAP.
2. O programa realizará a extração conforme os parâmetros indicados.
3. Arquivos CSV serão gerados no diretório especificado em `p_path`.

## 🛠️ Tecnologias

- ABAP (Advanced Business Application Programming)
- SAP ECC / S/4HANA (compatível)
- Manipulação de arquivos via `OPEN DATASET`

## 👤 Autor

Luiz Guni
