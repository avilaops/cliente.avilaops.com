# Glossário

Termos usados em tela, e-mail, contrato e central de ajuda. Um termo, um
significado. Se precisar de palavra nova, entra aqui antes.

## Papéis

| Termo | Significado | Não confundir com |
|---|---|---|
| **Titular** | Pessoa física ou jurídica dona do domínio, identificada por CPF/CNPJ. É sempre o cliente. | "Cliente da conta": a conta pode ser de uma agência que gerencia domínios de vários titulares. |
| **Conta** | Cadastro no account.avilaops.com. Agrupa domínios, zonas, cobrança e usuários. | Titular |
| **Usuário** | Pessoa que entra na conta pelo SSO. Uma conta pode ter mais de um [depende de A7]. | |
| **Contato técnico** | Papel que a Ávila ocupa no registro do domínio. | Titular |
| **Registro (entidade)** | Quem administra a extensão: Registro.br para `.br`, Verisign para `.com`, etc. | Registrador |
| **Registrador credenciado** | Empresa credenciada pela ICANN que registra genéricos junto ao registro. A Ávila **não** é. | Revendedor |
| **Revendedor** | Empresa que vende e gerencia domínios genéricos por meio de um registrador credenciado. É o papel da Ávila. | |
| **Provedor de Serviços** | Empresa homologada pelo Registro.br para registrar e gerenciar `.br` em nome dos seus clientes. É o papel da Ávila para `.br`. | |

## Domínio

| Termo | Significado |
|---|---|
| **Extensão** | O final do domínio: `.com.br`, `.com`, `.app`. Evitar "TLD" em tela. |
| **Registro de domínio** | Contratação do direito de uso de um nome por um período (normalmente 1 ano). |
| **Renovação** | Extensão do período antes ou logo após o vencimento. |
| **Renovação automática** | Cobrança e renovação feitas pelo sistema antes do vencimento, sem ação do cliente. |
| **Vencimento** | Data em que o período contratado termina. |
| **Período de recuperação** | Janela após o vencimento em que o domínio ainda pode voltar ao mesmo titular, às vezes com taxa. Prazos variam por extensão. |
| **Transferência de entrada** | Trazer um domínio de outro provedor para a Ávila. |
| **Transferência de saída** | Levar um domínio da Ávila para outro provedor. |
| **Código de autorização** | Senha do domínio usada na transferência de genéricos (também chamado de *auth code* ou *EPP code*). Em tela: "código de autorização". |
| **Trava de transferência** | Bloqueio que impede transferência sem ação do titular. |
| **Troca de titular** | Mudança do CPF/CNPJ dono do domínio. |
| **Servidores DNS** | Os servidores de nome que respondem pelo domínio (registros NS na delegação). Em tela: "servidores DNS", não "nameservers". |
| **Delegação** | Informar ao registro quais servidores DNS respondem pelo domínio. |
| **DNSSEC** | Assinatura criptográfica das respostas DNS. Liga-se ao registro publicando um registro DS. |
| **WHOIS / RDAP** | Consulta pública de dados do domínio. RDAP é o protocolo que substitui o WHOIS. |
| **SACI-Adm** | Procedimento administrativo do NIC.br para conflitos sobre domínios `.br`, conduzido por instituições credenciadas. Não é arbitragem nem mecanismo da ICANN. |
| **Reserva ao titular (`.br`)** | Até 90 dias após a expiração em que o domínio `.br` fica fora do ar, mas continua do titular e não pode ser registrado por outra pessoa. |
| **Remoção (`.br`)** | Saída do domínio da base do Registro.br ao fim da reserva. Não é o mesmo que ficar disponível. |
| **Processo de Liberação** | Ciclos do Registro.br em que domínios removidos são oferecidos a novos interessados. |
| **UDRP** | Política de solução de disputas de genéricos da ICANN. |

## DNS

| Termo | Significado |
|---|---|
| **Zona** | Conjunto de registros DNS de um domínio. |
| **Registro DNS** | Uma linha da zona: nome, tipo, valor, TTL. Em tela: "registro", nunca "entrada". |
| **Tipo de registro** | A, AAAA, CNAME, MX, TXT, NS, SRV, CAA, DS, HTTPS, SVCB, TLSA, PTR. |
| **TTL** | Tempo, em segundos, que resolvedores guardam a resposta em cache. |
| **Propagação** | Tempo até caches do mundo expirarem e verem o valor novo. Depende do TTL antigo. |
| **Arquivo de zona** | A zona em formato texto padrão (BIND), usado para importar e exportar. |
| **Apex / raiz** | O próprio domínio, sem subdomínio (`exemplo.com.br`). Representado por `@`. |
| **Versão da zona** | Cada alteração salva gera uma versão, que pode ser restaurada. |

## Segurança e conta

| Termo | Significado |
|---|---|
| **Verificação em duas etapas** | Segundo fator no login. Evitar "2FA" em tela. |
| **Código de atendimento** | Código mostrado no painel que o cliente informa ao suporte para provar que é dono da conta. Equivalente ao *Support OTP* da Hetzner. |
| **Token de API** | Credencial para automação, com escopo e validade. |
| **Trilha de auditoria** | Registro imutável de quem mudou o quê. |

## Marketing

| Termo | Significado | Não confundir com |
|---|---|---|
| **Propriedade** | Site ou app medido no Google Analytics 4. Fica dentro de uma conta do Analytics do cliente. | Conta (do account) |
| **Fluxo de dados** | Origem dos dados de uma propriedade: um site ou um app. O fluxo Web tem o **ID da métrica** `G-`. | |
| **Evento principal** | Ação importante marcada no GA4, como enviar formulário ou comprar. Nome atual do que o GA4 chamava de "conversão". | **Conversão**, que é o nome no Google Ads |
| **Função de acesso** | Papel de uma pessoa no GA4: Administrador, Editor, Profissional de marketing, Analista ou Leitor. | Usuário (do account) |
| **Anunciante** | Conta de Mercado Livre Ads de um vendedor, identificada pelo `advertiser_id`. | |
| **ROAS objetivo** | Receita que se espera por real investido numa campanha do Mercado Livre Ads. Substituiu o ACOS como indicador padrão. | ACOS |
| **Conectar** | Autorizar o account a agir na conta Google ou Mercado Livre do cliente, sem senha. Pode ser desfeito a qualquer momento. | Dar senha |
