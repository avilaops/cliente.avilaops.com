# 02. Renovação e régua de vencimento

**Objetivo:** nenhum domínio de cliente vence por falha nossa.

Motivo, nas palavras do levantamento comercial: hoje um domínio que vence
derruba site e e-mail do cliente no mesmo minuto, e a proteção é auditoria
diária e boa vontade.

## Rotina automática (requisito para o sistema)

| Quando | Sistema faz | Se falhar |
|---|---|---|
| diariamente | lista domínios vencendo na janela `produto.renovacao.janelaMonitoramentoDias` [60]; confere data no registro (não confiar só no banco) | alerta interno |
| D-30 | aviso ao cliente; primeira tentativa de cobrança se renovação automática | nova tentativa em D-15 |
| D-15, D-7, D-3 | nova tentativa + aviso | aviso por [WhatsApp/SMS] a partir de D-7 |
| após pagamento | envia renovação ao registro; confirma nova data lendo o registro | alerta interno P2 |
| D-1 sem pagamento | aviso final | caso aberto para Operação |
| D+1 a D+5 | aviso pós-vencimento (ERRP) | |
| diariamente | confere saldo no registrador contra renovações dos próximos 7 dias | alerta P1 se insuficiente |

## Operação humana

1. Todo dia útil, abrir a fila **Renovações com problema**.
2. Para cada item:
   - pagamento feito e renovação não confirmada → reenviar e confirmar no
     registro;
   - pagamento não feito → contato direto com o responsável da conta;
   - cliente sem resposta em D-3 → registrar tentativa. **Não renovar com
     dinheiro da Ávila sem autorização escrita do Dono do serviço**, caso a caso.
3. Registrar no caso cada contato feito.

Os dias da régua (D-30, D-15...) são política da Ávila, não regra externa:
vêm de `produto.renovacao.*` em `40-produto/POLITICAS-E-PARAMETROS.md`. O
aviso pós-vencimento em até 5 dias é regra da ICANN (`icann.errp.*`).

## Depois do vencimento

### `.br` (FONTES §5.1)

| Etapa | Sistema faz | Operação humana |
|---|---|---|
| Expiração e suspensão | marca o domínio como "expirado, reservado ao titular"; aviso D+1 | contato direto com o responsável da conta |
| Reserva ao titular (até `nicbr.expiracao.reservaTitularDias` [90]) | aviso semanal ao titular; mostra no painel quantos dias restam **da reserva**, nunca "data em que fica livre" | a partir da metade da reserva, contato por telefone registrado no caso |
| Fim da reserva | lê o estado no Registro.br; se removido, marca "removido" e encerra cobrança | informar o titular que a Ávila não recupera domínio removido |
| Processo de Liberação | nada; não é mais domínio do cliente | se o cliente quiser disputar o nome na liberação, orientar para o Registro.br |

PENDENTE DE CONFIRMAÇÃO: como reativar durante a reserva quando a Ávila é o
Provedor de Serviços (comando EPP ou interface do Registro.br) e se há custo
extra. Até confirmar, reativação é caso manual para Operação.

### Genéricos (FONTES §1)

| Etapa | Sistema faz |
|---|---|
| Vencimento até exclusão | permite renovar; aviso em até 5 dias; interrupção de DNS pelo registrador |
| Resgate (`icann.errp.resgateDias` [30]) | oferece resgate com a taxa da página de preços |
| Liberado | marca "liberado", encerra cobrança |

## Nunca

- Desligar renovação automática de cliente sem pedido dele.
- Renovar domínio de cliente em outra conta de registrador "para resolver rápido".
- Considerar renovado sem ler a nova data no registro.
