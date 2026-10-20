
# Triagem_PIX
Uma simples abordagem análitca de transações que utilizam PIX
# Triagem de Transações PIX por Valor

Projeto de estudo em Python que seleciona transações PIX acima de um limite configurável e apresenta um resumo para análise. Utiliza uma base fictícia com cinco transações, sem bibliotecas externas.

## Objetivo

Praticar fundamentos de Python em um contexto de Fraud Analytics: organizar dados, aplicar uma regra de triagem e calcular indicadores.

## Regra de triagem

Uma transação é selecionada quando atende às duas condições:

- O meio de pagamento é `PIX`.
- O valor é **maior** que a variável `limite`.

Na versão atual, `limite = 22000`. Valores iguais ao limite não são selecionados. TED e boleto não são selecionados por esta regra, mesmo quando ultrapassam o limite.

## Funcionalidades

- Exibição das transações selecionadas.
- Soma dos valores em atenção.
- Contagem de transações para análise.
- Percentual selecionado em relação a **todas as transações da lista**, incluindo outros meios de pagamento.
- Mensagem quando nenhuma transação atende ao filtro.

## Como executar

Com Python 3 instalado, coloque `triagem_pix.py` em uma pasta e execute no terminal dessa pasta:

```bash
python triagem_pix.py
```

Em ambientes que utilizam esse nome de comando, use `python3 triagem_pix.py`.

## Resultado do exemplo

Com os dados fornecidos e o limite de R$ 22.000, os PIX de IDs 152 (R$ 29.000) e 150 (R$ 25.000) são selecionados:

```text
{'id': 152, 'valor': 29000, 'meio': 'PIX'}
{'id': 150, 'valor': 25000, 'meio': 'PIX'}
Valor total em atenção: 54000
Transações em análise: 2
Percentual do total analisado: 40.0%
```

São 2 transações selecionadas entre 5 analisadas: **40%**, totalizando **R$ 54.000**.

## Conceitos praticados

- Lista de dicionários e acesso por chave.
- Laço `for` e condicionais `if`.
- Operadores de comparação e operador lógico `and`.
- Contador, acumulador e cálculo percentual.
- Variável para configuração da regra e saídas com f-strings.

## Escopo e limitações

Este é um exercício com dados fictícios. O limite foi definido para fins didáticos e não foi calibrado com dados reais. A seleção sinaliza transações para análise; não confirma fraude.

A versão atual pressupõe uma lista não vazia, registros completos e valores numéricos válidos. Uma lista vazia causa divisão por zero no cálculo do percentual. Não há integração bancária, leitura de arquivos ou classificação de fraude confirmada.

## Autor

[Lucas Freire Martins](https://github.com/lucasfrmg25-del)
