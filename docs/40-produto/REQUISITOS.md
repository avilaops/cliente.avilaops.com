# Requisitos do produto

**Estado:** minuta · **Atualizado em:** 16/09/2026

> Deriva do regimento: cada requisito cita o documento que ele cumpre. Stack e
> arquitetura ficam para quando as decisões A1 e A2 forem tomadas.

## Módulos

| Módulo | Faz | Cumpre |
|---|---|---|
| **Conta** | cadastro PF/PJ, usuários [A7], dados do titular reaproveitáveis, encerramento | externo 01 §3, §10 |
| **Segurança** | SSO, verificação em duas etapas, confirmação de ações sensíveis, sessões, código de atendimento, tokens [A8] | externo 08 |
| **Domínios** | busca, registro, renovação automática, transferência entrada/saída, código de autorização, trava, titular, servidores DNS, DNSSEC, glue | externo 02 |
| **DNS** | zonas, registros com validação, importação/exportação BIND, versões e restauração | externo 02 §7, 05 |
| **Cobrança** | pagamento antes do comando, régua de renovação, reembolso automático em falha, notas | externo 06 |
| **Avisos** | e-mail e [WhatsApp/SMS] de vencimento, ações sensíveis, incidentes | externo 02 §5, 08 §2 |
| **Painel interno** | filas (renovação com problema, fraude, abuso, transferências paradas), ações da equipe com motivo obrigatório | interno 01-11 |
| **Abuso** | formulário público, fila, suspensão de DNS | externo 03, 07 |
| **Auditoria** | trilha imutável de todo evento | interno 08 |
| **Legal** | versões públicas dos documentos, registro de aceite | externo README |
| **Marketing** | assistentes de Google Analytics 4, Google Ads e Mercado Livre Ads na conta do próprio cliente; painel de situação e métricas | D9, D10, interno 14 |

## Módulo Marketing

### Google Analytics 4

1. **Conectar Google**: login com a conta Google da empresa. Pede só `analytics.edit` e `analytics.manage.users` [A10].
2. **Conta**: se o cliente não tem conta no Analytics, gera o aceite dos Termos (`provisionAccountTicket`) e espera o cliente aceitar.
3. **Propriedade e fluxo**: nome `NomeCliente - Site`, fuso de São Paulo, moeda BRL, fluxo Web com medição otimizada. Guarda o ID `G-`.
4. **Ajustes**: retenção de 14 meses; Sinais do Google só se o site tiver aviso de cookies.
5. **Eventos principais** sugeridos pelo tipo de negócio (`generate_lead`, `contact`, `schedule`, `purchase`, `sign_up`). O cliente confirma antes de criar.
6. **Tag no site**:
   - site hospedado pela Ávila: instalação automática;
   - fora da Ávila: instrução pronta para o CMS, o Tag Manager ou o `<head>`.
7. **Passos sem API**: tráfego interno, referências indesejadas (Mercado Pago) e vários domínios. Checklist guiado, cada item com link direto para a tela do Google e caixa "feito".
8. **Acesso da Ávila**: o cliente escolhe o serviço contratado e o painel cria só a função correspondente (tabela da norma GA4, seção 4).
9. **Validação**: lê o Tempo real e mostra "Recebendo dados" ou o que falta.

### Google Ads

1. Mesmo login Google, com escopo do Google Ads [A10].
2. Lista as contas do Google Ads a que o cliente tem acesso administrativo. Sem conta, segue a decisão A11.
3. Vincula ao GA4 (`googleAdsLinks.create`) e liga a marcação automática.
4. Importa os eventos principais como conversões.
5. Mostra gasto, cliques e conversões por campanha.

### Mercado Livre Ads

1. **Conectar Mercado Livre**: OAuth com `offline_access`, no mesmo padrão já usado em `lojas.avilaops.com`.
2. Consulta o anunciante (`product_id=PADS`). Se o Mercado Livre responder 404 "No permissions found", orienta o cliente a ativar em Meu perfil > Publicidade e tenta de novo.
3. Lista as campanhas com orçamento, ROAS objetivo, estado e métricas (cliques, impressões, custo, vendas diretas e indiretas, ROAS).
4. **Criar ou editar campanha**:
   - pela API, se a escrita valer para vendedor brasileiro [A12];
   - se não valer, passo guiado com link para a tela de Publicidade do Mercado Livre, e o painel passa a acompanhar a campanha criada.
5. Alertas: campanha sem orçamento, impressões perdidas por orçamento acima de [50%], ROAS abaixo do objetivo por [7 dias].

## Requisitos não funcionais

1. **Fonte da verdade do domínio é o registro**, não o banco local. Estado e
   vencimento reconciliados diariamente.
2. **Comando pago é idempotente**: reenvio não registra ou renova duas vezes.
3. **Fila com retentativa** para todo comando ao registro/registrador; nenhum
   comando some por timeout.
4. **Validação de registro DNS antes de salvar**: CNAME no apex, CNAME
   dividindo nome, SPF duplicado, MX apontando para IP, CAA sem a autoridade
   em uso (aviso).
5. **Escopo por conta na função de acesso** ao banco.
6. **Credenciais de integração** fora do alcance de pessoas e do log.
7. **Limites de uso** na busca de domínios e na API.
8. Painel utilizável no celular (regra da casa).
9. **Tokens OAuth de terceiros** (Google, Mercado Livre) cifrados em repouso, nunca no log, renovados antes de vencer. Falha de renovação vira aviso para o cliente reconectar, não erro silencioso.
10. **Revogação**: desconectar no painel revoga o token no provedor e remove a função da Ávila na propriedade GA4. Encerrar a conta faz o mesmo.
11. **Menor escopo**: cada integração pede só os escopos da etapa que o cliente escolheu.
12. Toda criação ou alteração em GA4, Google Ads e Mercado Livre Ads grava na trilha de auditoria (interno 08), com o identificador devolvido pela API.
13. **Camada de políticas e parâmetros** separada do resto do sistema: regra externa (ICANN, NIC.br), regra de fornecedor e política do produto, com fonte, vigência e histórico. Nenhum prazo regulatório escrito direto em tela, rotina ou e-mail. Desenho em [`POLITICAS-E-PARAMETROS.md`](POLITICAS-E-PARAMETROS.md). Deve existir antes do primeiro fluxo de domínio.

## Integrações

| Integração | Protocolo | Decisão |
|---|---|---|
| Registro.br | EPP | etapa 2 |
| Registrador parceiro | API HTTP | A1 |
| DNS autoritativo | [API do motor escolhido] | A2 |
| Autenticação | SSO `auth.avilaops.com` | decidido |
| Pagamento | [gateway] | A4 |
| Nota fiscal | [emissor] | A3 |
| E-mail transacional | [provedor] | aberto |
| Provisionamento existente (n8n) | webhook: domínio registrado → DNS, caixa, Google | passo 2 do levantamento comercial |
| Google Analytics 4 | Analytics Admin API (`v1beta`, partes em `v1alpha`) + Data API para Tempo real | D9; app OAuth A10 |
| Google Ads | Google Ads API | A10, A11 |
| Mercado Livre Ads | API Product Ads (`api-version: 2`) | leitura decidida; escrita A12 |

## Critério de lançamento

Portões do procedimento interno 10, Etapa 3.
