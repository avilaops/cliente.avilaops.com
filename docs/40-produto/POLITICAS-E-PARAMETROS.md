# Políticas e parâmetros

**Estado:** minuta de desenho · **Atualizado em:** 16/09/2026

> Todo prazo, limite ou lista que o account usa para decidir algo sobre
> domínio vive **aqui**, com dono e fonte. Tela, e-mail, rotina e central de
> ajuda leem o parâmetro; ninguém escreve `60`, `90` ou `30` solto no código.
>
> Os nomes de chave são **conceituais**. Ainda não há código; quando houver,
> adaptar à arquitetura escolhida sem perder as três camadas nem o histórico.

## 1. Três camadas

| Camada | Quem define | Exemplo | Quem pode mudar | Exige |
|---|---|---|---|---|
| **Regra externa** | ICANN, NIC.br/Registro.br | trava de 60 dias após troca de titular; reserva de 90 dias do `.br` | ninguém na Ávila decide; só **registra** mudança da entidade | ID de fonte OFICIAL em `00-fundacao/FONTES-REGRAS-DE-TERCEIROS.md` e data de vigência |
| **Regra do fornecedor** | registrador parceiro, gateway | pedido `.com.br` no OpenSRS expira em 14 dias | idem | fonte do fornecedor e data |
| **Política do produto** | Ávila | avisar 30, 7 e 1 dia antes; não reter transferência por débito | Dono do serviço | decisão registrada e, se afeta cliente, nova versão do regimento externo |

**Regra de composição:** a política do produto pode ser **mais protetora ao
cliente** que a regra externa, nunca menos. Exemplo: a ICANN permite negar
transferência por débito do período corrente; a Ávila escolheu não negar.

## 2. Formato de um parâmetro

```text
chave               icann.transfer.travaAposTrocaTitularDias
camada              regra-externa | regra-fornecedor | politica-produto
escopo              global | extensão (.br, .com...) | registrador (opensrs...)
valor               60
unidade             dias corridos | dias úteis | horas | lista | booleano
estado              vigente | pendente-de-confirmacao | monitorada
fonte               F2, F3
vigenteDesde        21/08/2025
revisarEm           16/12/2026
dono                Dono do serviço
usadoEm             contrato 02 §4 e §6; ajuda trava-de-transferencia; rotina de transferência
historico           [valores anteriores com vigenteDesde e vigenteAte]
```

Regras do formato:

1. **Histórico com vigência, nunca sobrescrever.** Uma mudança da ICANN entra
   como nova versão com `vigenteDesde` futuro. O sistema aplica a versão
   vigente **na data do evento** (data da troca de titular, do vencimento),
   não na data de hoje.
2. **`pendente-de-confirmacao` não decide nada.** O sistema não bloqueia nem
   libera com base nele; manda o caso para operação humana.
3. **`monitorada` não é lida pelo sistema.** Serve para lembrar de revisar.
4. **Escopo mais específico vence:** registrador > extensão > global.
5. **Texto público lê o parâmetro.** Página de ajuda e contrato publicados a
   partir de modelo com o valor vigente, para não haver "60" no texto e "30"
   no código.
6. **Validação ao salvar:** política do produto que contrarie regra externa é
   recusada (ver §5).

## 3. Regras externas

### ICANN (genéricos)

| Chave | Valor vigente | Estado | Fonte |
|---|---|---|---|
| `icann.errp.aviso1JanelaDias` | 26 a 35 antes | vigente | F1 |
| `icann.errp.aviso2JanelaDias` | 4 a 10 antes | vigente | F1 |
| `icann.errp.avisoPosVencimentoMaxDias` | 5 | vigente | F1 |
| `icann.errp.interrupcaoDnsMinDias` | 8 | vigente | F1 |
| `icann.errp.resgateDias` | 30 | vigente | F1 |
| `icann.errp.exibirPrecosNoRevendedor` | sim | vigente | F1 |
| `icann.transfer.travaAposCriacaoDias` | 60 | vigente; revisão monitorada | F2, F3, F20 |
| `icann.transfer.travaAposTransferenciaDias` | 60 | vigente; revisão monitorada | F2, F3, F20 |
| `icann.transfer.travaAposTrocaTitularDias` | 60 | vigente; revisão monitorada | F2, F3, F20 |
| `icann.transfer.codigoAutorizacaoMaxDias` | 5 corridos | vigente | F2 |
| `icann.verificacaoContato.prazoDias` | 15 | vigente | F4, F5 |
| `icann.udrp.esperaCumprimentoDiasUteis` | 10 | vigente | F22 |

### NIC.br / Registro.br (`.br`)

| Chave | Valor vigente | Estado | Fonte |
|---|---|---|---|
| `nicbr.expiracao.reservaTitularDias` | até 90 | vigente | F10 |
| `nicbr.expiracao.reativacao` | — | **pendente-de-confirmacao** | — |
| `nicbr.liberacao.ciclos` | datas publicadas pelo Registro.br | consulta, não valor fixo | F11 |
| `nicbr.epp.renovacaoAnos` | 1 a 10 | vigente | F9 |
| `nicbr.epp.servidoresDns` | 2 a 5 | vigente | F9 |
| `nicbr.epp.dsMax` | 2 | vigente | F9 |
| `nicbr.epp.ipsPorServidorDns` | 1 IPv4 e 1 IPv6 | vigente | F9 |
| `nicbr.epp.remocao` | até 5 dias após criação, até 3% dos últimos 5 dias | vigente | F9 |
| `nicbr.epp.contatoNome` | mínimo 2 palavras, até 40 caracteres | vigente | F9 |
| `nicbr.epp.nomeProvedor` | 1 palavra, até 25 caracteres, imutável | vigente | F6 |
| `nicbr.epp.ipsAutorizados` | até 4 endereços ou blocos /26 | vigente | F6 |
| `nicbr.saciAdm.instituicoes` | ABPI; OMPI/WIPO (lista de 05/2026) | vigente; **revisar antes de exibir** | F13, F14 |
| `nicbr.saciAdm.duracaoMediaDias` | aproximadamente 74 (outro dado do NIC.br: cerca de 80, fonte a anexar) | informativo, nunca prazo | F13 |
| `nicbr.saciAdm.prazoAcaoJudicialDiasUteis` | 15 | vigente | F13 |
| `nicbr.saciAdm.prazoEsclarecimentoDias` | 5 | vigente | F13 |

## 4. Regras de fornecedor

Só valem se o fornecedor for escolhido (A1, A4).

| Chave | Valor | Estado | Fonte |
|---|---|---|---|
| `registrador.opensrs.dispensaTravaTrocaTitular` | — | **pendente-de-confirmacao** (contrato não lido) | — |
| `registrador.opensrs.br.pedidoExpiraDias` | 14 (DNS não validado) | vigente se escolhido | F17 |
| `registrador.opensrs.br.transferenciaEntrada` | não suportada | vigente se escolhido | F17 |
| `registrador.opensrs.saldo.moeda` | USD, pré-pago | vigente se escolhido | F16 |
| `registrador.opensrs.saldo.taxaCartaoPercentual` | 3 | vigente se escolhido | F16 |

## 5. Políticas do produto

| Chave | Valor proposto | Não pode contrariar | Onde está escrito |
|---|---|---|---|
| `produto.renovacao.automaticaPadrao` | ligada | — | externo 02 §5.1 |
| `produto.renovacao.tentativasDiasAntes` | [30, 15, 7, 3, 1] | — | externo 06 §2 |
| `produto.avisos.diasAntes` | [30, 7, 1] | deve ter um valor dentro de `icann.errp.aviso1JanelaDias` e outro dentro de `aviso2JanelaDias` | externo 02 §5.2 |
| `produto.avisos.diasDepois` | [1, 5] | máximo `icann.errp.avisoPosVencimentoMaxDias` | externo 02 §5.2 |
| `produto.avisos.brReservaFrequencia` | semanal | — | interno 02 |
| `produto.renovacao.janelaMonitoramentoDias` | 60 | — | interno 02 |
| `produto.transferencia.travaPadraoLigada` | sim | — | ajuda trava-de-transferencia |
| `produto.transferencia.reterPorDebito` | **não** | mais protetora que F2 | externo 02 §6.2 |
| `produto.transferencia.codigoAutorizacao` | imediato, no painel | máximo `icann.transfer.codigoAutorizacaoMaxDias` | externo 02 §6.2 |
| `produto.transferencia.zonaAposSaidaDias` | 30 | — | externo 02 §6.2, 04 §4 |
| `produto.recuperacaoConta.esperaHoras` | 72 | — | interno 11 |
| `produto.recuperacaoConta.travaTransferenciaDias` | 7 | — | interno 11, ajuda perdi-acesso |
| `produto.inadimplencia.bloqueioNovasComprasDias` | 15 | nunca bloquear renovação paga, DNS ou saída | externo 06 §7 |
| `produto.precos.avisoReajusteDias` | 30 | — | externo 02 §9, 06 §3 |
| `produto.saldoRegistrador.coberturaDias` | 30 + 20% | — | interno 07 |
| `produto.saldoRegistrador.alertaDias` | 7 | — | interno 07 |
| `produto.dns.versoesRetencaoDias` | 90 | — | interno 13 |

Valores entre colchetes nas minutas externas correspondem a estas chaves.

## 6. Como uma mudança externa entra

Exemplo: a ICANN publica a nova Transfer Policy com vigência definida.

1. Atualizar FONTES §2 e mover o item de §11 (monitorada) para vigente, com ID
   de fonte OFICIAL.
2. Criar nova versão de `icann.transfer.*` com `vigenteDesde` da ICANN.
   **Não apagar** a versão de 60 dias: eventos anteriores continuam usando-a.
3. Confirmar com o registrador parceiro a data em que ele aplica.
4. Revisar a coluna `usadoEm` e gerar nova versão do contrato 02 e das páginas
   da ajuda a partir dos parâmetros.
5. Registrar no histórico do contrato e avisar clientes se a mudança afetar
   algo em andamento.

Nenhum passo exige procurar números espalhados em telas ou rotinas.

## 7. O que ainda não vira parâmetro

| Item | Por quê |
|---|---|
| Reativação de `.br` durante a reserva | sem fonte oficial (PENDENTE DE CONFIRMAÇÃO) |
| Dispensa da trava de troca de titular | depende do contrato do registrador (A1) |
| Metas de SLA e nomes dos servidores DNS | dependem de A2 |
| Formas de pagamento e prazos de reembolso | dependem de A4 |
