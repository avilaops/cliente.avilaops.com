# Central de ajuda

Documentação para o cliente, publicada em `account.avilaops.com/ajuda`.
Molde: documentação da Hetzner (`docs/Docs/docs.avilaops.com/`), com uma
correção deliberada: a Hetzner espalha domínio e DNS em três árvores (Robot,
konsoleH, Console) por herança de sistemas antigos. Aqui é **uma árvore por
assunto**, não por tela.

## Áreas

```text
30-central-de-ajuda/
  conta/        criar conta, usuários, dados, encerrar
  seguranca/    verificação em duas etapas, código de atendimento, e-mails falsos, tokens
  dominios/     registrar, renovar, transferir, titular, DNSSEC, disputas
  dns/          zonas, registros, servidores DNS, referência por tipo
  cobranca/     pagamento, nota, renovação, reembolso, cancelamento
  marketing/    Google Analytics 4, Google Ads, Mercado Livre Ads
  suporte/      canais, horários, status, abuso
```

## Molde de cada área

Igual ao padrão que a Hetzner repete em DNS, Redes, Storage e Firewalls:

| Tipo de página | Para quê | Regra |
|---|---|---|
| **Visão geral** | o que é, conceitos, links para o resto | uma por área |
| **Primeiros passos** | uma tarefa por página, passos numerados | só quando a tela existe |
| **Referência** | um item por página ou seção (ex.: tipo de registro) | pode ser escrita antes da tela |
| **Como fazer** | casos avançados ou integrações | só quando a tela existe |
| **Conceitos** | arquitetura e terminologia | pode ser escrita antes da tela |
| **Perguntas frequentes** | **separadas por subtema**, nunca uma página gigante | nasce de pergunta real de atendimento |
| **Solução de problemas** | consertar estado quebrado (diferente de FAQ) | nasce de chamado real |

Modelo de página: [`MODELO-DE-PAGINA.md`](MODELO-DE-PAGINA.md). Backlog
completo com o equivalente Hetzner de cada página: [`../INDICE.md`](../INDICE.md).

## Já escritas (não dependem de tela)

- [dns/conceitos.md](dns/conceitos.md)
- [dns/referencia-tipos-de-registro.md](dns/referencia-tipos-de-registro.md)
- [dns/receita-email-google-workspace.md](dns/receita-email-google-workspace.md)
- [dominios/visao-geral.md](dominios/visao-geral.md)
- [dominios/ciclo-de-vida.md](dominios/ciclo-de-vida.md)
- [dominios/trava-de-transferencia.md](dominios/trava-de-transferencia.md)
- [dominios/regras-e-categorias-br.md](dominios/regras-e-categorias-br.md)
- [dominios/regras-dos-genericos.md](dominios/regras-dos-genericos.md)
- [dominios/disputas-saci-adm-e-udrp.md](dominios/disputas-saci-adm-e-udrp.md)
- [seguranca/perdi-acesso.md](seguranca/perdi-acesso.md)
- [dns/problema-mudanca-nao-aparece.md](dns/problema-mudanca-nao-aparece.md)
- [dns/problema-dnssec.md](dns/problema-dnssec.md)
