# 06. Plantão e incidentes

> **Bloqueado pela decisão A6.** O levantamento comercial registra: "Suporte
> vira plantão. Domínio caindo é urgência de verdade, inclusive fora do
> horário. Hoje a casa não tem plantão."

## Classificação

| Nível | Exemplo |
|---|---|
| P1 | DNS da Ávila sem resposta; domínios de clientes suspensos em massa; painel invadido; vazamento |
| P2 | Renovações ou transferências falhando; painel fora do ar com DNS funcionando |
| P3 | Falha parcial sem impacto de disponibilidade |

## Durante um incidente

1. Abrir registro do incidente com hora de início.
2. Atualizar a página de status em até [15 min] para P1.
3. Conter antes de investigar.
4. Comunicar clientes afetados em até **24 h** da confirmação, mesmo sem causa
   raiz (regra da casa, `docs/parcerias/openai/02-politica-seguranca-ia.md` §8).
5. Se envolver dado pessoal: avaliar comunicação à ANPD com advogado.

## Depois

Registro com: data, descrição, causa raiz, impacto (domínios e contas),
ação tomada, ação preventiva, crédito de SLA devido. Todo incidente gera
revisão do regimento, mesmo que conclua "nenhuma mudança".

## Para decidir (A6)

- Existe plantão? Com quem? Remunerado como?
- Se não existe: o SLA público precisa dizer que fora do horário não há
  atendimento humano, e a arquitetura de DNS precisa aguentar sozinha.
