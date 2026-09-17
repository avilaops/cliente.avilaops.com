# 01. Papéis e responsabilidades

Hoje a equipe é o Nicolas. A tabela separa os **papéis** para que, quando
entrar mais gente, se saiba o que entregar, e para deixar visível o que hoje
depende de uma pessoa só.

| Papel | Responde por | Hoje | Substituto |
|---|---|---|---|
| **Dono do serviço** | decisões, contratos com Registro.br e registrador, aprovação de regimento | Nicolas | [nenhum: risco] |
| **Operação de domínios** | exceções de renovação, transferência, verificação | Nicolas | [a definir] |
| **Abuso** | ler a caixa de abuso todo dia útil, decidir ação | Nicolas | [a definir] |
| **Plantão** | incidente P1 fora do horário | [não existe, decisão A6] | |
| **Financeiro** | saldo no registrador, conciliação, reembolso | Nicolas | [contador para nota] |
| **Encarregado de dados (LGPD)** | pedidos de titular de dados, incidentes | Nicolas | |
| **Desenvolvimento** | painel, integrações, DNS | [Antigravity / Codex, ver `docs/CONTEXTO-NOVAS-SESSOES.md`] | |

## Matriz de ações sensíveis

| Ação | Quem pode executar | Quem aprova | Evidência |
|---|---|---|---|
| Alterar DNS de cliente pela equipe | Operação | titular (código de atendimento) | trilha de auditoria + chamado |
| Suspender DNS por abuso grave | Abuso | Dono do serviço, em até [24 h] depois | caso de abuso |
| Reter transferência de saída | Operação | Dono do serviço | caso + aviso ao titular |
| Liberar acesso a quem perdeu a conta | Operação | Dono do serviço | documento + espera de 72 h |
| Reembolso fora da tabela | Financeiro | Dono do serviço | registro financeiro |
| Cumprir ordem judicial | Dono do serviço | [advogado] | ofício arquivado |

## Regra

Nenhuma ação sensível é feita direto no banco ou no painel do registrador.
Passa pelo painel interno, que grava a trilha. Se o painel interno não tiver o
botão, abrir tarefa de desenvolvimento e registrar a execução manual no caso.
