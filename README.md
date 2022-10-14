# Banco-de-Horas-FacPonto
  Programas para a análise do banco de dados do aplicativo FacPonto

## Pré processamento
  O FacPonto pode gerar dois tipos de relatórios, o Extrato do Banco de Horas e o Relatório de Registros de Ponto. Para a utilização dos programas, eles serão necessários. Recomenda-se o uso desses relatórios em um período mensal, pois períodos muito grandes podem fazer os relatórios saírem deformados.
- Primeiro, é preciso salvar os relatórios em planilhas, e então, converter para o formato .xlsx
- Além disso, devido a motivos de imprevisibilidade, é preciso filtrar as células que começam com "Emissão:", na primeira coluna da planilha, excluindo estas células, mas se atentando para não excluir as linhas que estão, para não haver perda de informação, nem deslocar as colunas de lugares.

Uma possível forma, seria selecionar estas linhas, excluir a primeira coluna, deslocando as células para a esquerda, e então inserir uma couluna, deslocando as células para a direita.

## Como descobrir o endereço de arquivos
  Para a execução de todos os programas, é perguntado o endereço de algum arquivo, para descobrir este endereço, é possível cliclar com o botão direito do mouse no arquivo desejado, clicar em "Propriedades" e verificar em "Local". Isto indica a pasta em que se encontra o arquivo, após este texto, basta inserir uma "\\", e o nome do arquivo, junto com seu formato, que também é possível ver nas propriedades do arquivo.
Caso o arquivo esteja na mesma pasta do programa, basta digitar o nome e a extensão do arquivo.

## Como usar os programas
  Após o préprocessamento, existem 8 programas, que realizam alguma análisa e retornam um arquivo contendo as informações. O arquivo retornado estará no formato .json, e para converter em planilhas, é possível usar o programa <b>planilha</b>.

### banco
  Este programa recebe o Extrato do Banco de Horas no formato .xlsx e retorna uma listagem de cada funcionário que teve faltas no banco de horas no período selecionado, e os dias em que ocorreram.

### ponto
  Este programa recebe o Relatório de Registros de Ponto no formato .xlsx e retorna os dias em que algum funcionário trabalhou menos de 6 horas. É possível desconsiderar feriados, digitando "s" quando perguntado se quer inserir um feriado, e então digitar a data como descrito.

### ticket
  Este programa recebe o Relatório de Registros de Ponto no formato .xlsx e retorna os dias em que algum funcionário trabalhou pelo menos 6 horas em feriados ou finais de semana. No início do programa é perguntado a data de quais feriados considerar, seguindo a formatação explicada no programa.

### adicional
  Este programa recebe o Extrato do Banco de Horas no formato .xlsx e retorna todas as horas adicionais calculadas pelo sistema Facponto.

### extra
  Este programa recebe o Relatório de Registros de Ponto no formato .xlsx e retorna todas as horas extras superiores a 15 minutos realizadas em sábados ou dias de semana e registradas no sistema por meio da marcação de ponto. É possível desconsiderar feriados, digitando "s" quando perguntado se quer inserir um feriado, e então digitar a data como descrito.

### extra_dobrado
  Este programa recebe o Relatório de Registros de Ponto no formato .xlsx e retorna todas as horas extras superiores a 15 minutos realizadas em domingos e feriados e registradas no sistema por meio da marcação de ponto. No início do programa é perguntado a data de quais feriados considerar, seguindo a formatação explicada no programa.

### saldo
  Este programa recebe o Extrato do Banco de Horas no formato .xlsx e retorna a quantiadade de horas no banco de horas de cada funcionário no início do período da planilha

### descontos
  Este programa recebe o Extrato do Banco de Horas no formato .xlsx e retorna a variação do banco de horas de cada funcionário no período da planilha

## Convertendo os arquivos JSON para planilhas

### planilha
  Por meio do programa planilha, é perguntado o endereço do arquivo JSON, e então uma planilha com os dados será criada no mesmo endereço do arquivo

## Total e Planilha Final

### total
  O programa total recebe o endereço de 5 arquivos json, resultantes da execução dos programas saldo, descontos, extra, extras_dobrado e adicionais, e então retorna uma listagem de funcionários no formato JSON, com o saldo de banco de horas, variação do período, horas extras, horas extras dobradas e horas adicionais.

### planilha_final
  Este programa recebe o endereço de um arquivo JSON do programa total, e gera uma planilha com os dados no mesmo endereço.



