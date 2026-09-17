# Contrato de Registro e Gestão de Domínios

**Versão:** 0.1 (minuta) · **Vigência:** não publicada · **Responsável:** Nícolas Ávila
**Aplica-se a:** todo domínio registrado, transferido ou gerenciado pelo account.avilaops.com.
**Complementa:** Termos de Serviço (01).

> **MINUTA PARA REVISÃO JURÍDICA.** Depende da decisão A1 (registrador
> parceiro) e da homologação no Registro.br. Regras de terceiros com fonte em
> `00-fundacao/FONTES-REGRAS-DE-TERCEIROS.md` (consultado em 16/09/2026);
> o que está **PENDENTE DE CONFIRMAÇÃO** não foi achado em fonte oficial.
> Todo prazo externo citado aqui é parâmetro em
> `40-produto/POLITICAS-E-PARAMETROS.md`.

---

## 1. Papéis

| Extensão | Quem administra | Papel da Ávila | Contrato que também se aplica |
|---|---|---|---|
| `.br` e subcategorias | Registro.br (NIC.br) | Provedor de Serviços | Contrato para Registro de Nome de Domínio sob o `.br` e regras do Registro.br |
| Genéricos (`.com`, `.app`...) | Registro da extensão, via registrador credenciado ICANN | Revendedora do [registrador parceiro] | Contrato de registro do [registrador parceiro] e *Registrants' Benefits and Responsibilities* da ICANN |

O cliente aceita esses contratos de terceiros no momento do registro ou da
transferência. Em caso de conflito, eles prevalecem sobre este documento.

## 2. Consequência de ter a Ávila como Provedor de Serviços `.br`

Enquanto um domínio `.br` estiver vinculado à Ávila, **as alterações nele
passam pela Ávila**. Por isso a Ávila se obriga a:

- manter o painel funcionando para o titular alterar DNS, contatos e renovação;
- liberar a mudança de provedor quando o titular pedir, sem condicionar a
  pagamento de serviço não relacionado ao domínio;
- em caso de encerramento da atividade, seguir o plano de continuidade
  (regimento interno 09) e avisar com [90] dias.

## 3. Registro

1. A disponibilidade exibida na busca é uma consulta, não uma reserva. O
   domínio só é do titular quando o registro confirma.
2. Dados obrigatórios do titular: nome ou razão social, CPF ou CNPJ, endereço,
   e-mail e telefone.
3. `.br` exige CPF/CNPJ válido e em situação regular na Receita Federal
   [confirmar regras por subcategoria, ex. extensões profissionais].
4. Genéricos exigem **verificação do e-mail do titular** em até **15 dias**
   após registro, transferência ou alteração de dados. Sem confirmação, o
   domínio é suspenso até a confirmação (programa de precisão de dados da ICANN).
5. Se o registro falhar depois do pagamento, o valor volta integralmente ao
   cliente (documento 06).

## 4. Dados do titular e consulta pública

1. O titular mantém os dados corretos. Dado falso pode levar ao cancelamento
   pelo registro, sem reembolso [confirmar com advogado].
2. Parte dos dados pode ficar visível em WHOIS/RDAP conforme a regra de cada
   registro. A Ávila exibe, antes da confirmação, o que será público
   [preencher por extensão após A1].
3. Troca de titular:
   - `.br`: segue o procedimento do Registro.br [confirmar documentação exigida];
   - genéricos: a troca aplica **trava de transferência de 60 dias** (Transfer
     Policy da ICANN vigente). O registrador pode oferecer dispensa dessa trava
     antes da troca; quando a dispensa estiver disponível, o painel mostra a
     opção antes da confirmação. [disponibilidade da dispensa: PENDENTE DE
     CONFIRMAÇÃO com o registrador parceiro, A1]

## 5. Renovação e vencimento

1. Todo domínio nasce com **renovação automática ligada**. O titular pode
   desligar.
2. Avisos de vencimento enviados pela Ávila, no mínimo:

   | Quando | Canal |
   |---|---|
   | [30] dias antes | e-mail |
   | [7] dias antes | e-mail + [WhatsApp/SMS] |
   | [1] dia antes, se não houver pagamento | e-mail + [WhatsApp/SMS] |
   | até [5] dias depois do vencimento | e-mail |

   > Para genéricos, a ERRP da ICANN exige aviso entre 26 e 35 dias antes,
   > entre 4 e 10 dias antes e em até 5 dias depois do vencimento, e que o
   > site descreva os canais usados. A tabela acima cumpre essa regra e vale
   > também para `.br`.

3. Renovação automática é tentada a partir de **[30] dias** antes do
   vencimento. Falha de pagamento gera nova tentativa e aviso.
4. **Depois do vencimento**, cada extensão tem sua própria sequência de
   interrupção, período de recuperação e liberação do nome. A página de
   preços mostra, por extensão, o prazo de recuperação, o preço de renovação
   após vencimento e a taxa de resgate.
   - **Genéricos:** o titular pode renovar a partir do vencimento. O DNS é
     interrompido pelo menos nos últimos 8 dias em que a renovação ainda é
     possível e pode dar lugar a uma página avisando do vencimento. Depois de
     excluído, o registro mantém o domínio por **30 dias de resgate**, sem DNS
     e sem transferência, com taxa. Prazo exato até a exclusão:
     [conforme registrador parceiro, A1].
   - **`.br`:** após a expiração, o domínio pode ser suspenso e deixa de
     funcionar, mas permanece reservado ao titular por até **90 dias** antes de
     sua remoção, sem ficar disponível para registro por terceiros. Depois da
     remoção, sua disponibilização a terceiros segue o Processo de Liberação do
     Registro.br, em ciclos definidos pelo Registro.br. Não há data garantida
     em que o nome fica disponível. [condições de reativação durante os 90
     dias: PENDENTE DE CONFIRMAÇÃO]
5. Domínio removido pelo registro após o fim do período de manutenção ou de
   resgate **não pode** ser devolvido pela Ávila.

## 6. Transferências

### 6.1 Entrada (trazer para a Ávila)

- Genéricos: o titular informa o código de autorização obtido no provedor
  atual. A transferência normalmente acrescenta um ano ao vencimento
  [confirmar por extensão].
- A transferência de genérico pode ser negada nos **60 dias** seguintes ao
  registro ou a uma transferência entre registradores, e fica bloqueada nos
  60 dias seguintes a uma troca de titular sem dispensa de trava (Transfer
  Policy da ICANN vigente). Se a ICANN alterar esses prazos, vale a regra
  vigente na data do pedido.
- `.br`: o titular escolhe a Ávila como novo Provedor de Serviços na
  interface do Registro.br; os dois provedores são avisados pelo sistema.
- A zona DNS do provedor anterior **não vem junto automaticamente**. O painel
  oferece importação do arquivo de zona antes de trocar os servidores DNS.

### 6.2 Saída (levar para outro provedor)

- O titular gera o código de autorização no próprio painel, sem abrir chamado.
- A Ávila **não cobra** para liberar transferência de saída e não a retém por
  débito de nenhum serviço, nem do próprio domínio. (A política da ICANN
  permitiria negar por débito do período corrente; a Ávila abre mão disso.
  Nunca é permitido negar por falta de pagamento de período futuro.)
- Domínio com disputa, ordem judicial ou suspeita de fraude em análise pode ter
  a saída suspensa pelo tempo da análise, com aviso ao titular.
- Ao concluir a saída, a zona DNS hospedada na Ávila continua disponível por
  **[30] dias** e depois é apagada.

## 7. DNS

1. O titular escolhe usar os servidores DNS da Ávila ou servidores próprios.
2. Nos servidores da Ávila, a zona é editada pelo painel, com histórico de
   versões e restauração.
3. A Ávila não altera registros DNS do cliente, exceto:
   - por pedido do titular registrado em atendimento;
   - por ordem judicial ou do registro;
   - para conter abuso grave (documento 03), com aviso imediato.
4. DNSSEC: disponível para [extensões compatíveis]. Ligar DNSSEC com
   servidores externos exige que o titular publique o registro DS correto;
   DS errado deixa o domínio fora do ar.
5. `.br` exige no mínimo 2 e no máximo 5 servidores DNS, que precisam estar
   respondendo pelo domínio, e aceita até 2 registros DS.

## 8. Disputas sobre o nome

- **`.br`:** SACI-Adm, procedimento administrativo do NIC.br vinculado ao
  contrato de registro `.br`, conduzido por instituição credenciada pelo
  NIC.br escolhida pelo reclamante. Não é arbitragem nem mecanismo da ICANN.
  Pode resultar em manutenção, transferência ou cancelamento do domínio.
  Regulamento suplementar e custos são os da instituição escolhida.
- **Genéricos sujeitos às políticas da ICANN:** UDRP ou procedimento
  equivalente previsto para a extensão.
- Em qualquer caso, as partes podem recorrer ao Poder Judiciário. Nenhum
  desses mecanismos é obrigatório para quem prefere a via judicial.

A Ávila não é parte nem julgadora do conflito. Durante procedimento formal,
trava transferência e troca de titular do domínio, e cumpre a decisão final
quando executada pelo registro ou determinada judicialmente.

## 9. Preços

Registro, renovação, renovação após vencimento, transferência e resgate têm
preço por extensão na página de preços, com link a partir deste contrato
(exigência da ERRP também para revendedores). O preço de renovação é o
vigente na data da renovação; reajuste é avisado com [30] dias.

---

## Histórico de revisão

| Versão | Data | Alteração | Responsável |
|---|---|---|---|
| 0.1 | 16/09/2026 | Minuta inicial | Nícolas Ávila |
| 0.2 | 16/09/2026 | Prazos de ERRP, transferência, verificação e regras EPP do `.br` preenchidos com fonte | Nícolas Ávila |
| 0.3 | 16/09/2026 | `.br`: 90 dias de manutenção da titularidade e Processo de Liberação como etapas distintas (NIC.br); SACI-Adm descrito com fonte oficial; retirada a previsão de trava de 30 dias (não vigente); dispensa da trava de troca de titular deixa de ser garantida | Nícolas Ávila |
