---
titulo: "Mudei o DNS e nada mudou"
area: dns
tipo: solucao-de-problemas
equivalente_hetzner: "nenhum"
depende_de_tela: nao
atualizado_em: "16/09/2026"
---

# Mudei o DNS e nada mudou

Siga na ordem. Cada passo elimina uma causa.

## 1. O domínio usa os servidores DNS da Ávila?

Se não usar, o que você edita na zona da Ávila não vale para ninguém.

```bash
dig NS exemplo.com.br +short
```

A resposta precisa listar os servidores da Ávila [nomes a definir, A2]. Se
listar outros, troque em **Domínios → Servidores DNS** ou edite a zona no
provedor que aparece.

## 2. Os servidores da Ávila já respondem o valor novo?

Pergunte direto a um servidor da Ávila, sem passar por cache:

```bash
dig www.exemplo.com.br A @[ns1 da Ávila] +short
```

- **Valor novo:** a zona está certa; o problema é cache (passo 3).
- **Valor antigo ou vazio:** confira nome e tipo do registro. Erros comuns:
  escrever `www.exemplo.com.br` no campo nome (vira
  `www.exemplo.com.br.exemplo.com.br`), ou criar A onde já existe CNAME.

## 3. É cache

Resolvedores guardam a resposta antiga pelo **TTL que o registro tinha antes**
da mudança. Com TTL de 3600, pode levar até 1 hora; com 86400, até 1 dia.

Para conferir sem o cache do seu computador:

```bash
dig www.exemplo.com.br A @1.1.1.1 +short
dig www.exemplo.com.br A @8.8.8.8 +short
```

Não há como forçar a limpeza do cache de terceiros. Da próxima vez, baixe o
TTL para 300 um dia antes da mudança.

## 4. Acabou de trocar os servidores DNS do domínio?

A delegação tem cache próprio, definido pelo registro da extensão, e costuma
levar mais que um registro comum. No `.br`, os servidores novos precisam
responder pelo domínio antes de o Registro.br aceitar a troca.

## 5. Nada disso

Abra um chamado com a saída dos comandos acima.
