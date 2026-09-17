---
titulo: "Ciclo de vida de um domínio"
area: dominios
tipo: conceitos
equivalente_hetzner: "Robot/Domain Registration Robot/ERRP"
depende_de_tela: nao
atualizado_em: "16/09/2026"
---

# Ciclo de vida de um domínio

> **Rascunho.** Regras com fonte em `00-fundacao/FONTES-REGRAS-DE-TERCEIROS.md`
> (§1 genéricos, §5.1 `.br`). Prazos vêm de `40-produto/POLITICAS-E-PARAMETROS.md`.
> Não publicar com colchetes.

`.br` e genéricos seguem caminhos diferentes depois do vencimento.

```text
.br        ativo ─► expiração ─► suspenso, reservado ao titular (até 90 dias) ─► removido ─► Processo de Liberação
                         ▲                         │
                         └──────── renovação ──────┘

genéricos  ativo ─► vencimento ─► renovável, DNS interrompido ─► excluído ─► resgate (30 dias) ─► liberado
                         ▲                   │                                   │
                         └──── renovação ────┘◄──────────── resgate com taxa ────┘
```

## 1. Ativo

Período pago, normalmente 1 ano. Com renovação automática ligada, a Ávila
tenta cobrar a partir de **[30] dias antes** do vencimento e avisa você por
e-mail em cada tentativa.

## 2. Depois do vencimento: `.br`

| Etapa | O que acontece |
|---|---|
| **Expiração** | a renovação não foi paga até a data de vencimento |
| **Suspensão** | o domínio deixa de funcionar: site e e-mail saem do ar |
| **Reserva ao titular** | por até **90 dias** o domínio continua em seu nome e **ninguém mais pode registrá-lo** |
| **Remoção** | ao fim desse período, o Registro.br pode remover o domínio |
| **Processo de Liberação** | só depois da remoção, e nos ciclos definidos pelo Registro.br, o nome pode ser oferecido a outras pessoas |

**Não existe data garantida em que o nome fica livre.** Remoção e liberação
são etapas diferentes, e a segunda depende do calendário do Registro.br.

[como e com que custo reativar durante os 90 dias: PENDENTE DE CONFIRMAÇÃO]

## 3. Depois do vencimento: genéricos

| Etapa | O que acontece |
|---|---|
| **Vencimento** | você ainda pode renovar |
| **Interrupção de DNS** | pelo menos nos últimos 8 dias em que a renovação é possível, o DNS é desligado e o endereço pode mostrar uma página avisando do vencimento |
| **Exclusão** | fim do prazo de renovação [prazo total: conforme registrador parceiro] |
| **Resgate** | **30 dias** em que o registro guarda o domínio excluído, sem DNS e sem transferência. Voltar custa a taxa de resgate da página de preços |
| **Liberado** | qualquer pessoa pode registrar |

Renovar antes da exclusão devolve tudo ao normal. O preço pode ser o de
renovação após vencimento, mostrado na página de preços.

## 4. Quando não tem volta

Domínio removido (`.br`) ou liberado depois do resgate (genéricos) **não pode
ser recuperado pela Ávila**.

## Avisos que você recebe

| Quando | Canal |
|---|---|
| [30] dias antes | e-mail |
| [7] dias antes | e-mail e [WhatsApp/SMS] |
| [1] dia antes | e-mail e [WhatsApp/SMS] |
| até 5 dias depois | e-mail |

Mantenha o e-mail da conta funcionando: é o único canal garantido.
