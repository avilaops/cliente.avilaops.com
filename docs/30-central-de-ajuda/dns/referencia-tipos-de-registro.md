---
titulo: "Tipos de registro DNS"
area: dns
tipo: referencia
equivalente_hetzner: "Network & Security/DNS/Record types (uma página por tipo)"
depende_de_tela: nao
atualizado_em: "16/09/2026"
---

# Tipos de registro DNS

> A Hetzner usa uma página por tipo. Aqui começa em uma página com âncoras;
> separar quando cada seção ganhar exemplos de tela.

Em todos os exemplos o domínio é `exemplo.com.br` e os endereços são de
documentação (não existem de verdade).

## Qual usar

| Quero | Tipo |
|---|---|
| Apontar para um endereço IPv4 | [A](#a) |
| Apontar para um endereço IPv6 | [AAAA](#aaaa) |
| Apontar um subdomínio para outro nome | [CNAME](#cname) |
| Receber e-mail | [MX](#mx) |
| Verificar domínio, SPF, DKIM, DMARC | [TXT](#txt) |
| Delegar um subdomínio | [NS](#ns) |
| Anunciar um serviço com porta (SIP, XMPP) | [SRV](#srv) |
| Limitar quem emite certificado SSL | [CAA](#caa) |
| Ligar DNSSEC de uma subzona | [DS](#ds) |
| Anunciar HTTP/3 e alias no apex | [HTTPS / SVCB](#https-e-svcb) |
| Fixar certificado para e-mail (DANE) | [TLSA](#tlsa) |
| DNS reverso | [PTR](#ptr) |

## A

Nome → endereço IPv4.

| Nome | Tipo | Valor | TTL |
|---|---|---|---|
| `@` | A | `203.0.113.10` | 3600 |
| `www` | A | `203.0.113.10` | 3600 |

Pode haver vários A no mesmo nome; o resolvedor recebe todos.

## AAAA

Nome → endereço IPv6. Mesma lógica do A.

| `@` | AAAA | `2001:db8::10` | 3600 |
|---|---|---|---|

## CNAME

Nome → outro nome. O resolvedor segue o destino.

| `loja` | CNAME | `lojas.avilaops.com.` | 3600 |
|---|---|---|---|

Regras que causam erro:

- **Não pode existir no `@`** (o próprio domínio), porque o apex precisa de SOA
  e NS. Para o apex, use A/AAAA ou HTTPS.
- **Não pode dividir o nome** com outro registro. `loja` com CNAME não pode ter
  também TXT ou MX.
- O valor é um nome, não um endereço, e não pode ter `https://`.

## MX

Para onde vão os e-mails do domínio. Menor prioridade = tentado primeiro.

| Nome | Tipo | Prioridade | Valor |
|---|---|---|---|
| `@` | MX | 10 | `mx1.provedor.exemplo.` |
| `@` | MX | 20 | `mx2.provedor.exemplo.` |

O valor precisa ser um nome com registro A/AAAA, nunca um CNAME nem um IP.
Receita pronta: [e-mail com Google Workspace](receita-email-google-workspace.md).

## TXT

Texto livre, usado por verificações e políticas de e-mail.

| Nome | Tipo | Valor | Uso |
|---|---|---|---|
| `@` | TXT | `v=spf1 include:_spf.google.com ~all` | SPF |
| `google._domainkey` | TXT | `v=DKIM1; k=rsa; p=MIIB...` | DKIM |
| `_dmarc` | TXT | `v=DMARC1; p=none; rua=mailto:dmarc@exemplo.com.br` | DMARC |
| `@` | TXT | `google-site-verification=...` | verificação |

- Só **um** SPF por nome. Dois SPF invalidam os dois.
- Valores com mais de 255 caracteres são divididos em partes automaticamente
  pelo painel [confirmar comportamento].

## NS

Quais servidores respondem por um nome.

- No `@`: criados pela Ávila, não editáveis enquanto a zona usa os servidores da
  Ávila. Para trocar os servidores do domínio inteiro, altere a **delegação**
  em **Domínios → Servidores DNS**, não a zona.
- Em subdomínio: delega aquele subdomínio para outros servidores.

| `lab` | NS | `ns1.outroprovedor.exemplo.` |
|---|---|---|

## SRV

Serviço, protocolo, prioridade, peso, porta e destino.

| Nome | Tipo | Prioridade | Peso | Porta | Destino |
|---|---|---|---|---|---|
| `_sip._tcp` | SRV | 10 | 60 | 5060 | `sip.exemplo.com.br.` |

## CAA

Quais autoridades podem emitir certificado SSL para o domínio.

| Nome | Tipo | Flag | Tag | Valor |
|---|---|---|---|---|
| `@` | CAA | 0 | issue | `letsencrypt.org` |
| `@` | CAA | 0 | iodef | `mailto:seguranca@exemplo.com.br` |

Criar CAA sem incluir a autoridade usada pelo seu site **impede a renovação do
certificado**.

## DS

Liga a cadeia de confiança DNSSEC de uma subzona delegada. Para o domínio
principal, o DS é publicado no **registro da extensão**, pela tela de DNSSEC
do domínio, não na zona.

DS errado ou esquecido depois de trocar de provedor deixa o domínio **fora do
ar** para resolvedores que validam DNSSEC.

## HTTPS e SVCB

Informam protocolos suportados (HTTP/2, HTTP/3), portas e alternativas, e
permitem apontar o apex para outro nome.

| Nome | Tipo | Prioridade | Destino | Parâmetros |
|---|---|---|---|---|
| `@` | HTTPS | 1 | `.` | `alpn="h2,h3"` |

Prioridade `0` é modo alias (apontar para outro nome). SVCB é o mesmo formato
para serviços que não são HTTPS.

## TLSA

Associa um certificado a um serviço e porta (DANE), usado principalmente por
servidores de e-mail. **Exige DNSSEC ativo.**

| `_25._tcp.mail` | TLSA | `3 1 1 <hash>` |
|---|---|---|

## PTR

Endereço → nome (DNS reverso). Não fica na zona do seu domínio: é configurado
por quem é dono do bloco de IP (o provedor do servidor). Aparece aqui porque é
pergunta comum ao configurar servidor de e-mail.
