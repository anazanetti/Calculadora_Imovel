# Módulo 1 - Santander Coders

**Alunos**

_Ana Cristina Zanetti_

_Mauro Domingues Junior_


# Calculadora Compra vs Aluguel

A calculadora tem o objetivo de, ao final de um período, apresentar o que é mais rentável: **comprar** ou **alugar** um imóvel.
<br><br><br>

## Preparação do Ambiente (Windows)

Instale o servidor web *ASGI*, **Uvicorn**:
```sh
$ pip install uvicorn
```
No mesmo diretório da aplicação ***calc_imovel_api***, execute o seguinte comando em seu terminal para iniciar o servidor local:
```sh
$ uvicorn calc_imovel_api:app --reload
```
<br>

## Acessando a aplicação via API

A URL seguirá um padrão (mesma ordem de parâmetros). O que varia é o método a ser requisitado:
*http://localhost:8000/{metodo}/{aluguel}/{valor_imovel}/{taxa_valorizacao_imovel}/{taxa_reajuste_aluguel}/{taxa_juros_aplicacao}/{anos}*
<br><br>
onde:

* ***metodo:*** Método a ser requisitado:
  * calculo
  * resumo
  * grafico
  * exporta
* ***demais parâmetros:*** 
  * ***valor_imovel:*** Valor de compra do imóvel
  * ***taxa_valorizacao_imovel:*** Juros de valorização do imóvel (a.a.)
  * ***taxa_reajuste_aluguel:*** Taxa de juros do aluguel (a.a.)
  * ***taxa_juros_aplicacao:*** Taxa de juros da aplicação (a.a.)
  * ***anos:*** Quantidade de anos a ser analisado

<br>

>***Obs.:*** <br>
>*O valor de compra do imóvel é o mesmo valor que será aplicado no investimento a ser analisado.* <br>
>*As taxas são em %, portanto, não é necessário fazer a conversão.*

<br>

## Métodos

### calculo ##

Retorna um dicionário contendo (mês a mês):
  * Mês:
    * Montante da aplicação (valor investido + rendimentos - aluguéis)
    * Valor do imóvel valorizado
    * Turnover: *"SIM"* ou *"NAO"*

### resumo

Retorna uma string contendo:
  * Análise da melhor escolha:
    * Quantidade de anos
    * O valor total da Aplicação
    * O valor total do Imóvel
    * A opção mais vantajosa
  * Análise de turnover:
    * Mês de turnover
    * Valor da aplicação
    * Valor do imóvel
    * Diferença 

### grafico

Apresenta um gráfico comparativo entre a Aplicação e a Valorização do Imóvel

### exporta

Exporta o arquivo dados.json contendo os resultados mês a mês:
  * Mês:
    * Montante da aplicação (valor investido + rendimentos - aluguéis)
    * Valor do imóvel valorizado
    * Turnover: *"SIM"* ou *"NAO"*


## Acessando a aplicação via Terminal

Dentro do diretório do Python rodar o programa calc_imovel_terminal.py. Inserir as entradas conforme solicitadas.
Todos os resultados acima mencionados nas rotas da API serão apresentados.

## Notebook

Também disponibilizado o programa em notebook
