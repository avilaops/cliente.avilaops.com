# Estado de implementação

**Verificado em:** 16/09/2026

> Separa o que o regimento **promete** do que **existe**. Mesma regra da
> política de IA da casa: uma política que descreve controles inexistentes é
> pior que nenhuma política. Atualizar a cada entrega.

## Infraestrutura e contratos

| Item | Estado | Evidência |
|---|---|---|
| Repositório/código do account.avilaops.com | **não existe** | só `docs/` |
| Subdomínio `account.avilaops.com` publicado | não verificado | — |
| Conta de revendedor de genéricos | **não existe** | nenhuma credencial em `docs/credenciais/` |
| Homologação Registro.br como Provedor de Serviços | **não existe** | idem |
| Servidores DNS autoritativos da Ávila | **não existe** | decisão A2 aberta |
| Registro manual atual | Registro.br e Cloudflare Registrar, por cliente | `docs/plataforma/PARTSAGRICOLA-DOMINIO.md` |
| SSO `auth.avilaops.com` | existe | `docs/plataforma/AUTH-SSO.md` |
| Revisão jurídica das minutas | **não feita** | — |
| Módulo Marketing (GA4, Google Ads, Mercado Livre Ads) no account | **não existe** | só `40-produto/REQUISITOS.md` |
| Criação de GA4 e GTM pela equipe | existe, **na conta da Ávila** | app.avilaops.com, botão "Configurar Google" pelo n8n. A conta de serviço enxergava 16 propriedades na conta AvilaOps em 16/09/2026, entre empresas do grupo e clientes (A13) |
| Painel GA4 da equipe | existe, só leitura | `app.avilaops.com/src/lib/google-analytics.ts` |
| App OAuth do Google verificado para `analytics.edit` | **não existe** | A10 |
| Token de desenvolvedor do Google Ads | **não existe** | A11 |
| App do Mercado Livre com OAuth e `offline_access` | existe no Lojas | `lojas.avilaops.com/src/lib/mercadolivre.ts`; permissão de Publicidade no app [confirmar] |

## Compromissos do regimento externo

| Documento | Compromisso | Estado |
|---|---|---|
| 02 §5 | Régua de avisos de vencimento | não implementado |
| 02 §6.2 | Código de autorização self-service | não implementado |
| 02 §7 | Versões de zona restauráveis | não implementado |
| 04 §5 | Pedidos de titular em 15 dias | processo manual possível hoje |
| 05 §1 | Disponibilidade DNS | sem infraestrutura |
| 05 §3 | Código de atendimento | não implementado |
| 07 | Canal de abuso lido todo dia | caixa não definida (A9) |
| 08 §1 | Verificação em duas etapas | [confirmar se o SSO já oferece] |
| 08 §4 | E-mails oficiais com SPF/DKIM/DMARC | [verificar domínio avilaops.com] |
| 09 | Trilha de auditoria imutável | não implementado |
| 09 | Termo de confidencialidade para quem acessa dados | modelo existe (`docs/juridico/NDA.md`), sem assinatura registrada |
| interno 09 | Retaguarda com acesso de emergência | minuta de contrato existe, não assinada |

## Lacunas a preencher nas minutas

Tudo que está entre colchetes nos documentos. Principais:

- `[e-mail de atendimento]`, `[e-mail de abuso]`, `[e-mail do encarregado]`,
  `[e-mail jurídico]`, remetentes oficiais: **A9**
- `[registrador parceiro]`, prazos de recuperação, taxas de resgate: **A1**
- nomes dos servidores DNS, metas de SLA: **A2**
- gateway, formas de pagamento, saldo pré-pago: **A4**
- horário de atendimento e plantão: **A6**
- todo `[confirmar com advogado]`: revisão jurídica

## PENDENTE DE CONFIRMAÇÃO em regras de terceiros (16/09/2026)

| Item | O que falta | Onde perguntar |
|---|---|---|
| Reativação de `.br` durante a reserva de 90 dias | forma (EPP ou interface) e custo quando a Ávila é provedor | `epp@registro.br` |
| Dispensa da trava de troca de titular | se o registrador parceiro oferece | contrato do registrador (A1) |
| SACI-Adm, média de ~80 dias | anexar a fonte oficial citada pelo Nicolas | NIC.br |
| MEI como Provedor de Serviços | aceitação pelo Registro.br | `epp@registro.br` + contador (A3) |
| Regras `.br` por subcategoria e documentação da troca de titular | fonte oficial | site do Registro.br |
| Transferência de genérico acrescenta um ano | confirmar por extensão | registrador parceiro (A1) |
