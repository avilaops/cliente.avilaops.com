---
titulo: "Domínio fora do ar depois de mexer em DNSSEC ou trocar de provedor"
area: dns
tipo: solucao-de-problemas
equivalente_hetzner: "nenhum"
depende_de_tela: nao
atualizado_em: "16/09/2026"
---

# Domínio fora do ar depois de mexer em DNSSEC ou trocar de provedor

**Sintoma típico:** o site abre em algumas redes e não em outras. Em quem não
abre, o erro é `SERVFAIL` ou "não foi possível encontrar o servidor".

**Causa quase sempre:** o registro guarda um **DS** que não combina com as
chaves dos servidores DNS atuais. Resolvedores que validam DNSSEC (Google,
Cloudflare e muitos provedores) passam a recusar o domínio inteiro.

## Confirmar

```bash
dig exemplo.com.br A @8.8.8.8          # SERVFAIL
dig exemplo.com.br A @8.8.8.8 +cd      # responde: confirma problema de DNSSEC
dig exemplo.com.br DS +short           # DS publicado no registro
dig exemplo.com.br DNSKEY +short       # chaves nos servidores atuais
```

`+cd` desliga a validação. Se com ele responde e sem ele não, é DNSSEC.

Para ver onde a cadeia quebra: [DNSViz](https://dnsviz.net).

## Corrigir

| Situação | O que fazer |
|---|---|
| Trocou para servidores de outro provedor e o DS antigo ficou | apague o DS em **Domínios → DNSSEC**; religue depois com o DS do provedor novo |
| Veio de outro provedor com DNSSEC e trocou para a Ávila | apague o DS antigo; ligue o DNSSEC da Ávila, que publica o DS certo |
| Digitou o DS à mão | confira algoritmo, tipo de resumo e valor com o que o provedor DNS mostra |

Depois de corrigir, a falha some quando o cache do DS expirar, normalmente
em algumas horas.

## Para não acontecer

Ao trocar de provedor DNS com DNSSEC ligado: **primeiro desligue o DNSSEC e
espere pelo menos um dia**, depois troque os servidores, depois religue com o
provedor novo.
