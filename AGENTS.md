# AGENTS.md: account.avilaops.com

<!-- avilaops:contexto:inicio (versão 2026-10-03; gerado a partir de avilaops/contexto, não editar aqui) -->
## Contexto Ávila Ops (vale para todos os projetos)

Este repositório pertence à Ávila Ops Tecnologia, que ajuda pequenas empresas a construir presença digital, organizar a operação e crescer. As contas `avilaops` e `avilainc` no GitHub são a mesma empresa. Nicolas Avila (Nicolas sem acento) é o fundador e quem decide.

### Como trabalhar

- Comunicar em português natural, com resposta direta e evidência. Sem tom de coach, promessa vaga ou jargão comercial. O idioma da interface e do conteúdo acompanha o site, não a conversa.
- Identificar o projeto, o domínio, o repositório e o ambiente antes de alterar qualquer coisa. Não presumir que todos os projetos usam o mesmo deploy.
- Ter iniciativa dentro do pedido e levar a tarefa até um resultado verificado. Plano, código, publicação e funcionamento comprovado são coisas diferentes: não declarar sucesso só porque um build terminou ou um workflow foi ativado.
- Proteger dados, acessos e a separação entre clientes. Nunca gravar segredo em arquivo versionado, issue, PR ou memória.
- Não iniciar comunicação externa nem ação irreversível sem autorização do Nicolas.
- Preservar trabalho em andamento de outra pessoa ou de outro agente. Trabalho não commitado vai para uma branch `resgate/*`.

### Decisões vigentes

- Pagamentos: Mercado Pago no Brasil e PayPal para clientes de fora. Não usar Stripe nem Éfi, mesmo que material antigo diga o contrário.
- Automações em n8n, infraestrutura em Cloudflare e canais em Twilio, preservando integrações existentes.
- Ofertas com três planos: entrada limitada, intermediário como escolha principal e premium como referência. Consultar preços vigentes antes de publicar.
- Build de aplicação roda no GitHub Actions, não no servidor de produção.
- Versão antiga de código fica no GitHub. Não criar `.tgz`, `.tar`, `*-before-*` nem pastas `rollback/`, `releases/` ou `backups/` com código no servidor; voltar versão é republicar o commit. Antes de mexer em dado, fazer dump do banco.

### Sessões na nuvem

- Uma sessão de nuvem não tem acesso à máquina do Nicolas, aos servidores nem à memória compartilhada. Não presumir o estado de produção: buscar evidência ou dizer que não foi verificado.
- Decisão durável tomada na sessão deve ficar registrada na descrição do PR e, quando for do projeto, neste arquivo, fora deste bloco.
- A memória compartilhada completa e as regras corporativas ficam no repositório privado `avilaops/contexto`.
<!-- avilaops:contexto:fim -->

Regras específicas deste projeto. As regras gerais da casa continuam valendo
(`../AGENTS.md`, `../docs/regras/`).

## Vocabulário obrigatório

- Para `.br`: "Provedor de Serviços do Registro.br". Para genéricos:
  "revendedora de registrador credenciado".
- **Proibido** escrever que a Ávila é "registrador", "registradora
  credenciada", "credenciada pela ICANN" ou "entidade registradora". É falso e
  tem consequência jurídica.
- "Titular" é o dono do domínio (o cliente). "Contato técnico" é o papel da
  Ávila. Não inverter.
- Termos do glossário em [`docs/00-fundacao/GLOSSARIO.md`](docs/00-fundacao/GLOSSARIO.md)
  são os únicos usados em tela e documentação.

## Regras de conteúdo

1. **Ideia não é funcionalidade.** Página da central de ajuda que descreve tela
   só é escrita quando a tela existe em produção. Até lá fica como item do
   backlog em `docs/INDICE.md`.
2. Todo documento de regimento tem cabeçalho de versão, histórico de revisão e,
   no externo, a marca **MINUTA** até passar por revisão jurídica.
3. Número que vem de terceiro (prazo do Registro.br, regra da ICANN, preço de
   atacado) só entra com a fonte ao lado ou marcado **PENDENTE DE CONFIRMAÇÃO**.
4. Dado a preencher fica entre colchetes: `[e-mail de atendimento]`. A lista
   de lacunas vive em `ESTADO-DE-IMPLEMENTACAO.md`. Regra de terceiro sem
   fonte oficial é marcada **PENDENTE DE CONFIRMAÇÃO**, com o que falta.
4b. Fonte SECUNDÁRIA (blog, notícia, outro provedor) nunca sustenta obrigação
   do Registro.br, NIC.br ou ICANN. Mudança regulatória só em discussão fica
   em FONTES §11 e não entra em texto nem código.
5. Domínio de cliente nunca é registrado no CNPJ da Ávila, nem "temporariamente".
6. Datas em `DD/MM/AAAA`. Idioma: português do Brasil.

## Regras técnicas (para quando houver código)

- Login pelo SSO de `auth.avilaops.com` (`../docs/plataforma/AUTH-SSO.md`).
- Toda alteração de zona DNS e todo comando ao registro/registrador grava
  trilha de auditoria: quem, quando, antes, depois, origem (cliente, equipe,
  automação).
- Comando que custa dinheiro (registro, renovação, transferência) é idempotente.
- **Nenhum prazo, limite ou lista regulatória no código.** Tudo vem da camada
  de `docs/40-produto/POLITICAS-E-PARAMETROS.md`, separando regra externa,
  regra de fornecedor e política do produto. Lista de instituições do
  SACI-Adm também é configuração.
- Credenciais do registrador e do EPP nunca vão para Git, `.env.example` ou log.
