Exercícios Teóricos – Processos

1. Qual a diferença entre programa e processo?

R= Os programas são um conjunto de instruções detalhadas armazenadas em um arquivo, já o processo é um programa em execução.

2. Quais são os estados de um processo e quando ocorrem as transições?

R= Os estados de um processo são:
Novo: quando o processo foi criado e está aguardando alocação de recursos;
Pronto: quando o processo está apto a ser executado aguardando a CPU;
Executando: o processo está atualmente em execução na CPU;
Bloqueado: quando o processo aguarda um evento externo;
Finalizado: o processo foi finalizado e liberou os recursos alocados.
As transições ocorrem da seguinte forma:
Novo => Pronto (quando é admitido pelo sistema operacional).
Pronto => Execução (quando o escalonador escolhe o processo).
Execução => Pronto (quando é preemptado).
Execução => Bloqueado (quando espera por E/S).
Bloqueado => Pronto (quando o evento ocorre).
Execução => Finalizado (quando termina).


3. O que contém um Process Control Block (PCB)?

R= O PCB contém as principais informações do processo: seu identificador (PID), estado atual, contador de programa, registradores da CPU, dados para escalonamento (como prioridade), informações de memória e de entrada/saída (arquivos e dispositivos usados).

4. O que acontece com os recursos de um processo quando ele termina?

R= Quando um processo termina, o sistema operacional libera todos os recursos que estavam sendo usados por ele, como a memória ocupada, arquivos abertos, dispositivos de entrada e saída e quaisquer outros recursos alocados.

5. Qual a diferença entre fork() e exec() no UNIX?

R= No UNIX, fork() cria um novo processo filho, copiando quase todo o contexto do processo pai.Já o exec() não cria processo novo, ele substitui o código do processo atual por outro programa carregado na memória.

6. Como funciona a hierarquia de processos em UNIX?

R= No UNIX, os processos formam uma "árvore", cada processo (pai) pode criar processos filhos, que herdam algumas informações do pai. O pai pode esperar o filho terminar, e se acabar antes, o filho é adotado pelo processo init/systemd.

7. Compare memória compartilhada e troca de mensagens (IPC).

R= Na memória compartilhada, dois ou mais processos acessam a mesma área de memória para trocar dados. É muito rápida, pois não precisa passar mensagens pelo SO, mas exige mecanismos de sincronização,como semáforos, para evitar conflitos. Já na troca de mensagens, os processos enviam e recebem dados por meio do SO (filas, pipes, sockets). É mais simples de usar e mais segura, pois cada processo tem sua própria memória, mas costuma ser mais lenta que a memória compartilhada.

8. Cite exemplos de chamadas de sistema usadas em IPC.

R= Alguns exemplos de chamadas de sistema usadas em IPC são: 
pipe() => que cria um canal de comunicação unidirecional;
shmget() e shmat() => que criam e conectam segmentos de memória compartilhada;
msgget(),msgsnd() e msgrcv() => que permitem usar filas de mensagens;
socket() => usado para comunicação entre processos locais ou remotos.


9. Por que é importante que o sistema operacional faça gerenciamento de processos?

R= O gerenciamento de processos é importante porque o sistema operacional precisa controlar a execução de múltiplos processos simultâneos, garantindo que cada um receba tempo de CPU, acesso à memória e a outros recursos de forma organizada. Isso evita desperdício de recursos e travamentos, garantindo a estabilidade e a segurança do sistema.

10. Explique a diferença entre processos independentes e processos cooperativos.

R= Os processos independentes não compartilham informações nem recursos com outros processos.Eles podem ser executados sem se preocupar com o que outros processos fazem. Já os processos cooperativos podem  compartilhar dados e recursos, precisando se sincronizar para evitar conflitos. Essa cooperação permite comunicação e divisão de tarefas, mas exige cuidado para não ocorrerem erros.

11. O que é um processo zumbi em UNIX/Linux?

R= É um processo que já terminou sua execução, mas ainda mantém uma entrada na tabela de processos porque o processo pai não coletou seu status.

12. Explique a diferença entre chamadas bloqueantes e não bloqueantes em IPC.

R= As chamadas bloqueantes fazem o processo esperar até a operação terminar. Já as não bloqueantes deixam o processo seguir, mesmo que a operação não tenha sido concluída.

13. Qual a diferença entre processo pesado (process) e thread (processo leve)?

R= O processo pesado (process) tem seu próprio espaço de endereçamento e recursos e, como o próprio nome diz, ele é mais pesado de criar e trocar contexto. Já a Thread (processo leve) compartilha memória e recursos do processo pai e é mais leve e rápida, mas exige maior cuidado com sincronização.

14. Por que sistemas operacionais multiprogramados precisam de troca de contexto (context switch)?

R= Os sistemas operacionais precisam de troca de contexto (context switch) para alternar entre processos em execução, permitindo compartilhamento justo da CPU, garantindo que todos os processos tenham chance de rodar e que a máquina seja usada de forma eficiente.

15. Cite vantagens e desvantagens da comunicação via memória compartilhada.

R= Vantagens: rápida e boa para grandes volumes de dados.
Desvantagens: exige sincronização cuidadosa, senão gera conflitos e erros de concorrência.
