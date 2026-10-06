# Índice e checklist de cobertura

**Atualizado em:** 06/10/2026

Mapa de toda a documentação do account.avilaops.com. A coluna **Hetzner**
aponta a página equivalente no clone em `docs/Docs/docs.avilaops.com/`, que é
o checklist para não esquecer nenhum assunto.

**Estados:** `escrito` · `minuta` (precisa revisão) · `backlog` (pode escrever
agora) · `espera tela` (só quando a funcionalidade existir) · `bloqueado` (depende
de decisão em `DECISOES.md`) · `fora` (não se aplica).

---

## 1. Fundação

| Documento | Estado |
|---|---|
| [README do projeto](../README.md) | escrito |
| [AGENTS.md](../AGENTS.md) | escrito |
| [Narrativa e vocabulário](NARRATIVA.md) | minuta |
| [Decisões](00-fundacao/DECISOES.md) | escrito, 14 abertas |
| [Glossário](00-fundacao/GLOSSARIO.md) | escrito |
| [Estado de implementação](00-fundacao/ESTADO-DE-IMPLEMENTACAO.md) | escrito |
| [Regras de terceiros com fonte](00-fundacao/FONTES-REGRAS-DE-TERCEIROS.md) | escrito, revalidar antes de publicar |
| [Requisitos do produto](40-produto/REQUISITOS.md) | minuta |
| [Políticas e parâmetros](40-produto/POLITICAS-E-PARAMETROS.md) | minuta de desenho; camada implementada no app (PR #84), políticas pendentes de confirmação |

## 2. Regimento externo (público, `/legal`)

| Documento | Hetzner | Estado |
|---|---|---|
| [01 Termos de Serviço](10-regimento-externo/01-termos-de-servico.md) | Terms and Conditions (não clipado) | minuta |
| [02 Contrato de Registro de Domínios](10-regimento-externo/02-contrato-registro-dominios.md) | Robot/Domain Registration Robot; ERRP; Contact information verification | minuta, bloqueado A1 |
| [03 Uso Aceitável](10-regimento-externo/03-politica-uso-aceitavel.md) | Security and Identification/Abuse form | minuta |
| [04 Privacidade](10-regimento-externo/04-politica-privacidade.md) | Company and Policy/Data Protection | minuta |
| [05 SLA e Suporte](10-regimento-externo/05-sla-e-suporte.md) | Company and Policy/SLA; Allgemein/Support opening hours | minuta, bloqueado A2, A6 |
| [06 Cobrança, Renovação e Cancelamento](10-regimento-externo/06-cobranca-renovacao-cancelamento.md) | Billing and Account Management/Billing, Cancellation, 30 days policy | minuta, bloqueado A4, A5 |
| [07 Denúncia de Abuso](10-regimento-externo/07-denuncia-abuso.md) | Security and Identification/Abuse form | minuta |
| [08 Segurança da Conta](10-regimento-externo/08-seguranca-da-conta.md) | 2FA; Login-OTP; Support OTP; Phishing; Fraud prevention | minuta |
| [09 Medidas Técnicas e Organizativas](10-regimento-externo/09-medidas-tecnicas-organizativas.md) | Security and Identification/TOMs | minuta |
| Aviso de cookies | — | backlog (hoje só cookies necessários) |
| Página "Quem somos / dados do fornecedor" | Company and Policy/Overview; Legal requirements for websites | backlog |
| Política de reajuste de preços | Infrastructure and availability/Price adjustment | coberto em 06 §3 |
| Newsletter e comunicações | Company and Policy/Customer newsletter | fora (não haverá newsletter no lançamento) |
| Sustentabilidade, ISO 27001 próprio, fórum | Company and Policy | fora |
| Cláusula de integrações de terceiros: cliente autoriza o acesso, é dono das contas e responde pelo gasto de mídia no Google Ads e no Mercado Livre Ads | — | backlog, entra no 01 Termos |

## 3. Regimento interno (não publicar)

| Procedimento | Estado |
|---|---|
| [01 Papéis e responsabilidades](20-regimento-interno/01-papeis-e-responsabilidades.md) | minuta |
| [02 Renovação e régua de vencimento](20-regimento-interno/02-renovacao-e-regua-de-vencimento.md) | minuta |
| [03 Transferências](20-regimento-interno/03-transferencias.md) | minuta |
| [04 Verificação de titular](20-regimento-interno/04-verificacao-de-titular.md) | minuta |
| [05 Abuso, ordens e disputas](20-regimento-interno/05-abuso-ordens-e-disputas.md) | minuta |
| [06 Plantão e incidentes](20-regimento-interno/06-plantao-e-incidentes.md) | bloqueado A6 |
| [07 Saldo e conciliação](20-regimento-interno/07-saldo-e-conciliacao.md) | bloqueado A1, A4 |
| [08 Acesso interno e auditoria](20-regimento-interno/08-acesso-interno-e-auditoria.md) | minuta |
| [09 Continuidade](20-regimento-interno/09-continuidade.md) | minuta |
| [10 Homologação e revenda](20-regimento-interno/10-homologacao-e-revenda.md) | minuta |
| [11 Atendimento e recuperação de conta](20-regimento-interno/11-atendimento-e-recuperacao-de-conta.md) | minuta |
| [12 Manutenção programada](20-regimento-interno/12-manutencao-programada.md) | minuta |
| [13 Backup e restauração](20-regimento-interno/13-backup-e-restauracao.md) | minuta |
| Troca de preços e tabela por extensão | backlog |
| [14 Integrações de marketing](20-regimento-interno/14-integracoes-de-marketing.md) | minuta, depende de A10-A13 |

## 4. Central de ajuda (público, `/ajuda`)

Molde e regras em [30-central-de-ajuda/README.md](30-central-de-ajuda/README.md).

### 4.1 Conta

| Página | Tipo | Hetzner | Estado |
|---|---|---|---|
| Visão geral da conta e do painel | visão geral | Billing and Account Management/Hetzner Account Getting Started | espera tela |
| Criar conta | primeiros passos | idem | espera tela |
| Dados cadastrais (PF/PJ) | primeiros passos | Robot/General/Change access data | espera tela |
| Usuários da conta e permissões | como fazer | — | bloqueado A7 |
| Transferir domínio entre contas da Ávila | como fazer | Billing and Account Management/Product migration | espera tela |
| Encerrar conta | primeiros passos | Cancellation/Overview | espera tela |
| Pedidos de privacidade (exportar, excluir dados) | como fazer | Data Protection | espera tela |
| FAQ: conta | faq | — | nasce do atendimento |

### 4.2 Segurança

| Página | Tipo | Hetzner | Estado |
|---|---|---|---|
| Ligar verificação em duas etapas | primeiros passos | Security and Identification/Two-factor authentication | espera tela |
| Confirmação de login em dispositivo novo | conceitos | Login-OTP | espera tela |
| Código de atendimento | conceitos | Support OTP | espera tela |
| Sessões ativas | como fazer | — | espera tela |
| Reconhecer e-mail falso da Ávila | conceitos | Phishing email collection | backlog (depende só de A9) |
| Por que pedimos verificação (fraude) | faq | Fraud prevention FAQ | backlog |
| [Perdi o acesso à conta](30-central-de-ajuda/seguranca/perdi-acesso.md) | solução de problemas | — | escrito (depende de A9) |
| Tokens de API | primeiros passos | Cloud/API/Generating an API token | bloqueado A8 |
| Usar a API | referência | Cloud/API/Using the API | bloqueado A8 |

### 4.3 Domínios

| Página | Tipo | Hetzner | Estado |
|---|---|---|---|
| [Visão geral](30-central-de-ajuda/dominios/visao-geral.md) | visão geral | Domain Registration Robot/Overview | escrito |
| [Ciclo de vida do domínio](30-central-de-ajuda/dominios/ciclo-de-vida.md) | conceitos | ERRP | minuta, bloqueado A1 |
| Pesquisar e registrar | primeiros passos | Domain Registration Robot/Getting started; Managed/Ordering Domains | espera tela |
| [Regras e categorias do `.br`](30-central-de-ajuda/dominios/regras-e-categorias-br.md) | referência | — | escrito, com fonte oficial |
| [Regras dos genéricos (`.com`, `.app`, `.dev`)](30-central-de-ajuda/dominios/regras-dos-genericos.md) | referência | Domain Robot FAQ | escrito, com fonte oficial; catálogo e preços dependem de A1 |
| [Extensões de país (`.ai`, `.io`)](30-central-de-ajuda/dominios/extensoes-de-pais-ai-io.md) | referência | — | escrito, com fonte oficial; regras por extensão a confirmar |
| Dados do titular e contatos | primeiros passos | konsoleH Domain FAQ (Owner-C/Admin-C) | espera tela |
| Confirmar e-mail do titular (genéricos) | primeiros passos | Contact information verification; Contact details verification (konsoleH) | espera tela |
| Trocar titular | como fazer | konsoleH Domain FAQ | espera tela |
| Renovação automática e manual | primeiros passos | — | espera tela |
| Recuperar domínio vencido | solução de problemas | ERRP | espera tela |
| Trazer domínio para a Ávila | primeiros passos | Tutorial ChProv; Change your provider to Hetzner | espera tela |
| Levar domínio para outro provedor / código de autorização | primeiros passos | Tutorial ChProv outgoing; Auth code on konsoleH | espera tela |
| [Trava de transferência](30-central-de-ajuda/dominios/trava-de-transferencia.md) | conceitos | — | escrito |
| Trocar servidores DNS do domínio | primeiros passos | DNS delegating; Updating name servers of external domains | espera tela |
| Hosts filho (glue) | como fazer | — | espera tela |
| Ligar DNSSEC | como fazer | — | espera tela |
| Privacidade no WHOIS/RDAP | conceitos | E-Mail-Interface (2019 GDPR changes) | bloqueado A1 |
| [Disputas: SACI-Adm e UDRP](30-central-de-ajuda/dominios/disputas-saci-adm-e-udrp.md) | conceitos | — | escrito, com fonte oficial |
| Bloqueio e desbloqueio por abuso | conceitos | Block/unblock hosting or domain | backlog |
| Preços por extensão e reajustes | referência | Domain price adjustments | bloqueado A1 |
| FAQ: registro | faq | Domain Robot FAQ | nasce do atendimento |
| FAQ: transferências | faq | Domain Robot FAQ | nasce do atendimento |
| Mensagens de erro | solução de problemas | Domain Robot Error FAQ | espera tela |
| Interface por e-mail | — | Email Interface | fora (legado da Hetzner) |

### 4.4 DNS

| Página | Tipo | Hetzner | Estado |
|---|---|---|---|
| Visão geral do DNS da Ávila | visão geral | DNS/Overview | bloqueado A2 |
| [Como o DNS funciona](30-central-de-ajuda/dns/conceitos.md) | conceitos | Technical Concepts/Architecture, Terminology | escrito |
| Criar zona | primeiros passos | Getting Started/Creating a zone | espera tela |
| Adicionar, editar e apagar registro | primeiros passos | Getting Started/Adding records | espera tela |
| Importar e exportar arquivo de zona | primeiros passos | Getting Started/Editing the zone file | espera tela |
| Versões da zona e restauração | como fazer | — | espera tela |
| Servidores DNS da Ávila (nomes e IPs) | referência | FAQ/Name servers | bloqueado A2 |
| Usar DNS da Ávila com domínio de outro provedor | como fazer | Updating name servers of external domains | espera tela |
| Zona secundária (AXFR) | como fazer | How-To/Configuring secondary zones | bloqueado A2 |
| [Tipos de registro](30-central-de-ajuda/dns/referencia-tipos-de-registro.md) | referência | Record types (13 páginas) | escrito |
| [E-mail com Google Workspace](30-central-de-ajuda/dns/receita-email-google-workspace.md) | como fazer | Managed/Email/Email security | escrito |
| Apontar domínio para site na Ávila (Lojas, sites) | como fazer | Managed/Subdomain administration | backlog |
| Redirecionar raiz para www | como fazer | Redirect a domain to subdomain www | backlog (depende de onde roda o site) |
| TTL e propagação | conceitos | — | coberto em conceitos |
| FAQ: geral | faq | FAQ/General | nasce do atendimento |
| FAQ: servidores DNS | faq | FAQ/Name servers | nasce do atendimento |
| FAQ: registros | faq | FAQ/Records | nasce do atendimento |
| FAQ: zonas (subzonas, limites) | faq | FAQ/Zones | bloqueado A2 |
| [Problemas: mudança não aparece](30-central-de-ajuda/dns/problema-mudanca-nao-aparece.md) | solução de problemas | — | escrito (nomes dos servidores: A2) |
| [Problemas: fora do ar por DNSSEC](30-central-de-ajuda/dns/problema-dnssec.md) | solução de problemas | — | escrito |
| Problemas: conflito de CNAME | solução de problemas | — | coberto na referência |

### 4.5 Cobrança

| Página | Tipo | Hetzner | Estado |
|---|---|---|---|
| Como a cobrança funciona | visão geral | Billing system at Hetzner | bloqueado A4 |
| Formas de pagamento | referência | Payment Overview | bloqueado A4 |
| Nota fiscal | conceitos | Value added tax | bloqueado A3 |
| Cupons e créditos | como fazer | Promo codes | bloqueado A4 |
| Cancelar serviço ou renovação | primeiros passos | Cancellation (Console/Robot/konsoleH) | espera tela |
| Reembolso e arrependimento | conceitos | — | minuta em externo 06 |
| Pagamento em atraso | conceitos | — | minuta em externo 06 |

### 4.6 Suporte

| Página | Tipo | Hetzner | Estado |
|---|---|---|---|
| Canais e horários | referência | Support Team opening hours | bloqueado A6, A9 |
| Página de status | referência | — | bloqueado A2 |
| Denunciar abuso | primeiros passos | Abuse form | minuta em externo 07 |

### 4.7 Marketing: Analytics e anúncios

Sem equivalente na Hetzner. O checklist aqui é a trilha oficial do Google em
`docs/Docs/docs.avilaops.com/Google Analytics/` e a documentação de Product Ads
do Mercado Livre. Regras e fontes em
[FONTES §8-10](00-fundacao/FONTES-REGRAS-DE-TERCEIROS.md).

| Página | Tipo | Referência | Estado |
|---|---|---|---|
| Visão geral do módulo Marketing | visão geral | Google Analytics para iniciantes | espera tela |
| Por que a conta de Analytics e de anúncios é sua | conceitos | D10 | backlog |
| Funções de acesso no GA4 e qual dar à Ávila | referência | Gerenciamento de restrição de dados e acesso | backlog |
| Eventos principais recomendados por tipo de negócio | referência | Marcar eventos como principais | backlog |
| Conectar o Google | primeiros passos | — | bloqueado A10 |
| Configurar o Google Analytics 4 | primeiros passos | Configurar o Google Analytics para um site | espera tela |
| Instalar a tag fora da Ávila (CMS, Tag Manager, `<head>`) | como fazer | idem, seção "Configurar a coleta de dados" | backlog |
| Tráfego interno, referências indesejadas e vários domínios | como fazer | Filtrar tráfego interno; Medição em vários domínios | backlog (não depende de tela: é feito no Google) |
| Aviso de cookies e modo de consentimento | conceitos | Modo de consentimento | backlog |
| Ler os relatórios do GA4 | conceitos | Visão geral dos relatórios; Sobre a página inicial | backlog |
| Vincular o Google Ads e importar conversões | primeiros passos | Conectar o Google Ads; Criar conversões do Google Ads | bloqueado A10, A11 |
| Conectar o Mercado Livre | primeiros passos | — | espera tela |
| Ativar a Publicidade no Mercado Livre | como fazer | FONTES §10 (erro 404) | backlog |
| Criar e ajustar campanhas no Mercado Livre Ads | primeiros passos | Product Ads | bloqueado A12 |
| Métricas do Mercado Livre Ads: ROAS, impressões perdidas, vendas indiretas | referência | Product Ads | backlog |
| Desconectar e remover o acesso da Ávila | primeiros passos | interno 14 | espera tela |
| Problemas: GA4 sem dados em Tempo real | solução de problemas | norma GA4 §6 | nasce de chamado real |
| FAQ: Analytics e anúncios | faq | — | nasce do atendimento |

## 5. Fora do escopo (Hetzner cobre, a Ávila não oferece aqui)

Cloud (servidores, volumes, floating IPs, firewalls, placement groups, apps),
Robot (dedicados, colocation, RAID, rescue), Storage (object storage, storage
box, storage share), Network & Security (load balancer, redes privadas,
certificados gerenciados), Managed (hospedagem, bancos, servidor gerenciado,
webmail, cron). Reavaliar se o produto crescer.
