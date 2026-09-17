# SLA e Suporte

**Versão:** 0.1 (minuta) · **Vigência:** não publicada · **Responsável:** Nícolas Ávila

> **MINUTA.** Não pode ser publicada antes das decisões A2 (onde roda o DNS)
> e A6 (plantão). Prometer disponibilidade sem infraestrutura e sem plantão
> que a sustentem é pior que não ter SLA.

---

## 1. O que é coberto

| Serviço | Meta mensal | Como se mede |
|---|---|---|
| Resolução DNS nos servidores da Ávila | [100% / 99,99%] de pelo menos um servidor DNS respondendo | Sondas externas em [N] regiões, a cada [1] minuto |
| Painel account.avilaops.com | [99,5%] | Sonda HTTP na página de login e na API |
| Comandos ao registro/registrador | sem meta de disponibilidade | Dependem de terceiros |

**Não é coberto:** indisponibilidade do Registro.br, do registrador parceiro
ou de registros de extensão; manutenção avisada com [48 h]; erro de
configuração feito pelo cliente; DNS em servidores externos; ataque que exija
mitigação fora do controle da Ávila; suspensão pela Política de Uso Aceitável.

## 2. Compensação

| Disponibilidade DNS no mês | Crédito sobre a mensalidade de DNS/gestão daquele domínio |
|---|---|
| abaixo da meta até [99,9%] | [10%] |
| abaixo de [99,9%] até [99%] | [25%] |
| abaixo de [99%] | [50%] |

Crédito pedido em até [30] dias após o mês, pelo atendimento. Crédito não é
dinheiro de volta e não passa de [50%] do valor mensal.

## 3. Suporte

| Canal | Para quê | Horário |
|---|---|---|
| Central de ajuda | tudo que o cliente resolve sozinho | sempre |
| [e-mail de atendimento] / chat | dúvidas e problemas | [seg a sex, 9h às 18h, horário de Brasília] |
| [canal de urgência] | domínio ou DNS fora do ar | [a definir pela decisão A6] |
| Página de status | incidentes e manutenções | [status.avilaops.com, a definir] |

### Prioridade e prazo de primeira resposta

| Prioridade | Exemplo | Primeira resposta |
|---|---|---|
| P1 Crítica | DNS da Ávila fora do ar; domínio suspenso indevidamente | [1 h em horário comercial; fora dele, conforme A6] |
| P2 Alta | falha em renovação ou transferência | [4 h úteis] |
| P3 Normal | dúvida de configuração | [1 dia útil] |
| P4 Baixa | sugestão | [3 dias úteis] |

### Identificação no atendimento

Para qualquer ação sobre domínio ou conta, o suporte pede o **código de
atendimento** exibido no painel. Sem ele, o suporte só orienta, não executa.
A Ávila nunca pede senha, código de verificação em duas etapas ou código de
autorização de domínio.

---

## Histórico de revisão

| Versão | Data | Alteração | Responsável |
|---|---|---|---|
| 0.1 | 16/09/2026 | Minuta inicial | Nícolas Ávila |
