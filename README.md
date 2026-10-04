<div align="center">

# Portal do Cliente · Ávila Ops

**Domínio no seu nome, DNS na sua mão e renovação que não depende de alguém lembrar.**

O painel onde o cliente da Ávila Ops registra domínios, edita o próprio DNS e
acompanha cobrança, segurança e marketing, tudo no mesmo lugar.

![Fase](https://img.shields.io/badge/fase-documenta%C3%A7%C3%A3o%20antes%20do%20c%C3%B3digo-0a66c2)
![Regimento](https://img.shields.io/badge/regimento-minuta-f0ad4e)
![Idioma](https://img.shields.io/badge/idioma-pt--BR-2ea44f)
![Login](https://img.shields.io/badge/login-SSO%20auth.avilaops.com-6f42c1)

[Visão geral](#visão-geral) ·
[Estado atual](#estado-atual) ·
[Módulos](#módulos) ·
[Documentação](#documentação) ·
[Princípios](#princípios) ·
[Decisões em aberto](#decisões-em-aberto) ·
[Contribuir](#como-contribuir)

</div>

---

## Visão geral

| | |
|---|---|
| **Para quem** | Pequenos negócios e profissionais que têm (ou vão ter) site e e-mail com a Ávila, e agências que cuidam dos domínios dos clientes. |
| **O problema** | O domínio vence e derruba site e e-mail; ninguém sabe onde ele foi registrado; mexer no DNS exige chamar alguém. |
| **A proposta** | Domínio sempre no CPF/CNPJ do cliente, renovação automática, DNS editável sem depender da equipe e tudo no mesmo painel dos outros serviços. |
| **O que não é** | Não é hospedagem, e a Ávila não é registradora credenciada. Para `.br`, o modelo é **Provedor de Serviços do Registro.br**; para as demais extensões, **revendedora de registrador credenciado**. |

O produto é **self-service**: o cliente registra, renova, transfere e edita o
DNS sozinho, e a equipe atua nas exceções.

> **Nome do projeto.** O repositório nasceu como `account.avilaops.com` e
> passou a se chamar `cliente.avilaops.com`. Os documentos ainda usam o nome
> antigo em vários pontos; a troca acompanha a publicação do endereço
> definitivo.

## Estado atual

A decisão D7 é **documentação e regimento antes do código**. Hoje o
repositório tem só a base documental; o painel ainda não foi construído.

| Frente | Situação |
|---|---|
| Fundação (decisões, glossário, fontes, requisitos) | ✅ escrita · 14 decisões em aberto |
| Regimento externo (termos, contrato, privacidade, SLA…) | 📝 minuta, aguardando revisão jurídica |
| Regimento interno (renovação, transferências, abuso, auditoria…) | 📝 minuta |
| Central de ajuda (domínios, DNS, segurança) | 📝 conceitos e referências escritos; os passo a passo esperam a tela existir |
| Código do painel | 🚧 começou no `app.avilaops.com`, em `/portal`: página do domínio e DNS editável pelo titular (ainda não publicado) |
| Login | ✅ o SSO já existe em `auth.avilaops.com` |

O quadro completo, item por item e com evidência, está em
[`ESTADO-DE-IMPLEMENTACAO.md`](docs/00-fundacao/ESTADO-DE-IMPLEMENTACAO.md),
que separa o que o regimento **promete** do que **existe**.

## Módulos

| Módulo | O que faz |
|---|---|
| **Conta** | Cadastro PF/PJ, dados do titular reaproveitáveis e encerramento de conta. |
| **Segurança** | SSO, verificação em duas etapas, confirmação de ações sensíveis, sessões e código de atendimento. |
| **Domínios** | Busca, registro, renovação automática, transferência de entrada e saída, código de autorização, trava, titular, servidores DNS, DNSSEC e glue. |
| **DNS** | Zonas, registros com validação, importação e exportação no formato BIND, versões e restauração. |
| **Cobrança** | Pagamento antes do comando, régua de renovação, reembolso automático em caso de falha e notas fiscais. |
| **Avisos** | Vencimento, ações sensíveis e incidentes por e-mail (outros canais a definir). |
| **Marketing** | Assistentes de Google Analytics 4, Google Ads e Mercado Livre Ads, sempre na conta do próprio cliente. |
| **Abuso** | Formulário público, fila de análise e suspensão de DNS. |
| **Auditoria** | Trilha imutável de todo evento: quem, quando, antes, depois e origem. |
| **Painel interno** | Filas de exceção (renovação com problema, fraude, abuso, transferência parada), com motivo obrigatório em toda ação da equipe. |

Catálogo pretendido: `.br`, `.com`, `.ai`, `.io`, `.app` e `.dev`. Cada
extensão só entra no ar depois de a regra dela estar confirmada em fonte
oficial. Detalhes em [`REQUISITOS.md`](docs/40-produto/REQUISITOS.md).

## Documentação

O mapa completo, com o estado de cada página, está em [`docs/INDICE.md`](docs/INDICE.md).

```text
docs/
├── 00-fundacao/            decisões, glossário, fontes de regras de terceiros, estado de implementação
├── 10-regimento-externo/   documentos públicos: termos, contrato de registro, uso aceitável,
│                           privacidade, SLA, cobrança, abuso, segurança da conta, medidas técnicas
├── 20-regimento-interno/   procedimentos da equipe: renovação, transferências, verificação de titular,
│                           disputas, plantão, conciliação, auditoria, continuidade, backup
├── 30-central-de-ajuda/    páginas para o cliente, uma árvore por assunto (domínios, DNS, segurança…)
├── 40-produto/             requisitos e a camada de políticas e parâmetros
├── INDICE.md               mapa e checklist de cobertura
└── NARRATIVA.md            posicionamento e vocabulário
```

Por onde começar:

- **O produto:** [Narrativa](docs/NARRATIVA.md) → [Requisitos](docs/40-produto/REQUISITOS.md)
- **As regras:** [Decisões](docs/00-fundacao/DECISOES.md) → [Fontes de regras de terceiros](docs/00-fundacao/FONTES-REGRAS-DE-TERCEIROS.md)
- **O que o cliente vai ler:** [Central de ajuda](docs/30-central-de-ajuda/README.md) → [Ciclo de vida do domínio](docs/30-central-de-ajuda/dominios/ciclo-de-vida.md)
- **O vocabulário:** [Glossário](docs/00-fundacao/GLOSSARIO.md)

## Princípios

1. **O domínio é sempre do cliente.** Registrado no CPF/CNPJ dele, nunca no da Ávila, nem "temporariamente". A Ávila aparece só como contato técnico.
2. **Os dados de marketing também são do cliente.** Analytics, contas de anúncio e dados ficam na conta Google e na conta Mercado Livre dele; a Ávila recebe só a função que o serviço exige.
3. **Ideia não é funcionalidade.** Página de ajuda que descreve uma tela só é escrita quando a tela existe em produção.
4. **Regra de terceiro tem fonte.** Prazo do Registro.br, regra da ICANN ou preço de atacado só entra com a fonte oficial ao lado; sem ela, fica marcado **PENDENTE DE CONFIRMAÇÃO**.
5. **Nenhum prazo regulatório no código.** Regra externa, regra de fornecedor e política do produto ficam numa camada própria de parâmetros, com fonte, vigência e histórico.
6. **Tudo que mexe em DNS ou no registro deixa rastro**, e todo comando que custa dinheiro é idempotente.

## Decisões em aberto

As que mais seguram o avanço:

| | Decisão | Por que importa |
|---|---|---|
| **A1** | Qual registrador parceiro para as extensões genéricas | Define contrato, prazos, preços de resgate e forma de pagamento. |
| **A2** | Onde roda o DNS autoritativo (servidor próprio, API de terceiro ou híbrido) | Define SLA, DNSSEC, nomes dos servidores e custo. |
| **A4** | Gateway de cobrança e saldo pré-pago | Muda a régua de renovação, o reembolso e a emissão de nota. |
| **A6** | Plantão fora do horário comercial | Sem plantão, o SLA não pode prometer atendimento 24h. |

As 14 decisões abertas, com contexto e impacto, estão em
[`DECISOES.md`](docs/00-fundacao/DECISOES.md).

## Stack prevista

Será definida quando A1 e A2 estiverem decididas. O que já está fixado:

- Login pelo SSO de `auth.avilaops.com`.
- Credenciais de registrador e de EPP nunca entram no Git, em `.env.example` nem em log.
- Português do Brasil em tela e documentação, com datas no formato `DD/MM/AAAA`.

## Como contribuir

As regras do projeto estão no [`AGENTS.md`](AGENTS.md) e valem para pessoas e
agentes de IA. As principais:

- **Vocabulário obrigatório.** "Provedor de Serviços do Registro.br" para `.br` e "revendedora de registrador credenciado" para as demais extensões. É **proibido** descrever a Ávila como registradora, registradora credenciada ou credenciada pela ICANN: é falso e tem consequência jurídica.
- Todo documento de regimento tem cabeçalho de versão e histórico de revisão; os externos levam a marca **MINUTA** até a revisão jurídica.
- Dado ainda não definido fica entre colchetes, como `[e-mail de atendimento]`.
- Ao concluir uma entrega, atualize o [estado de implementação](docs/00-fundacao/ESTADO-DE-IMPLEMENTACAO.md) e o [índice](docs/INDICE.md).

## Projetos relacionados

| Projeto | Papel |
|---|---|
| `auth.avilaops.com` | Login único (SSO) de toda a plataforma |
| `app.avilaops.com` | Painel interno da equipe Ávila Ops |
| `docs.avilaops.com` | Documentação pública da plataforma |

## Licença

Código e documentação proprietários da Ávila Ops. Todos os direitos reservados.

---

<div align="center">
<sub>Feito pela <a href="https://avilaops.com">Ávila Ops</a></sub>
</div>
