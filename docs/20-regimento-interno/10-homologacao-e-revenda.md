# 10. Homologação Registro.br e conta de revenda

Checklist do que precisa existir **antes** de vender. Ordem do levantamento
comercial: genéricos primeiro, `.br` depois.

## Etapa 1: revenda de genéricos

- [ ] Decidir registrador parceiro (A1). Levantar: preço de atacado por
      extensão, forma de pagamento, taxa de transferência e resgate, contrato
      que o cliente final precisa aceitar, obrigações de revendedor (exibição
      de *Registrants' Benefits and Responsibilities*, canal de abuso, retenção
      de dados). OpenSRS já levantado (FONTES §6); ler o contrato de revenda
      dele e comparar com pelo menos um concorrente.
- [ ] Obrigações de revendedor já confirmadas na ERRP: publicar preço de
      renovação, renovação após vencimento e resgate, e os canais dos avisos
      de vencimento (FONTES §1).
- [ ] Resolver enquadramento do CNPJ (A3).
- [ ] Abrir conta de revendedor, com MFA, em nome da Ávila.
- [ ] Registrar **um domínio da Ávila** pela conta, do começo ao fim: busca,
      registro, verificação de e-mail, DNS, renovação, código de autorização.
- [ ] Transferir um domínio da Ávila de entrada e um de saída.
- [ ] Registrar o aprendizado em `ESTADO-DE-IMPLEMENTACAO.md`.

## Etapa 2: `.br`

Requisitos levantados em 16/09/2026, com fonte, em
`00-fundacao/FONTES-REGRAS-DE-TERCEIROS.md` §4.

- [ ] Perguntar a `epp@registro.br`: MEI é aceito? Há taxa, garantia ou
      requisito financeiro? Pedir a minuta do contrato (A3).
- [ ] Escolher o **nome do provedor**: uma palavra, até 25 caracteres, **não
      pode ser trocado depois**. Sugestão: `AVILAOPS` [decidir].
- [ ] Definir SAC público exigido no formulário: site, telefone e e-mail (A9).
- [ ] Criar ID de usuário técnico no Registro.br.
- [ ] Definir IPs fixos de saída do servidor que fala EPP (até 4 endereços ou
      blocos /26).
- [ ] Enviar formulário de **homologação** em texto para
      `epp-suporte@registro.br`.
- [ ] Instalar a biblioteca EPP (`libepp-nicbr`) ou cliente equivalente e
      executar o roteiro de homologação em `beta.registro.br`: conexão, login,
      contatos, organizações, domínios (verificar, criar, renovar, excluir),
      mensagens. Anotar data, hora e IP e enviar ao Registro.br.
- [ ] Após aprovação, enviar formulário de **credenciamento** para
      `epp@registro.br`, com dados do representante legal (RG, CPF, profissão,
      endereço).
- [ ] Assinar contrato com o NIC.br.
- [ ] Carregar crédito para renovações (renovação EPP exige crédito suficiente).
- [ ] Migrar **um domínio `.br` da Ávila** para a Ávila como provedor, pela
      interface do Registro.br.

Restrições que o sistema precisa respeitar desde o primeiro dia: renovação de
1 a 10 anos; exclusão só nos 5 primeiros dias e até 3% dos registros recentes;
2 a 5 servidores DNS respondendo; até 2 registros DS; contato que se recadastra
na web deixa de ser editável pelo provedor.

## Etapa 3: antes de anunciar

- [ ] Revisão jurídica das minutas de `10-regimento-externo/`.
- [ ] Canal de abuso lido todo dia (procedimento 05).
- [ ] Decisão de plantão (A6) e SLA coerente com ela.
- [ ] Régua de renovação rodando com o domínio de teste (procedimento 02).
- [ ] Portões de `docs/regras/PRONTO-PARA-VENDER.md` cumpridos.

> Não anunciar "compre seu domínio" antes da Etapa 1 estar provada: vender
> registro que ainda é manual promete automático e entrega WhatsApp.
