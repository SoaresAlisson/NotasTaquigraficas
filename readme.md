# Notas Taquigráficas - CPI da Pandemia
O script pega as Notas Taquigráficas e a estrutura em dataframes .Rds e tabelas .csv.
No caso, o script pega dados da CPI da Pandemia, mas com pequenos ajustes, pode funcionar também para outras notas taquigráficas.

Aqui você encontra notas taquigráficas da [CPI da Pandemia](https://legis.senado.leg.br/comissoes/comissao?codcol=2441) estruturadas em dataframe Rds (da linguagem R) e em tabela csv, feita com um script em R (será disponibilizado em breve). Deste modo é possível separar somente as falas de pessoas específicas, de blocos parlamentares específicos ou de partidos, usando apenas filtros simples (como do dplyr).
- [Aqui](https://www25.senado.leg.br/web/atividade/notas-taquigraficas/-/notas/r/9996) você encontra um exemplo de uma das notas taquigráficas no site do Senado.

## Se quiser apenas baixar os arquivos:
- Todas as tabelas estão em formato .Rds (na [pasta rds](https://github.com/SoaresAlisson/NotasTaquigraficas/tree/master/rds)) e em formato .csv (na [pasta csv](https://github.com/SoaresAlisson/NotasTaquigraficas/tree/master/csv))
 - Há a tabela com a listagem com todas as Notas Taquigráficas na versão csv ([csv/NotasTaq-CPI_Pandemia-listagem.csv](https://github.com/SoaresAlisson/NotasTaquigraficas/blob/master/csv/NotasTaq-CPI_Pandemia-listagem.csv)) ou na versão .Rds ([rds/NotasTaq-CPI_Pandemia-listagem.Rds](https://github.com/SoaresAlisson/NotasTaquigraficas/raw/master/rds/NotasTaq-CPI_Pandemia-listagem.Rds)). Estes contém a seguinte estrutura:
  - Coluna `data`(data da referida reunião no formato ano-mês-dia), `reuniao_dia` (cada reunião possui um número diferente), `Depoente.tema` (nome do depoente em oitiva, ou se reunião deliberativa) e `link_notaTaquigrafica` com o link para a Nota taquigráfica.

Já os arquivos de Nota Taquigráfica estão estruturados da seguinte forma:
  
- `reuniao`: número da reunião
- `data`:  data da reunião da CPI no formato ano-mês-dia
- `nome`: Nome de quem fala no momento
- `funcao_blocoPar`: Qual a função (se presidente) ou bloco parlamentar, partido e Estado da federação. Esta foi repetida de modo desmembrado nas seguintes colunas:
  - `BlocoParl`: Apenas o bloco parlamentar
  - `partido`: Apenas o partido
  - `estado`: Estado da Federação do parlamentar
- `complemento`: alguns complementos, como "pela ordem", "fora do microfone", "como relator", "Para interpelar Por videoconferência", etc.
- `fala`: a fala da pessoa.

## Rds com todas as notas juntas
Criei um dataframe com as notas de todas as reuniões, o [NT_todas_df.rds](https://github.com/SoaresAlisson/NotasTaquigraficas/blob/master/rds/NT_todas_df.rds).
Há também o [NT_todas_normalizado.rds](https://github.com/SoaresAlisson/NotasTaquigraficas/blob/master/rds/NT_todas_normalizado.rds) que é basciamente o mesmo arquivo anterior, porém: 1) as colunas tem datatypes mais apropriados e não são apenas do tipo "char" 2) a coluna "nome", que no arquivo anterior continha nomes em caixa alta (caso dos senadores que estavam como presidentes), foi normalizada/padronizada. 3) "Eduardo Pazuello" e "Gen. Eduardo Pazuello", que apareciam em ambas as formas, foram unificadas.

## Rodando o script na sua máquina 
- O script R pega a lista com as Notas Táquigráficas na página do Senado da [CPI da Pandemia](https://legis.senado.leg.br/comissoes/comissao?codcol=2441) e atualiza a lista de notas taquigráficas, salva em `nt.lista` (que, apesar do nome, é um tibble/dataframe)
- A partir de `nt.lista` gerado, o script baixa e estrutura os arquivos das notas taquigráficas.
- Se parar o script, ele retoma onde parou. O critério de conferência é o arquivo .Rds existir e estar na pasta `rds`. 
  - Deste modo, é possível ir atualizando com as novas notas taquigráficas que forem surgindo.
  
**Veja o script neste link [aqui](https://htmlpreview.github.io/?https://raw.githubusercontent.com/SoaresAlisson/NotasTaquigraficas/master/NotasTaq_parser.html).**
