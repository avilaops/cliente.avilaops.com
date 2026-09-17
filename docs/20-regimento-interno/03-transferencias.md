# 03. Transferências de entrada e saída

## Entrada

**Gatilho:** cliente pede transferência pelo painel.

Automático (requisito):
1. Conferir se o domínio não está travado ou dentro do prazo de trava.
2. Cobrar.
3. Enviar pedido com o código de autorização (genéricos) ou iniciar mudança de
   provedor (`.br`).
4. Oferecer importação da zona **antes** de trocar servidores DNS.
5. Acompanhar estado até concluir ou falhar; falha → reembolso automático.

Operação humana, só em exceção:
- pedido parado por mais de [7] dias → contato com cliente para verificar
  e-mail de confirmação do provedor antigo;
- recusa pelo provedor antigo → explicar motivo ao cliente, reembolsar.

**Nunca:** trocar os servidores DNS de um domínio que está chegando sem a zona
ter sido recriada. É a forma mais comum de derrubar e-mail na migração.

## Saída

**Gatilho:** titular gera código de autorização ou pede mudança de provedor.

1. Sistema exige verificação em duas etapas e avisa o e-mail do titular.
2. Código entregue na hora, no painel.
3. Retenção só nos casos do externo 02 §6.2 (disputa, ordem, fraude em
   análise). Retenção exige caso aberto, aprovação do Dono do serviço e aviso ao
   titular com motivo **no mesmo dia**.
4. Ao concluir, zona fica disponível 30 dias e é apagada por rotina.

**Nunca:** dificultar saída por débito de outro serviço, pedir motivo para
liberar, ou atrasar entrega do código.

**Limites da ICANN (FONTES §2), mesmo em exceção:** sem autoatendimento, o
código precisa sair em até 5 dias corridos. É **proibido** negar por falta de
pagamento de período futuro, por falta de resposta do titular ou por trava
que o titular não tem como desligar. É **obrigatório** negar com UDRP, URS ou
processo judicial pendente.

## `.br` com a Ávila como provedor

A saída não depende de código: o titular escolhe o novo provedor na interface
do Registro.br. O sistema recebe o aviso por mensagem EPP e deve: registrar o
evento, avisar o titular e agendar a exclusão da zona em 30 dias.
