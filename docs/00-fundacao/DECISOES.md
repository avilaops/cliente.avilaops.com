# Decisões do account.avilaops.com

**Atualizado em:** 16/09/2026 · **Responsável:** Nícolas Ávila

> Decisão tomada não é apagada: quando mudar, registrar a substituição e a data.

## Decididas

| # | Decisão | Data | Origem |
|---|---|---|---|
| D1 | Genéricos: Ávila como **revendedora** de registrador credenciado. Credenciamento direto na ICANN está descartado para o tamanho atual. | 31/08/2026 | `docs/comercial/dominios-revenda-levantamento.md` |
| D2 | `.br`: Ávila como **Provedor de Serviços homologado** pelo Registro.br, integração EPP. | 31/08/2026 | idem |
| D3 | Ordem: genéricos primeiro (com um domínio nosso de teste), `.br` depois. | 31/08/2026 | idem, a confirmar pelo Nicolas |
| D4 | Domínio sempre no CPF/CNPJ do cliente. Ávila só como contato técnico. | regra da casa | idem, seção 4 |
| D5 | O produto é **self-service**: o cliente registra, renova, transfere e edita DNS sozinho. A equipe atua em exceção. | 16/09/2026 | pedido do Nicolas |
| D6 | Modelo confirmado neste projeto (revenda + provedor `.br`), e não registrador próprio. | 16/09/2026 | Nicolas, nesta sessão |
| D7 | Documentação e regimento antes do código, usando a documentação da Hetzner como checklist de cobertura. | 16/09/2026 | Nicolas |
| D8 | Login pelo SSO `auth.avilaops.com`. | 16/09/2026 | padrão da plataforma |
| D9 | O account ganha o módulo **Marketing**: o cliente configura sozinho Google Analytics 4, Google Ads e Mercado Livre Ads pelo painel. | 16/09/2026 | Nicolas |
| D10 | Conta de Analytics, conta de anúncios e dados são **sempre do cliente**, na conta Google e na conta Mercado Livre dele. A Ávila recebe só a função que o serviço exige. Mesmo princípio de D4. | 16/09/2026 | Nicolas; norma `docs/analytics/NORMA-GA4-CONTA-DO-CLIENTE.md` |
| D11 | Regra externa (ICANN, NIC.br), regra de fornecedor e política do produto ficam em **camada própria de parâmetros**, com fonte, vigência e histórico. Nenhum prazo regulatório espalhado em código ou tela. Mudança só em discussão (ex.: trava de 30 dias da ICANN) fica monitorada e não é aplicada. | 16/09/2026 | Nicolas; `40-produto/POLITICAS-E-PARAMETROS.md` |
| D12 | **Catálogo pretendido:** `.br`, `.com`, `.ai`, `.io`, `.app`, `.dev` e outras a definir. Três famílias diferentes: ccTLD brasileiro, gTLDs e ccTLDs estrangeiros. Cada extensão só entra no ar depois de a regra dela estar confirmada em fonte oficial (FONTES §5.3, §13, §14). | 17/09/2026 | Nicolas, nesta sessão; canal de venda de cada uma ainda depende de A1 |

## Abertas (bloqueiam partes do regimento)

| # | Pergunta | Por que importa | Bloqueia |
|---|---|---|---|
| A1 | Qual registrador parceiro? OpenSRS/Tucows é a referência. Levantado em 16/09/2026: ativação de US$ 95 que vira crédito, **pré-pago só em dólar**, 3% de taxa no cartão, crédito não reembolsável; vende `.com.br` novo, mas **não aceita transferência de `.br`**. Comparar com pelo menos mais um parceiro. **Com o catálogo de D12, o parceiro precisa carregar `.ai` e `.io` além dos gTLDs** — o `.ai` é operado pela Identity Digital, com credenciamento próprio (FONTES §14). Pode ser que nenhum parceiro cubra tudo e a casa precise de mais de um canal. | O contrato de registro dele é repassado ao cliente; define prazos, preços de resgate e forma de pagamento. OpenSRS não substitui a homologação própria no Registro.br para os `.br` que os clientes já têm. | `02-contrato-registro-dominios.md`, interno 07 |
| A2 | Onde roda o DNS autoritativo? Opções: servidor próprio (ex.: PowerDNS nos servidores Hetzner), API de terceiro (Cloudflare, Hetzner DNS) ou híbrido. | Define SLA possível, anycast, DNSSEC, nomes dos servidores (`ns1...`) e custo. | `05-sla-e-suporte.md`, central de ajuda de DNS |
| A3 | **O CNPJ atual é MEI.** Levantado em 16/09/2026 (fonte secundária): os CNAEs mais próximos da atividade, 6311-9/00 e 6319-4/00, **não são permitidos para MEI**. O formulário EPP do Registro.br pede CNPJ, mas não diz se aceita MEI. Levar ao contador: CNAE correto, se cabe no MEI e se o valor repassado dos domínios conta no limite. Perguntar a `epp@registro.br` se MEI é aceito. | Pode obrigar a passar para ME **antes** da homologação e da conta de revenda. | Tudo que for contrato com Registro.br e registrador |
| A4 | Gateway de cobrança (Asaas, Mercado Pago, outro) e se há saldo pré-pago do cliente. | Muda régua de renovação, reembolso e emissão de nota. | `06-cobranca-renovacao-cancelamento.md` |
| A5 | Domínio entra embutido no pacote de entrada no primeiro ano e como linha separada na renovação? | Recomendação do Comercial, sem decisão. | Cobrança e ficha comercial |
| A6 | Haverá plantão fora do horário? Se não, o SLA não pode prometer atendimento 24h. | Domínio caindo é urgência real. | `05-sla-e-suporte.md`, `06-plantao-e-incidentes.md` |
| A7 | O cliente poderá ter vários usuários por conta (sócio, agência, contador) com papéis? | Define modelo de permissões e quem pode transferir domínio. | Termos, central de ajuda de conta |
| A8 | API pública para o cliente (tokens) entra no lançamento ou depois? | Hetzner documenta API como produto; aumenta superfície de abuso. | Segurança da conta |
| A9 | Endereço público de atendimento e de abuso (`[e-mail de atendimento]`, `[e-mail de abuso]`). | Obrigatório no Decreto 7.962/2013 e exigido pelos registros. | Todas as minutas externas |
| A10 | Quando pedir a verificação do app OAuth do Google (escopos `analytics.edit` e `analytics.manage.users`, e `adwords` para Google Ads)? Qual projeto do Google Cloud é o dono do app? | Escopo sensível sem verificação limita o login a usuários de teste cadastrados. A análise do Google leva semanas [confirmar prazo]. | Lançamento do módulo Marketing |
| A11 | Google Ads: o cliente que ainda não tem conta cria a dele, ou a Ávila cria sob a conta de administrador (MCC) da Ávila e dá acesso de administrador ao cliente? Pedir o token de desenvolvedor da API do Google Ads (nível Básico)? | Conta criada sob o MCC da Ávila contraria D10 se o cliente não virar administrador. O token de desenvolvedor tem aprovação própria do Google. | Central de ajuda de Google Ads, interno 14 |
| A12 | Mercado Livre Ads: a API documentada para o **Brasil** só lê anunciante, campanhas e métricas. Criar e editar campanhas por API só aparece na documentação do **Global Selling**. Confirmar com o Mercado Livre se a escrita vale para vendedor brasileiro. | Define se o painel cria campanha ou só guia o cliente até a tela do Mercado Livre e depois acompanha as métricas. | Módulo Marketing, central de ajuda de Mercado Livre Ads |
| A13 | O fluxo atual "Configurar Google" do app.avilaops.com (n8n e conta de serviço) cria o GA4 **na conta da Ávila**. Continua como serviço gerenciado ou migra as propriedades de clientes para as contas deles? | Contradiz D10 para quem entrar no self-service. A conta de serviço enxergava 16 propriedades na conta AvilaOps em 16/09/2026, entre empresas do grupo e clientes; separar quais são de clientes. | Interno 14, norma GA4 |
| A14 | Preço dos três planos do módulo: só o assistente; assistente com revisão e instalação pela equipe; completo com Google Ads, Mercado Livre Ads e acompanhamento mensal. | Regra de três planos da casa. | Cobrança, página de serviços |

## Fora do escopo (Hetzner documenta, a gente não oferece aqui)

Servidores cloud e dedicados, colocation, volumes, object storage, load
balancer, redes privadas, marketplace de apps. Se algum dia entrar, ganha
seção própria no `INDICE.md`. Hospedagem de site e e-mail continuam nos
produtos que já existem; o account só aponta o DNS para eles.
