# Regras de terceiros: fatos com fonte

**Atualizado em:** 16/09/2026

> Todo prazo ou regra de Registro.br, NIC.br, ICANN, registrador ou Receita que
> entra numa minuta vem daqui. Revalidar antes de publicar qualquer minuta.

## Como ler

| Classe | Significado | Pode sustentar contrato ou regra do produto? |
|---|---|---|
| **OFICIAL** | publicada pela entidade que define a regra (ICANN, NIC.br/Registro.br, CGI.br) ou pelo próprio fornecedor sobre o próprio serviço | sim |
| **SECUNDÁRIA** | blog, notícia, site de contador ou de outro provedor | não; só aponta onde procurar |
| **HISTÓRICA** | oficial, mas superada por publicação mais recente da mesma entidade | não; guardada para explicar divergências |

**PENDENTE DE CONFIRMAÇÃO** = não há fonte oficial suficiente. O texto diz o
que falta. Nada marcado assim vira regra de contrato ou de código.

**Estabilidade:** *estável* (política consolidada, muda raramente), *em
revisão* (há processo formal de mudança, ver §11), *variável* (depende de
fornecedor ou é dado estatístico).

Cada regra aqui corresponde a um parâmetro em
`40-produto/POLITICAS-E-PARAMETROS.md`. Quando a regra mudar, muda aqui e lá,
não no código espalhado.

---

## 1. ICANN: vencimento de genéricos (ERRP)

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F1 | OFICIAL | ICANN | [Expired Registration Recovery Policy](https://www.icann.org/resources/pages/errp-2013-02-28-en) | 16/09/2026 | estável |

| Regra | Texto | Seção |
|---|---|---|
| Aviso antes do vencimento | dois avisos: aproximadamente 1 mês antes (aceito entre 26 e 35 dias) e 1 semana antes (aceito entre 4 e 10 dias) | 2.1.1 |
| Aviso depois do vencimento | pelo menos um aviso em até 5 dias após o vencimento | 2.1.2 |
| Interrupção de DNS | se o domínio for apagado em até 8 dias do vencimento, DNS interrompido desde o vencimento; se depois, pelo menos nos últimos 8 dias consecutivos em que ainda pode ser renovado | 2.2 |
| Página de aviso | se o tráfego for para página própria, ela deve dizer claramente que o domínio venceu e como renovar | 2.2 |
| Renovação após vencimento | o titular deve poder renovar desde o vencimento até o fim da interrupção de DNS | 2.2.5 |
| Resgate (RGP) | o registro oferece 30 dias de resgate logo após a exclusão; DNS desligado e transferência proibida | 3.1 |
| Transparência de preço | preço de renovação, de renovação após vencimento e de resgate visíveis no site, **inclusive no site do revendedor** | 4.1 |
| Transparência de aviso | o site descreve canais e destinatário dos avisos de vencimento | 4.2, 4.2.1 |

**Consequência:** a tabela de avisos do externo 02 §5 e a página de preços
por extensão são obrigação para os genéricos.

## 2. ICANN: transferência de genéricos

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F2 | OFICIAL | ICANN | [Transfer Policy](https://www.icann.org/en/contracted-parties/accredited-registrars/resources/domain-name-transfers/policy) (versão de 21/02/2024, cumprimento obrigatório desde 21/08/2025) | 16/09/2026 | **em revisão** (§11) |
| F3 | OFICIAL | ICANN | [FAQs for Registrants: Transferring Your Domain Name](https://www.icann.org/resources/pages/name-holder-faqs-2017-10-10-en) | 16/09/2026, conferido pelo Nicolas | em revisão (§11) |

**Regra operacional vigente: 60 dias.**

| Regra | Vigente | Fonte |
|---|---|---|
| Após a criação | transferência pode ser negada nos primeiros 60 dias | F2, F3 |
| Após transferência entre registradores | restrição nos 60 dias seguintes | F2, F3 |
| Após troca de titular | trava de 60 dias. O registrador **pode** oferecer dispensa (*opt-out*) antes da troca; **não é garantido** que ofereça | F2, F3 |
| Código de autorização | entregue em até 5 dias corridos se não houver autoatendimento | F2 |
| Pode negar | fraude; disputa de identidade; falta de pagamento de período anterior (se vencido) ou do período corrente (se não vencido); objeção expressa do titular; dentro dos 60 dias | F2 |
| Deve negar | UDRP, URS ou processo judicial pendente; disputa de transferência; trava de troca de titular não dispensada | F2 |
| **Não pode negar** | falta de pagamento de período **futuro**; falta de resposta do titular; domínio travado sem oportunidade de destravar | F2 |

A dispensa da trava de troca de titular depende do **registrador parceiro**
(A1). PENDENTE DE CONFIRMAÇÃO até ler o contrato dele.

## 3. ICANN: verificação de dados do titular

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F4 | OFICIAL | ICANN | [About Verification of Contact Information](https://www.icann.org/resources/pages/contact-verification-2013-05-03-en) | 16/09/2026 | estável |
| F5 | OFICIAL | ICANN | [2013 RAA Whois Accuracy Program Specification](https://itp.cdn.icann.org/en/files/accredited-registrars/whois-inaccuracy-rdds-31oct13-en.pdf) | 16/09/2026 | estável |

- E-mail ou telefone do titular verificado em até **15 dias** após registro,
  transferência ou alteração de dados, ou após devolução/indício de erro.
- Sem resposta afirmativa: verificação manual ou **suspensão** do domínio.
- Dado falso intencional ou falta de resposta a consulta de precisão por mais
  de 15 dias: suspensão ou exclusão.

## 4. Registro.br: Provedor de Serviços via EPP

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F6 | OFICIAL | Registro.br | [Formulário de credenciamento EPP](https://registro.br/tecnologia/epp-formulario.txt) | 16/09/2026 | estável |
| F7 | OFICIAL | Registro.br | [Formulário de homologação EPP](https://registro.br/tecnologia/epp-formulario-homologacao.txt) | 16/09/2026 | estável |
| F8 | OFICIAL | Registro.br | [Procedimento de homologação EPP](https://ftp.registro.br/pub/libepp-nicbr/pt-epp-accreditation-proc.txt) | 16/09/2026 | estável |
| F9 | OFICIAL | Registro.br | [Políticas e restrições ao serviço EPP](https://ftp.registro.br/pub/libepp-nicbr/pt-policy-restrictions-espec.txt) | 16/09/2026 | estável |

| Item | Regra | Fonte |
|---|---|---|
| Ordem | 1) homologação no servidor `beta.registro.br`; 2) credenciamento em produção | F6, F8 |
| Pedido | formulário em texto no corpo do e-mail: homologação para `epp-suporte@registro.br`, produção para `epp@registro.br` | F6, F7 |
| Dados exigidos | **CNPJ**, razão social, nome do provedor (1 palavra, até 25 caracteres, **não pode ser alterado**), site, telefone e e-mail de SAC, responsável, endereço, representante(s) legal(is) com RG e CPF, ID do usuário técnico no Registro.br | F6 |
| Rede | até 4 endereços ou blocos IP, até /26 cada | F6 |
| Homologação | roteiro obrigatório de comandos (conexão, contatos, organizações, domínios, mensagens); o provedor informa data, hora e IP do teste; análise posterior | F8 |
| Contrato | assinado entre NIC.br e o provedor, com dados do representante legal | F6 |
| Renovação | de 1 a 10 anos; exige crédito suficiente | F9 |
| Remoção | só nos 5 primeiros dias após criação, até 3% dos registrados nos últimos 5 dias | F9 |
| DNS | mínimo 2 e máximo 5 servidores; 1 IPv4 e 1 IPv6 por servidor; até 2 registros DS; DNS precisa responder, senão fica pendência | F9 |
| Contatos | nome com pelo menos duas palavras, até 40 caracteres; depois que o contato se recadastra na web, o provedor não altera mais | F9 |
| Mudança de provedor | escolhida pelo titular na interface web do Registro.br; provedores antigo e novo avisados por mensagem EPP | F9 |

PENDENTE DE CONFIRMAÇÃO: tipo de empresa aceito (MEI?), taxas, garantias,
cláusulas do contrato. Não aparecem em F6 a F9. Perguntar a `epp@registro.br`.

## 5. Registro.br e NIC.br: vencimento, liberação e SACI-Adm

### 5.1 Vencimento e liberação de `.br`

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F10 | OFICIAL | NIC.br | [Panorama Setorial da Internet, ano XVII, n. 1 (2025): Infraestrutura digital: avanços e desafios para a universalização da conectividade](https://nic.br/media/docs/publicacoes/6/20250512105226/ano-xvii-n-1-infraestrutura-digital-avancos-desafios-universalizacao-conectividade.pdf) | 16/09/2026, texto extraído do PDF | estável (o NIC.br descreve como característica do `.br` "desde o início") |
| F11 | OFICIAL | Registro.br | [Processo de liberação: ofertas](https://registro.br/dominio/processo-de-liberacao/ofertas/) | 16/09/2026, conferido pelo Nicolas no navegador (página não extraível por ferramenta) | variável (datas dos ciclos) |
| F12 | SECUNDÁRIA | provedores de hospedagem (Task, Locaweb, HostGator e outros) | páginas de ajuda sobre domínio congelado | 16/09/2026 | **descartada**: prazos divergentes entre si, superados por F10 |

Trecho de F10: *"quando o domínio expira, ele é mantido durante 90 dias na
titularidade do cliente: deixa de funcionar, mas não fica disponível para
registro por outra pessoa."*

| Etapa | Regra | Fonte |
|---|---|---|
| Expiração | domínio não renovado expira | F10 |
| Suspensão | deixa de funcionar | F10 |
| Manutenção da titularidade | até **90 dias** na titularidade do cliente; não fica disponível a terceiros | F10 |
| Remoção | ao fim desse período, o domínio pode ser removido | F10, F11 |
| Processo de Liberação | domínios removidos por não renovação, cancelamento ou irregularidade seguem o Processo de Liberação, em ciclos definidos pelo Registro.br | F11 |

**Não existe "no 91º dia fica disponível".** Remoção e disponibilização a
terceiros são etapas diferentes; a segunda depende do ciclo do Processo de
Liberação.

PENDENTE DE CONFIRMAÇÃO:
- se o titular pode reativar pagando em qualquer momento dos 90 dias e se há
  taxa extra (não está em F10);
- como a reativação funciona quando a Ávila é o Provedor de Serviços (comando
  EPP ou só pela interface do Registro.br).

### 5.2 SACI-Adm

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F13 | OFICIAL | CGI.br / NIC.br | [Caderneta SACI-Adm 15 anos (2026)](https://www.cgi.br/media/docs/publicacoes/24/pt-br/20260506121815/caderneta-SACI-15-anos-2026_digital.pdf) | 16/09/2026, texto extraído do PDF | variável (lista de instituições e média de prazo) |
| F14 | OFICIAL | NIC.br | [Evento em São Paulo celebra 15 anos de SACI-Adm](https://nic.br/noticia/releases/evento-em-sao-paulo-celebra-15-anos-de-saci-adm-referencia-na-disputa-de-dominios-de-internet-no-brasil/), 30/09/2025 | 16/09/2026 | variável |
| F15 | HISTÓRICA | NIC.br | [SACI-Adm completa 10 anos](https://www.nic.br/noticia/releases/sistema-de-resolucao-de-conflitos-para-nomes-de-dominios-no-br-saci-adm-completa-10-anos/) | 16/09/2026 | superada: lista ABPI, **CCBC** e WIPO e prazo médio de 45 dias |

| Regra | Texto | Fonte |
|---|---|---|
| O que é | procedimento especial e **administrativo**, vinculado ao contrato de registro de domínio `.br`, para conflitos sobre titularidade | F13 |
| Não é | arbitragem (resposta expressa do NIC.br) nem mecanismo da ICANN | F13 |
| Papel do NIC.br | técnico e administrativo: regras gerais, supervisão das instituições, execução da decisão. Não julga | F13 |
| Quem conduz | instituições credenciadas pelo NIC.br; o reclamante escolhe | F13 |
| Credenciadas e ativas em 05/2026 | **ABPI** (CASD-ND) e **OMPI/WIPO** | F13, F14 |
| CCBC | aparece só em fonte HISTÓRICA (F15). **Não apresentar como disponível** | F15 |
| Regras e custos | cada instituição tem regulamento suplementar e tabela própria; a taxa é paga pelo reclamante à instituição. **Não existe preço único** do SACI-Adm | F13 |
| Resultado | manutenção, transferência ou cancelamento do domínio | F13, F14 |
| Esclarecimentos | 5 dias após a publicação da decisão | F13 |
| Judiciário ou arbitragem | as partes têm **15 dias úteis** após a decisão para entrar com ação judicial ou arbitral; sem ação, o NIC.br executa a decisão | F13 |
| Duração média | aproximadamente **74 dias**, da apresentação à decisão de mérito. É **média histórica, não prazo garantido** | F13 |

PENDENTE DE CONFIRMAÇÃO: média de cerca de **80 dias** citada em outro
material recente do NIC.br (informado pelo Nicolas, fonte não anexada). Até
anexar, os textos usam "aproximadamente 74 a 80 dias, conforme dados do
NIC.br", sempre como média.

**Regra de produto:** a lista de instituições nunca fica fixa em tela ou
código. Vem de configuração atualizável (`40-produto/POLITICAS-E-PARAMETROS.md`).

## 6. OpenSRS (candidato a registrador parceiro, A1)

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F16 | OFICIAL (fornecedor) | OpenSRS / Tucows | [Payment terms](https://opensrs.com/payment-terms/) | 16/09/2026 | variável |
| F17 | OFICIAL (fornecedor) | OpenSRS / Tucows | [.BR domain policies para revendedores](https://support.opensrs.com/support/solutions/articles/201000063494--br-domain-policies) | 16/09/2026 | variável |
| — | OFICIAL (fornecedor) | OpenSRS / Tucows | [Contract](https://opensrs.com/contract/) | **não lido** | — |

| Item | Regra | Fonte |
|---|---|---|
| Ativação | US$ 95, uma vez, convertidos em crédito, não reembolsáveis; sem anuidade | F16 |
| Pagamento | **pré-pago**, só em dólar; cartão ou PayPal com taxa de 3%; transferência internacional, cheque, ordem de pagamento | F16 |
| Saldo | recomendam manter pelo menos um mês de crédito; crédito não é reembolsável | F16 |
| `.com.br` pelo OpenSRS | oferecido; exige CPF/CNPJ validado na Receita e endereço brasileiro; mínimo 2 servidores DNS respondendo; pedido expira em 14 dias se DNS não validar; pode levar até 45 dias | F17 |
| Transferência de `.br` para o OpenSRS | **não suportada** | F17 |
| Titular que já tem domínio `.br` em outro provedor | precisa pedir mudança ao Registro.br antes | F17 |

**Consequência para A1/D2:** o OpenSRS resolve `.com.br` **novo**, mas não
traz os `.br` que os clientes já têm. Para a base atual, a homologação
própria no Registro.br continua necessária.

## 7. Enquadramento MEI (A3)

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F18 | SECUNDÁRIA | Meu Contador Online | [CNAE 6311-9/00](https://www.meucontadoronline.com.br/consulta-cnae/atividades-de-prestacao-de-servicos-de-informacao/6311900-tratamento-de-dados-provedores-de-servicos-de-aplicacao-e-servicos-de-hospedagem-na-internet/) | 16/09/2026 | variável |
| F19 | SECUNDÁRIA | Meu Contador Online | [CNAE 6319-4/00](https://www.meucontadoronline.com.br/consulta-cnae/atividades-de-prestacao-de-servicos-de-informacao/6319400-portais-provedores-de-conteudo-e-outros-servicos-de-informacao-na-internet/) | 16/09/2026 | variável |

- Segundo F18 e F19, os CNAEs 6311-9/00 e 6319-4/00 **não são permitidos
  para MEI**.

PENDENTE DE CONFIRMAÇÃO (contador): CNAE correto de revenda de domínio e DNS,
se cabe no MEI, e se o valor repassado do domínio conta no limite de
faturamento. Fonte oficial a buscar: anexo de ocupações do MEI (Resolução
CGSN) e o próprio Registro.br (F6 não diz se aceita MEI).

## 8. Google Analytics 4 (módulo Marketing)

Consultado em 16/09/2026. Cópias em `docs/Docs/docs.avilaops.com/Google Analytics/`.

| Regra | Texto | Fonte |
|---|---|---|
| Funções | Administrador, Editor, Profissional de marketing, Analista, Leitor; restrições "sem métricas de custo" e "sem métricas de receita" | [Gerenciamento de acesso](https://support.google.com/analytics/answer/9305587?hl=pt-br) |
| Quem marca evento principal | Profissional de marketing ou superior | [Marcar eventos como principais](https://support.google.com/analytics/answer/13128484?hl=pt-br) |
| Limite de eventos principais | 30 por propriedade padrão, 50 no Analytics 360 | idem |
| Eventos principais por padrão | `purchase` (Web e app); `first_open`, `in_app_purchase` e assinaturas de loja (só app) | idem |
| Retenção de dados | 2 ou 14 meses na propriedade padrão; idade, gênero e interesse sempre 2 meses | [Retenção de dados](https://support.google.com/analytics/answer/7667196?hl=pt-br) |
| Conta nova | exige aceite dos Termos de Serviço e da Emenda sobre processamento de dados | [Configurar o Google Analytics](https://support.google.com/analytics/answer/9304153?hl=pt-br) |
| Fuso horário | mudar no máximo uma vez por dia; só vale para dados futuros | idem |

### API de administração (Analytics Admin API)

Fonte: documento de descoberta `analyticsadmin.googleapis.com`, versões `v1beta` e `v1alpha`, lido em 16/09/2026.

| Etapa do assistente | Método | Versão |
|---|---|---|
| Criar conta (gera link de aceite dos Termos) | `accounts.provisionAccountTicket` | v1beta |
| Criar propriedade | `properties.create` | v1beta |
| Criar fluxo Web e obter o ID `G-` | `properties.dataStreams.create` | v1beta |
| Medição otimizada | `properties.dataStreams.updateEnhancedMeasurementSettings` | **v1alpha** |
| Retenção de 14 meses | `properties.updateDataRetentionSettings` | v1beta |
| Sinais do Google | `properties.updateGoogleSignalsSettings` | **v1alpha** |
| Eventos principais | `properties.keyEvents.create` | v1beta |
| Vincular Google Ads | `properties.googleAdsLinks.create` | v1beta |
| Dar função à Ávila | `properties.accessBindings.create` | **v1alpha** |

- Escopos: `analytics.edit`; para funções de acesso, `analytics.manage.users`.
- **Sem API encontrada:** definir tráfego interno, listar referências indesejadas, configurar vários domínios. No painel viram passo guiado com link para a tela do Google.
- Métodos só em `v1alpha` podem mudar sem aviso. **[revalidar antes de desenvolver]**

## 9. Google Ads

| Regra | Texto | Fonte |
|---|---|---|
| Permissão para vincular ao GA4 | Administrador ou Editor na propriedade **e** acesso administrativo no Google Ads | [Conectar o Google Ads ao Analytics](https://support.google.com/analytics/answer/9379420?hl=pt-br) |
| Limite de vínculos | 400 por propriedade; vínculo a conta de administrador conta como um | idem |
| Conversões | importadas no Google Ads a partir dos eventos principais do GA4 | [Criar conversões com base nos eventos principais](https://support.google.com/analytics/answer/10632359?hl=pt-br) |
| Criar conta pela API | só sob uma conta de administrador (MCC) [confirmar] | [Google Ads API](https://developers.google.com/google-ads/api/docs/start) [confirmar] |
| Token de desenvolvedor | exigido pela API do Google Ads, com aprovação por nível de acesso [confirmar] | idem |

## 10. Mercado Livre Ads (Product Ads)

Fontes: [Product Ads para Catálogo e User Products (Brasil)](https://developers.mercadolivre.com.br/pt_br/product-ads-para-catalogo-e-user-products-leitura), atualizada em 06/07/2026; [Product Ads (Global Selling)](https://global-selling.mercadolibre.com/devsite/manage-sales-global-selling/new-product-ads). Consultadas em 16/09/2026.

| Regra | Texto | Fonte |
|---|---|---|
| Disponível no Brasil | sim (site `MLB`) | Brasil |
| Tipos de gestão | **Automático** (padrão ao começar; o Mercado Livre escolhe as publicações) e **Personalizado** (várias campanhas, orçamento e objetivo por campanha) | Brasil |
| Anunciante | `GET /advertising/advertisers?product_id=PADS` devolve o `advertiser_id` | Brasil |
| Produto não habilitado | erro 404 "No permissions found for user_id": o vendedor precisa ativar em Mercado Livre > Meu perfil > Publicidade | Brasil |
| Endpoints antigos | desativados em 27/05/2026; respondem 404 | Brasil |
| Agrupamento | variantes do mesmo produto ficam numa única campanha, identificadas por `ad_group_id` | Brasil |
| Métrica padrão | ROAS (`roas_target`) substitui ACOS desde janeiro/2026; `acos_target` visível só até 30/03/2026 | Brasil |
| Orçamento | média diária de um orçamento mensal; o que sobra num dia é gasto nos seguintes até o fim do mês | Brasil |
| **Escrita (criar, editar, apagar campanha)** | `POST`, `PUT` e `DELETE` em `/marketplace/advertising/...` aparecem **só na documentação do Global Selling**. A documentação do Brasil só traz consultas. | Global Selling · **decisão A12** |
| Autorização | OAuth do Mercado Livre; token vale 6 horas; sem `offline_access` não há refresh token | `lojas.avilaops.com/src/lib/mercadolivre.ts`, provado em 02/09/2026 |

## 11. Mudanças regulatórias monitoradas

Mudança em discussão ou aprovada, mas **sem vigência formal aplicável**. Não
entra em contrato, central de ajuda nem código como regra. O sistema continua
com a regra vigente, parametrizada.

### 11.1 Transfer Policy Review (ICANN)

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F20 | OFICIAL | ICANN / GNSO | [Transfer Policy Review PDP, relatório final, 04/02/2025](https://gnso.icann.org/sites/default/files/policy/2025/correspondence/tpr-team-to-gnso-council-04feb25-en.pdf) | 16/09/2026 | recomendação, não é política vigente |
| F21 | SECUNDÁRIA | Domain Incite | [ICANN to kill off 60-day domain transfer lock](https://domainincite.com/30891-icann-to-kill-off-60-day-domain-transfer-lock), 13/03/2025 | 16/09/2026 | notícia |

| Campo | Situação |
|---|---|
| O que muda | travas após criação e após transferência passariam a 720 horas (30 dias); mudanças no tratamento de troca de titular e do código de autorização |
| Estado | recomendações aceitas pelo GNSO Council em 2025; a política oficial publicada (F2) e a página para titulares (F3) continuam com **60 dias** |
| Regra operacional hoje | **60 dias** (§2) |
| Quando adotar | só quando a ICANN publicar a nova Transfer Policy com data de vigência aplicável a registradores, e o registrador parceiro confirmar a implementação |
| Onde mudar | parâmetros `icann.transfer.*` em `40-produto/POLITICAS-E-PARAMETROS.md`, este documento §2, contrato 02 §4 e §6, central de ajuda "Trava de transferência" |
| Revisar em | a cada 3 meses, ou ao receber aviso do registrador parceiro |

## 12. ICANN: disputas de genéricos (UDRP)

| ID | Classe | Entidade | Título | Consultado | Estabilidade |
|---|---|---|---|---|---|
| F22 | OFICIAL | ICANN | [Uniform Domain-Name Dispute-Resolution Policy](https://www.icann.org/resources/pages/policy-2012-02-25-en), atualizada em 21/02/2024 | 16/09/2026 | estável |

| Regra | Texto | Parágrafo |
|---|---|---|
| Três requisitos | domínio idêntico ou confusamente semelhante a marca do reclamante; titular sem direito ou interesse legítimo; registrado **e** usado de má-fé | 4(a) |
| Resultados | limitados a cancelamento ou transferência do domínio | 4(i) |
| Espera antes de cumprir | o registrador espera 10 dias úteis após ser informado da decisão, para eventual ação judicial | 4(k) |
