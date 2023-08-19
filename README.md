# Atividade de Programação - Multicast Communication Without Coordination - Sistema Distribuído

**Aluno:** Ian Marcos da Cruz Chaves  
**Matrícula:** 201802684  

Este repositório contém um exemplo simples de uma aplicaçãoMulticast Communication Without Coordination

## Funcionamento do Código
O código é um exemplo de comunicação multicast sem coordenação em um sistema distribuído. Ele simula vários processos que se comunicam enviando mensagens uns aos outros. O código é dividido em dois trechos, um para os processos que enviam mensagens e outro para o servidor que compara as mensagens recebidas de todos os processos.

## Processos que enviam mensagens
O código para os processos que enviam mensagens está no primeiro bloco fornecido. Aqui está um resumo do funcionamento:
>+ Importação das bibliotecas necessárias (socket, pickle, threading, random, time).
>+ Definição das constantes e configurações (como o número de processos N, o número de mensagens N_MSGS, portas e endereços dos processos PEERS, etc.).
>+ Definição da classe MsgHandler, que é uma subclasse de threading.Thread responsável por lidar com as mensagens recebidas pelo processo.
>+ Inicialização do contador handShakeCount para contar quantos processos realizaram o handshake.
>+ Criação de um socket de envio sendSocket.
>+ Geração de um ID aleatório para cada processo.
>+ Criação de um socket de recebimento recvSocket.
>+ Aguardo de um tempo de inicialização (10 segundos) para garantir que todos os processos estejam prontos para iniciar.
>+ Criação e inicialização de uma instância da classe MsgHandler para lidar com as mensagens recebidas.
>+ Envio dos handshakes para todos os outros processos.
>+ Aguardo até que todos os processos tenham realizado o handshake.
>+ Envio de uma sequência de mensagens para todos os outros processos.
>+ Envio de uma mensagem de encerramento para todos os outros processos.

## Servidor de Comparação de Mensagens
O segundo bloco de código é para o servidor que compara as mensagens recebidas de todos os processos. Aqui está um resumo do funcionamento:

>+ Criação de um socket de servidor serverSock que aguarda conexões.
>+ Inicialização de variáveis para contar o número de mensagens recebidas e armazenar as mensagens.
>+ Aguardo até que todas as mensagens sejam recebidas.
>+ Comparação das mensagens recebidas de diferentes processos para verificar se estão em ordem.

## Exemplo de Execução
Aqui está um exemplo de como você pode executar o código:
>+ Certifique-se de ter todas as configurações corretas, como o número de processos, portas e endereços dos processos em constMP.py.
>+ Execute o primeiro bloco de código em vários terminais ou máquinas virtuais diferentes para simular os processos que enviam mensagens.
>+ Depois que todos os processos tiverem concluído a execução, execute o segundo bloco de código em uma máquina separada para atuar como o servidor de comparação de mensagens.

Isso simulará a comunicação multicast entre os processos e verificará se as mensagens foram entregues em ordem.
