# 08. Acesso interno e auditoria

## Contas e credenciais

| Credencial | Onde fica | Quem acessa | Rotação |
|---|---|---|---|
| API do registrador parceiro | cofre do servidor, variável de ambiente | só o serviço | [12 meses] ou suspeita |
| Certificado/credencial EPP Registro.br | cofre do servidor | só o serviço | conforme Registro.br |
| Painel web do registrador e do Registro.br | gerenciador de senhas da empresa, com MFA | Dono do serviço | [12 meses] |
| Banco de produção | servidor | Desenvolvimento, por SSH individual | chave revogada na saída da pessoa |

Inventário de credencial com dono e data de rotação é obrigatório; a política
de IA da casa já registra que esse inventário ainda não existe.

## Visão de cliente pela equipe

- Equipe pode **ver** dados da conta para atender.
- Equipe só **age** sobre domínio ou DNS com código de atendimento válido do
  cliente ou com caso de abuso/ordem aberto.
- "Entrar como o cliente" (impersonação), se existir, grava trilha e avisa o
  cliente por e-mail.

## Trilha de auditoria (requisito)

Cada evento grava: data/hora UTC, ator (usuário, equipe, automação, API
token), conta, objeto (domínio, zona, registro), antes, depois, IP, motivo
(obrigatório para ação da equipe), identificador do comando no
registro/registrador.

A trilha não pode ser editada nem apagada pela aplicação. Retenção no externo 04.

## Revisão

A cada [trimestre]: listar acessos ativos, remover quem não precisa,
amostrar [20] ações da equipe na trilha e conferir se todas têm motivo e caso.
