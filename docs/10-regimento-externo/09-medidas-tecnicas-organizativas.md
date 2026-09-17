# Medidas Técnicas e Organizativas

**Versão:** 0.1 (minuta) · **Vigência:** não publicada · **Responsável:** Nícolas Ávila

> **MINUTA.** Equivalente ao documento de TOMs da Hetzner. Só lista o que
> será verdade no lançamento; cada linha tem estado real em
> `00-fundacao/ESTADO-DE-IMPLEMENTACAO.md`. Linha que não virar verdade sai
> antes de publicar.

---

| Área | Medida |
|---|---|
| **Controle de acesso físico** | Infraestrutura em data center de terceiro ([Hetzner, Alemanha]), com certificação [ISO 27001 do provedor]. A Ávila não mantém servidor em escritório. |
| **Controle de acesso lógico** | SSO central; verificação em duas etapas obrigatória para toda a equipe; acesso de produção por chave SSH individual; sem conta compartilhada. |
| **Menor privilégio** | Equipe de atendimento vê dados da conta, mas só executa ação sobre domínio com código de atendimento do cliente. Credencial do registrador e do EPP acessível apenas ao serviço, não a pessoas. |
| **Segregação entre clientes** | Toda consulta ao banco escopada pela conta na função de acesso, não só na tela. |
| **Criptografia** | TLS em todo tráfego; segredos (tokens, credenciais de integração) cifrados no banco; backups cifrados. |
| **Integridade** | Trilha de auditoria imutável para alteração de domínio, DNS, usuários e cobrança; versões de zona restauráveis. |
| **Disponibilidade** | DNS em [N] servidores em [N] locais/redes distintos [depende de A2]; backups [diários], retidos [30 dias], restauração testada [trimestralmente]. |
| **Registro de acesso** | Logs de acesso guardados 6 meses (Marco Civil). |
| **Gestão de incidentes** | Registro formal de incidente; comunicação ao cliente afetado em até 24 h da confirmação. |
| **Fornecedores** | Registro, registrador, gateway, e-mail transacional e hospedagem avaliados quanto a privacidade e segurança antes do uso. |
| **Pessoas** | Termo de confidencialidade para toda pessoa com acesso a dados de cliente (modelo `docs/juridico/NDA.md`). |
| **Revisão** | Este documento é revisado a cada [6 meses] ou após incidente. |

---

## Histórico de revisão

| Versão | Data | Alteração | Responsável |
|---|---|---|---|
| 0.1 | 16/09/2026 | Minuta inicial | Nícolas Ávila |
