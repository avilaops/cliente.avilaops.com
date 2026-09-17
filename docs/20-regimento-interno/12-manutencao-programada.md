# 12. Manutenção programada

**Objetivo:** manutenção não conta como indisponibilidade no SLA **só** se
avisada como o externo 05 exige.

## Antes

| Quando | Ação |
|---|---|
| ao decidir | registrar: o que muda, janela, impacto esperado, plano de volta |
| [48 h] antes | aviso na página de status e e-mail aos clientes afetados |
| 1 h antes | conferir backup das zonas e do banco (procedimento 13) |

**Janela padrão:** [terça a quinta, 0h às 5h, horário de Brasília]. Nunca
perto de fim de mês, quando se concentram renovações.

## Regras

- **Nunca** derrubar todos os servidores DNS ao mesmo tempo. Um por vez,
  conferindo resposta externa antes de passar ao próximo.
- Mudança no motor de DNS é testada antes com um domínio da Ávila.
- Comandos ao Registro.br e registrador ficam em fila durante a janela, não
  são descartados.

## Depois

1. Conferir sondas externas de DNS e painel.
2. Fechar aviso na página de status.
3. Se passou da janela ou teve impacto não previsto: tratar como incidente
   (procedimento 06).
