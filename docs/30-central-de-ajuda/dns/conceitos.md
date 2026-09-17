---
titulo: "Como o DNS funciona"
area: dns
tipo: conceitos
equivalente_hetzner: "Network & Security/DNS/Technical Concepts (Architecture, Terminology)"
depende_de_tela: nao
atualizado_em: "16/09/2026"
---

# Como o DNS funciona

O DNS traduz um nome (`loja.exemplo.com.br`) no endereço de um servidor e diz
para onde vão os e-mails do domínio. Entender três peças evita quase todo
problema: **delegação**, **zona** e **cache**.

## 1. Delegação: quem responde pelo domínio

Quando alguém acessa `exemplo.com.br`, o computador dela pergunta, em cadeia:

1. Aos servidores raiz: quem cuida de `.br`?
2. Ao Registro.br: quem cuida de `exemplo.com.br`?
3. Aos **servidores DNS** informados pelo titular: qual o endereço de
   `exemplo.com.br`?

O passo 2 é a **delegação**. Ela é configurada no domínio (em
**Domínios → Servidores DNS**), não na zona. Se os servidores DNS do domínio
não forem os da Ávila, nada do que você editar na zona da Ávila tem efeito.

## 2. Zona: as respostas

A zona é a lista de **registros** do domínio. Cada registro tem:

| Campo | Exemplo | Significado |
|---|---|---|
| Nome | `www` | subdomínio; `@` é o próprio domínio |
| Tipo | `A` | que tipo de resposta é (ver [referência](referencia-tipos-de-registro.md)) |
| Valor | `203.0.113.10` | a resposta |
| TTL | `3600` | por quantos segundos a resposta pode ficar em cache |

Toda zona tem registros criados automaticamente: **SOA** (dados da zona) e
**NS** (os servidores da Ávila). Eles não podem ser apagados enquanto a zona
estiver ativa.

## 3. Cache e propagação

Os resolvedores (do provedor de internet, do Google, da Cloudflare) guardam a
resposta pelo tempo do TTL. Por isso:

- a mudança vale **na hora** nos servidores da Ávila;
- quem já tinha a resposta antiga continua vendo a antiga até o **TTL antigo**
  expirar;
- troca de servidores DNS de um domínio pode levar mais, porque o TTL da
  delegação é definido pelo registro da extensão.

**Dica:** antes de uma migração planejada, baixe o TTL do registro para `300`
um dia antes. Depois da mudança, suba de novo.

## Termos

Glossário completo em `docs/00-fundacao/GLOSSARIO.md` [virar página pública].

| Termo | Em uma frase |
|---|---|
| Resolvedor | servidor que faz as perguntas em cadeia em nome do usuário |
| Servidor autoritativo | servidor que tem a zona e dá a resposta final |
| Subdomínio | nome à esquerda do domínio (`blog.exemplo.com.br`) |
| Subzona | subdomínio delegado para outros servidores DNS [confirmar se será suportado] |
