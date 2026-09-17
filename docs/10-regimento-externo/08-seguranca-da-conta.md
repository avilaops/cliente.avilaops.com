# Segurança da Conta

**Versão:** 0.1 (minuta) · **Vigência:** não publicada · **Responsável:** Nícolas Ávila

> **MINUTA.** Cada item diz se é compromisso (vale quando publicado) ou recurso
> (vale quando existir em produção). Estado real em `00-fundacao/ESTADO-DE-IMPLEMENTACAO.md`.

---

## 1. Login

- Login pela autenticação central da Ávila (`auth.avilaops.com`).
- **Verificação em duas etapas**: recomendada para toda conta; **obrigatória**
  para liberar código de autorização, trocar titular, desligar trava de
  transferência e criar token de API.
- **Código em dispositivo novo**: login de dispositivo ou local não reconhecido
  pede confirmação por e-mail.
- Sessões ativas visíveis e encerráveis em **Conta → Segurança**.

## 2. Ações sensíveis

Pedem nova confirmação (verificação em duas etapas ou código por e-mail),
mesmo com sessão aberta, e geram aviso por e-mail ao responsável da conta:

- gerar código de autorização;
- desligar trava de transferência;
- trocar titular ou e-mail do titular;
- trocar servidores DNS de um domínio;
- ligar ou desligar DNSSEC;
- adicionar usuário com poder de administração;
- criar token de API.

## 3. Atendimento

- O suporte identifica o cliente pelo **código de atendimento** do painel.
- A Ávila **nunca** pede senha, código de verificação ou código de
  autorização por e-mail, telefone ou WhatsApp.
- Pedido de acesso de quem perdeu o login segue verificação de identidade do
  titular (documento com foto e, para empresa, contrato social) e espera de
  [72 h] com aviso ao e-mail cadastrado antes de liberar.

## 4. E-mails oficiais

A Ávila só envia avisos de:

- [avisos@avilaops.com]
- [cobranca@avilaops.com]

Todo e-mail oficial tem SPF, DKIM e DMARC válidos. Links sempre levam a
`account.avilaops.com`. Aviso de vencimento de domínio vindo de outro
remetente, cobrando por boleto de "renovação de registro", é golpe comum:
ignore e confira no painel.

## 5. Prevenção a fraude

Para proteger titulares, a Ávila pode pedir verificação adicional antes de
concluir registro, transferência ou primeira compra, especialmente quando:

- o nome imita marca conhecida ou banco;
- o pagamento vem de cartão de país diferente do cadastro;
- vários domínios parecidos são pedidos em sequência.

Enquanto a verificação estiver pendente, o comando não é enviado ao registro
e nada é cobrado.

## 6. Tokens de API [depende da decisão A8]

- Escopo por permissão (ler, editar DNS, gerenciar domínios) e por domínio.
- Validade máxima de [12 meses].
- Exibido uma única vez; a Ávila guarda só o hash.

---

## Histórico de revisão

| Versão | Data | Alteração | Responsável |
|---|---|---|---|
| 0.1 | 16/09/2026 | Minuta inicial | Nícolas Ávila |
