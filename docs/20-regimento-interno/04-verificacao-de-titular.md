# 04. Verificação de titular e dados

## Verificações automáticas (requisito)

| Verificação | Quando | Falha |
|---|---|---|
| CPF/CNPJ com dígito válido | cadastro do titular | bloqueia |
| CNPJ ativo na Receita | titular PJ, `.br` | bloqueia com mensagem [confirmar regra do Registro.br] |
| E-mail do titular confirmado | registro, transferência, alteração de dados ou e-mail devolvido, em genéricos | suspensão após 15 dias sem confirmação (ICANN, FONTES §3) |
| CPF/CNPJ na Receita e endereço brasileiro | `.br` (também exigido pelo OpenSRS) | registro recusado |
| Sinais de fraude (externo 08 §5) | registro, primeira compra | fila de revisão, nada cobrado |

## Revisão humana de fraude

1. Abrir caso na fila **Revisão de fraude**.
2. Conferir: nome imita marca? dados do titular batem com o pagador? histórico
   da conta?
3. Decidir em até [1 dia útil]: liberar, pedir documento ou recusar.
4. Recusa: nada é cobrado; mensagem ao cliente sem expor o critério usado.

## Denúncia de dado falso

1. Recebida pelo canal de abuso (procedimento 05).
2. Pedir correção ao titular com prazo de [5] dias úteis.
3. Sem correção: suspender alterações e comunicar ao registro/registrador
   conforme regra de cada um.

## Nunca

- Cadastrar titular com dados da Ávila ou de funcionário.
- Aceitar documento por WhatsApp pessoal. Documento entra pelo painel ou
  pelo e-mail de atendimento, e fica anexado ao caso.
