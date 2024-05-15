# SCO - System Closeing Orchestration [Chronogram Orchestrator Tool]

Solução desenvolvida para auxiliar nas rotinas de Fechamento Contábil do Grupo Boticário.
Fesenvolvidos que executam operações de apoio à planilha que mantem as atividades do fechamento contábil.

## Estrutura das Functions no Google Apps Script

![Diagram](./.img/mermaid-diagram.png)

## Funções Principais

### `criarFormularioEEnviar(id)`
Cria um formulário com base nos dados de uma linha específica da planilha e o envia para o executor da atividade.

### `armazenarResposta(e)`
Armazena a resposta do formulário enviado, atualiza a planilha com a resposta e executa ações associadas à resposta.

## Funções Auxiliares

### `enviaSlackMessageDirectPayload(token, mensagem, userId)`
Envia uma mensagem direta para um usuário no Slack.

### `enviarMensagemSlackComMencao(webhookUrl, mensagem, username)`
Envia uma mensagem para um canal do Slack mencionando um usuário.

### `deleteFormTrigger(formsID)`
Exclui a trigger associada a um formulário.

### `deleteForms(formsID)`
Exclui um formulário.

## Funções de Configuração e Agendamento

### `onInstall()`
Executada quando o script é instalado como um complemento.

### `onOpen()`
Executada quando a planilha é aberta.

### `armazenarRespostaAgendar()`
Agenda a execução da função `armazenarResposta`.

### `alterarValorNotificaStatusExecuteAgendar()`
Agenda a execução da função `alterarValorNotificaStatusExecute`.

## Funções Acionadas pelo usuário

### `adicionarLinhaComFormulas(nomeDaAba, linhaParaCopiar)`
Insere uma nova linha na planilha com base em uma linha modelo. É acionada após o Usuário Clicar em um Botão na Planilha.

## Funções Genéricas

### `alteraValorGenerico(valor, colunaOrigem, colunaDestino, novoValor, nomeAba)`
Localiza um valor em uma coluna e altera o valor correspondente em outra coluna.

## Funções de Atualização de Status

### `alterarValorNotificaStatus(qValor, novoValorF, abaPlanilha)`
Atualiza o status das tarefas na planilha e envia formulários para executores quando necessário.

### `alterarValorNotificaStatusExecute()`
Subfunção que atualiza o status das tarefas para "Iniciada".

## Desenho da Solução

![Diagrama Solução](./.img/FerramentaCronogramaSlack.drawio.svg)

