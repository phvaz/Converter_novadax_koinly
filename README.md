# Conversor de CSV da Novadax para Koinly

Este script Python converte um arquivo CSV gerado pela Novadax em um formato compatível com o Koinly, uma plataforma de gerenciamento de impostos para criptomoedas.

## Requisitos

- Python 3.x
- Bibliotecas padrão do Python: `csv`, `datetime`, `re`, `unicodedata`

## Como usar

1. **Preparação do ambiente**:
   - Certifique-se de que o Python 3.x está instalado no seu sistema.
   - Não é necessário instalar bibliotecas adicionais, pois o script utiliza apenas módulos padrão do Python.

2. **Preparação do arquivo CSV**:
   - Exporte o seu extrato de ativos da Novadax no formato CSV.
   - Coloque o arquivo CSV exportado no mesmo diretório onde o script está localizado.
   - Renomeie o arquivo CSV para `Extrato_de_ativos.csv` ou altere o nome do arquivo no código-fonte.

3. **Execução do script**:
   - Abra o terminal e navegue até o diretório onde o script está localizado.
   - Execute o script com o seguinte comando:
     ```bash
     python3 converter_novadax_koinly.py
     ```
   - O script irá gerar um novo arquivo CSV chamado `Koinly_Custom_CSV.csv` no mesmo diretório.

4. **Importação no Koinly**:
   - Abra o Koinly e vá para a seção de importação de transações.
   - Selecione o arquivo `Koinly_Custom_CSV.csv` gerado pelo script.
   - Siga as instruções do Koinly para finalizar a importação.

## Funções principais

- **normalize_str(s: str) -> str**: Remove acentos e caracteres especiais, retornando o texto em ASCII básico e em minúsculas.
- **convert_date(novadax_date: str) -> str**: Converte a data/hora do formato `DD/MM/YYYY HH:MM:SS` para `YYYY-MM-DD HH:MM UTC`.
- **extract_numeric_value(text: str) -> str**: Extrai o primeiro número de uma string, remove separadores de milhar e converte vírgula em ponto decimal.
- **process_novadax_row(row)**: Processa uma linha do CSV da Novadax e a converte para o formato do Koinly.
- **convert_novadax_to_koinly(input_file, output_file)**: Lê o CSV da Novadax e gera um CSV no formato Koinly.

## Exemplo de uso

```python
if __name__ == "__main__":
    input_file = "Extrato_de_ativos.csv"
    output_file = "Koinly_Custom_CSV.csv"
    convert_novadax_to_koinly(input_file, output_file)
    print(f"Arquivo convertido salvo em: {output_file}")
