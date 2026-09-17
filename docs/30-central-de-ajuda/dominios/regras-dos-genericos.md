---
titulo: "Regras dos domínios genéricos (.com, .app, .dev...)"
area: dominios
tipo: referencia
equivalente_hetzner: "Robot/Domain Registration Robot/Domain Robot FAQ"
depende_de_tela: nao
atualizado_em: "17/09/2026"
---

# Regras dos domínios genéricos

> Fonte: FONTES §1 a §3 (ICANN), §12 (UDRP) e §13 (sintaxe e extensões).
> Valores vêm de `icann.*` e `generico.*`.
>
> Página irmã: [Regras e categorias do `.br`](regras-e-categorias-br.md). As
> duas famílias seguem regras diferentes, e a diferença custa dinheiro se
> passar despercebida.

`.com`, `.net`, `.app`, `.dev` e as demais extensões genéricas não têm um dono
único como o `.br`. Cada extensão tem seu próprio registro, todos sob regras da
ICANN. A Ávila atua como **revendedora de um registrador credenciado**.

## Quem pode registrar

Não existe exigência de CPF, CNPJ nem de estar no Brasil. O que a ICANN exige é
que os dados do titular sejam **verdadeiros e verificáveis**:

- o **e-mail do titular precisa ser confirmado em até 15 dias** após o
  registro, uma transferência ou uma alteração de dados;
- sem a confirmação, o domínio é **suspenso** até você confirmar;
- dado falso ou desatualizado pode levar à suspensão ou ao cancelamento.

É por isso que o painel insiste no e-mail do titular: não é burocracia nossa.

## Como o nome pode ser

| Regra | Valor |
|---|---|
| Tamanho | 1 a 63 caracteres na parte antes do ponto; 255 no nome inteiro |
| Caracteres | letras `a`–`z`, números `0`–`9` e hífen |
| Primeiro caractere | letra **ou** número |
| Último caractere | letra ou número, nunca hífen |
| Hífen duplo | `--` na 3ª e 4ª posições é reservado para nomes com acento (formato `xn--`) |
| Maiúsculas | não existem: o DNS não diferencia `Avila` de `avila` |

Acento e caracteres não latinos existem em várias extensões, mas cada registro
mantém a própria lista do que aceita. O painel valida antes de cobrar.

## A diferença que mais pega: não existe equivalência

No `.br`, o Registro.br ignora acento, cedilha e hífen ao comparar nomes, então
`avila-ops.com.br` e `avilaops.com.br` são o **mesmo** nome e não podem ficar
com titulares diferentes.

**Nos genéricos não é assim.** `avila-ops.com` e `avilaops.com` são dois nomes
diferentes, e qualquer pessoa pode registrar o outro.

Consequência prática: se o nome da sua marca importa, registrar só uma variação
não protege as outras. Quem quiser fechar a porta registra as variações que
interessam, ou trata isso por marca registrada (veja abaixo).

## Extensões com regra própria

Além das regras gerais, cada extensão pode ter as suas. Duas que aparecem com
frequência:

| Extensão | Regra | O que muda para você |
|---|---|---|
| `.app` | está na lista **HSTS preload**: HTTPS obrigatório em toda conexão | site sem certificado válido **não abre**, e o navegador não oferece a opção de seguir mesmo assim |
| `.dev` | idem | idem |

Isso não é configuração que a Ávila possa desligar: está embutido nos
navegadores. Se você vai usar `.app` ou `.dev`, o site precisa de HTTPS desde o
primeiro dia. Com hospedagem da Ávila, o certificado já vem.

## Transferência: as travas de 60 dias

A transferência para outro provedor fica restrita por **60 dias** depois de
registrar o domínio, de transferi-lo entre provedores ou de trocar o titular.
Detalhes em [Trava de transferência](trava-de-transferencia.md).

## Vencimento

Genéricos seguem a política ERRP da ICANN: avisos antes e depois, interrupção
do DNS e um período de **resgate de 30 dias** depois da exclusão, com taxa.
Detalhes em [Ciclo de vida](ciclo-de-vida.md).

## Disputa sobre o nome

Nos genéricos o mecanismo é a **UDRP**, da ICANN — não o SACI-Adm, que só vale
para `.br`. Veja [Disputas](disputas-saci-adm-e-udrp.md).

## O que ainda não está aqui

Quais extensões a Ávila vende, por quanto, e qual a taxa de resgate de cada
uma. Isso depende do registrador parceiro e sai na página de preços, que mostra
por extensão o preço de registro, de renovação, de renovação após vencimento e
de resgate.
