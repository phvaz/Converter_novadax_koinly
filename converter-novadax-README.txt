script funcional em Python que converte automaticamente o extrato da Novadax para o formato de CSV compatível com o Koinly. A ideia é simplificar o processo de importação de dados de trades, depósitos e saques, evitando qualquer edição manual.

O que o script faz
Lê o arquivo CSV exportado da Novadax.
Identifica os tipos de operação (Compra, Venda, Depósito, Taxa de transação, Saque etc.).
Extrai e normaliza os valores numéricos (incluindo casas decimais, sem arredondar).
Gera um novo CSV já pronto para importar no Koinly.

Como usar
Instale o Python 3 (caso ainda não tenha).
Salve o script em um arquivo, por exemplo: converter_novadax_koinly.py.
Tenha o arquivo de extrato da Novadax, por exemplo: Extrato_Anual_Novadax.csv, na mesma pasta do script (ou ajuste o caminho no código).
No terminal, execute:
python converter_novadax_koinly.py

Isso vai gerar um arquivo chamado Koinly_Custom_CSV.csv com todos os dados formatados.

Requisitos
Python 3
Biblioteca unicodedata (já vem incluída na instalação padrão do Python).
Possivelmente re e csv, que também fazem parte da biblioteca padrão.

Caso tenham dúvidas ou sugestões de melhoria, fiquem à vontade para falar comigo. Podemos ajustar o script para atender a outros cenários ou corrigir qualquer detalhe. 
