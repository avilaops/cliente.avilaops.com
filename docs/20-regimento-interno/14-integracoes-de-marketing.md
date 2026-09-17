# 14. Integrações de marketing: GA4, Google Ads e Mercado Livre Ads

**Estado:** minuta · **Atualizado em:** 16/09/2026 · **Cumpre:** D9, D10

Norma de configuração do GA4, válida para toda a casa:
[`docs/analytics/NORMA-GA4-CONTA-DO-CLIENTE.md`](../../../docs/analytics/NORMA-GA4-CONTA-DO-CLIENTE.md).
Este procedimento cobre o que é próprio do account.

## Objetivo

O cliente configura sozinho, pelo painel, Analytics e anúncios **na conta dele**. A equipe só entra em exceção e com a função mínima.

## Gatilho

- Cliente abre um assistente do módulo Marketing.
- Cliente contrata um plano com revisão ou gestão pela equipe.
- Falha de conexão, token revogado ou alerta de campanha.

## Responsável

| Situação | Quem |
|---|---|
| Assistente sem equipe | o próprio cliente |
| Revisão, instalação da tag fora da Ávila, eventos personalizados | Dev frontend |
| Google Ads e Mercado Livre Ads com gestão contratada | Tráfego pago |
| Token com falha repetida, pedido de remoção de acesso | Dono do serviço |

## Passos

1. **Antes de criar qualquer coisa**, confirmar no painel que a conta Google ou Mercado Livre conectada é da empresa do cliente, e não de funcionário ou da Ávila. Conta pessoal de funcionário gera um aviso, e o cliente confirma que quer seguir.
2. **Função da Ávila**: conceder só a função do plano, pela tabela da norma GA4. Mudar de plano muda a função no mesmo dia.
3. **Mercado Livre Ads**: a equipe não altera orçamento nem ROAS objetivo sem pedido registrado do cliente, mesmo com gestão contratada. Cada alteração leva valor antes, valor depois e motivo.
4. **Fim do contrato ou pedido do cliente**: no mesmo dia útil, remover a função da Ávila no GA4 e no Google Ads e revogar os tokens. Avisar o cliente por e-mail.
5. **Fluxo antigo (n8n)**: propriedade criada na conta da Ávila não é oferecida como self-service. Tratamento conforme decisão A13.

## Registro

- Trilha de auditoria (interno 08) para toda chamada que cria ou altera algo, com o identificador devolvido pela API.
- Ficha do cliente guarda: ID `G-`, número da propriedade, ID da conta Google Ads, `advertiser_id` do Mercado Livre, função concedida e data.

## Exceções

- Cliente sem conta Google da empresa: orientar a criar uma antes. Não usar conta da Ávila "por enquanto".
- Cliente pede que a Ávila seja administradora: só com pedido escrito anexado à ficha, e o cliente continua administrador.

## O que nunca fazer

- Pedir senha do Google ou do Mercado Livre.
- Criar propriedade, conta de anúncios ou campanha na conta da Ávila para cliente do self-service.
- Deixar a Ávila como única administradora de qualquer conta do cliente.
- Enviar dado pessoal (nome, e-mail, telefone, CPF) em parâmetro de evento do GA4.
- Guardar token de terceiro em planilha, chat, `.env.example` ou log.
