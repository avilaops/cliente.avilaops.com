# AGENTS.md: account.avilaops.com

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
