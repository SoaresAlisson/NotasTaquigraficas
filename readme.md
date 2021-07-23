# Notas Taquigráficas - CPI da Pandemia
Aqui você encontra notas taquigráficas da [CPI da Pandemia](https://legis.senado.leg.br/comissoes/comissao?codcol=2441) estruturadas em Rdata e csv, feita com um script em R (será disponibilizado em breve). 

Os arquivos estão separadas em três colunas: 
- Coluna 1: "Nomes", quem fala no momento
- Coluna 2: "cargo_função", qual o bloco parlamentar de quem fala, o partido e o estado da Federação. No caso do presidente, a coluna 1 fica como Presidente, e a coluna 2 mostra a pessoa/partido/Estado da federação, assim como está originalmente nas Notas Taquigráficas (a se pensar se compensa mudar as colunas, neste caso). No caso do depoente, esta coluna fica vazia.
- Coluna 3: "falas" o que foi dito por aquela pessoa

- [Aqui](https://www25.senado.leg.br/web/atividade/notas-taquigraficas/-/notas/r/9996) você encontra um exemplo de uma delas no site do Senado.
- A tabela com todos links para todos as reuniões (inclusive depoimentos) você encontra [aqui](https://github.com/SoaresAlisson/NotasTaquigraficas/blob/master/NotasTaq_listagem.csv).

## Plano para atualizações futuras (em breve)
- mais arquivos de notas taquigráficas
  -  separação destes em pastas diferentes. Todos csv ficarão em uma pasta, todos os Rdata, em outra.
- melhora do script em R para estruturar em Rdata e csv as notas taquigráficas do Senado, em especial da CPI da Pandemia.
  - Ex.: separação do bloco parlamentar em uma coluna, partido em outra e estado e demais informações em colunas diferentes.
- disponibilização do script em R.
