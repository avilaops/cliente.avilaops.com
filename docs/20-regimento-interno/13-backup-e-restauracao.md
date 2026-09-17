# 13. Backup e restauração

## O que tem backup

| Dado | Frequência | Retenção | Onde |
|---|---|---|---|
| Banco (contas, domínios, cobrança) | [diário] + log contínuo | [30 dias] | [local fora do servidor principal] |
| Zonas DNS em formato BIND | a cada alteração (versão) + exportação [diária] | versões: [90 dias]; exportação: [30 dias] | idem |
| Trilha de auditoria | junto com o banco | conforme externo 04 | idem |
| Configuração dos servidores DNS | a cada mudança | Git, sem segredos | repositório |

Backup cifrado. Chave de decifragem fora do servidor que é copiado.

## O que não depende de backup nosso

Titularidade, vencimento e servidores DNS delegados estão no **registro**
(Registro.br, registrador). Em perda total do banco, são reconstruídos
consultando o registro, domínio por domínio. A rotina de reconciliação
diária (procedimento 02) é o que prova que isso funciona.

## Teste de restauração

A cada [trimestre]:

1. Restaurar o backup mais recente em ambiente isolado.
2. Conferir: número de contas, domínios e zonas bate com produção; uma zona
   escolhida ao acaso responde igual.
3. Restaurar uma versão antiga de uma zona de teste pelo painel.
4. Registrar data, tempo gasto e problemas.

Backup nunca testado é tratado como inexistente em `ESTADO-DE-IMPLEMENTACAO.md`.
