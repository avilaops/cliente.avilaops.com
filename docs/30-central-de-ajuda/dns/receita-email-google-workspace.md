---
titulo: "Configurar e-mail do Google Workspace"
area: dns
tipo: como-fazer
equivalente_hetzner: "Managed/Email/Email security (DKIM, SPF, DMARC)"
depende_de_tela: nao
atualizado_em: "16/09/2026"
---

# Configurar e-mail do Google Workspace

Registros que o domínio precisa para receber e enviar e-mail pelo Google
Workspace sem cair em spam.

> **Antes de começar:** o domínio precisa usar os servidores DNS da Ávila, e
> você precisa de acesso ao Google Admin. Confira os valores atuais no Google
> Admin: o Google pode mudá-los, e o que vale é o que ele mostra para a sua
> conta.

## Registros

| Nome | Tipo | Valor | Para quê |
|---|---|---|---|
| `@` | TXT | `google-site-verification=<código do Google Admin>` | provar que o domínio é seu |
| `@` | MX | prioridade `1`, valor `smtp.google.com.` | receber e-mail |
| `@` | TXT | `v=spf1 include:_spf.google.com ~all` | autorizar o Google a enviar |
| `google._domainkey` | TXT | `v=DKIM1; k=rsa; p=<chave gerada no Google Admin>` | assinar e-mails |
| `_dmarc` | TXT | `v=DMARC1; p=none; rua=mailto:<seu e-mail>` | política e relatórios |

## Ordem

1. Adicione o TXT de verificação e confirme no Google Admin.
2. **Apague MX antigos** do provedor anterior. MX antigo misturado com o novo
   faz parte dos e-mails ir para o lugar errado.
3. Adicione o MX.
4. Adicione o SPF. Se já existir um SPF (outro serviço envia e-mail pelo seu
   domínio), **junte num só**: `v=spf1 include:_spf.google.com include:<outro> ~all`.
5. No Google Admin, gere a chave DKIM, adicione o TXT e clique em
   **Iniciar autenticação**.
6. Adicione o DMARC com `p=none`. Depois de [2 a 4 semanas] de relatórios sem
   surpresa, suba para `p=quarantine`.

## Se der errado

| Sintoma | Causa provável |
|---|---|
| Google Admin diz que MX não foi encontrado | servidores DNS do domínio não são os da Ávila, ou cache (aguardar TTL) |
| E-mails enviados caem em spam | SPF duplicado, DKIM não ativado no Google Admin |
| Parte dos e-mails não chega | MX antigo ainda na zona |
