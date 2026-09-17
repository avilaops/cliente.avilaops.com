# 07. Saldo no registrador e conciliação

> **Bloqueado pelas decisões A1 e A4.** Se o registrador exigir depósito
> antecipado, é caixa preso antes da venda (levantamento comercial, §4).

## O que já se sabe (FONTES §4 e §6)

- **OpenSRS:** pré-pago, só em dólar; cartão com 3% de taxa; crédito não é
  reembolsável. Todo depósito é exposição cambial e caixa preso sem volta.
- **Registro.br:** renovação por EPP falha com "crédito insuficiente".
  Forma de carga do crédito [perguntar ao Registro.br].

## Regras

1. Saldo mínimo no registrador = soma das renovações dos próximos [30] dias
   + [margem de 20%].
2. Alerta P1 quando o saldo cobrir menos de [7] dias.
3. Dinheiro de cliente recebido para domínio não é usado para outra despesa
   antes de o comando ser executado.
4. Como o crédito do OpenSRS não volta, depositar em lotes de [1 mês] de
   renovações previstas, nunca "para garantir o ano".
5. Preço de genérico cobrado em real embute margem cambial de [x%], revisada
   todo mês contra o dólar do dia do depósito.

## Conciliação mensal

| Conferir | Contra |
|---|---|
| Domínios cobrados no mês | Comandos executados no registro/registrador |
| Débitos do registrador | Comandos executados |
| Reembolsos | Falhas de comando |
| Taxa de câmbio aplicada (genéricos) | Preço cobrado |

Divergência vira caso para o Financeiro, com prazo de [5] dias úteis.

## Nota fiscal

[confirmar com contador: se o serviço é faturado como intermediação, com o
valor do domínio repassado, ou como serviço cheio; impacto no limite do MEI
(decisão A3).]
