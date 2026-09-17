---
titulo: "Regras e categorias do .br"
area: dominios
tipo: referencia
equivalente_hetzner: "nenhum"
depende_de_tela: nao
atualizado_em: "17/09/2026"
---

# Regras e categorias do `.br`

> Fonte: FONTES §5.3 (páginas oficiais "Regras do domínio" e "Categorias .br"
> do Registro.br, consultadas em 17/09/2026). Valores vêm de
> `nicbr.dominio.*`, `nicbr.titular.*` e `nicbr.categorias.*`.

Quem manda no `.br` é o Registro.br, não a Ávila. Esta página resume as regras
dele que mudam o que você consegue registrar.

## Quem pode registrar

Pessoa física com CPF ou pessoa jurídica com CNPJ, **legalmente representada
ou estabelecida no Brasil**, com cadastro regular no Ministério da Fazenda.

Algumas categorias aceitam só CPF, outras só CNPJ.

## Como o nome pode ser

| Regra | Valor |
|---|---|
| Tamanho | de 2 a 26 caracteres, sem contar a categoria — em `suaempresa.com.br`, conta só `suaempresa` |
| Letras e números | `a` a `z` e `0` a `9` |
| Acentos aceitos | `à á â ã é ê í ó ô õ ú ü ç` |
| Hífen | pode no meio, **não** no começo nem no fim |
| Só números | não pode |

## A regra que mais surpreende: equivalência

Para decidir se um nome está livre, o Registro.br **ignora acento, cedilha e
hífen**. Então estes três são o **mesmo nome**:

```text
avila-ops.com.br
avilaops.com.br
ávilaops.com.br
```

Se qualquer um deles já pertence a **outro titular**, os outros não podem ser
registrados. Trocar o hífen de lugar ou tirar o acento não contorna.

Se o nome equivalente é **seu**, não há problema: a regra só bloqueia
equivalência entre titulares diferentes.

## Dois servidores DNS, desde o começo

O registro só se efetiva com pelo menos **dois servidores DNS respondendo com
autoridade** pelo nome. Usando o DNS da Ávila, isso já vem pronto. Usando
servidores próprios, prepare-os antes de pedir o registro.

## Limites por titular

O Registro.br limita quantos pedidos em aberto cada CPF ou CNPJ pode ter:

| Situação | O que acontece |
|---|---|
| Existe domínio seu com a primeira manutenção em atraso | pedido de domínio novo é **recusado** até regularizar |
| Pedidos pendentes (tickets) | limite entre 3 e 200, conforme seu histórico de registros e pagamentos |
| Registros novos ainda não pagos | limite entre 3 e 200, pelo mesmo critério |

O limite exato não é publicado e sobe com histórico bom. Se um pedido for
recusado por isso, o painel mostra o motivo que o Registro.br devolveu.

## Categorias

São dezenas de categorias (DPNs), agrupadas em: Genéricos, Cultura, Educação,
Entretenimento, Localidades, Negócios, Pessoais, Poder Público, Profissões,
Tecnologia e Terceiro Setor.

Alguns exemplos:

| Grupo | Exemplos |
|---|---|
| Genéricos | `com.br`, `net.br`, `etc.br` |
| Negócios | `srv.br`, `ind.br`, `imb.br`, `agr.br`, `log.br` |
| Profissões | `adv.br`, `eng.br`, `arq.br`, `med.br`, `cnt.br`, `geo.br` |
| Tecnologia | `app.br`, `dev.br`, `tec.br`, `seg.br` |
| Localidades | `ribeirao.br`, `sampa.br`, `riopreto.br` e outras cidades |
| Pessoais | `nom.br`, `blog.br` |

**Categorias com exigência extra.** Algumas pedem documento comprobatório,
autorização de uma instituição específica ou DNSSEC obrigatório. Em 17/09/2026
são: `am.br`, `fm.br`, `radio.br`, `edu.br`, `g12.br`, `emp.br`, `leilao.br`,
`psi.br`, `gov.br`, `mil.br`, `coop.br`, `ong.br` e `org.br`.

[O que exatamente cada uma dessas pede ainda precisa ser confirmado categoria
por categoria antes de a Ávila oferecer a extensão.]

A lista de categorias muda: `api.br`, `ia.br`, `social.br` e `xyz.br` entraram
em setembro de 2025. A busca do painel lê a lista do Registro.br, então não
fica desatualizada.
