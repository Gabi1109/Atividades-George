Questões sobre Ferramentas de Monitoramento de Sistema

1. Comparação de Finalidade e Acesso: Qual a principal diferença na finalidade e na forma de acesso entre o Monitor de Atividade e o top? Como o Gerenciador de Tarefas se alinha com essa distinção?

R= O Monitor de Atividade e o Gerenciador de Tarefas usam interface gráfica para mostrar processos e recursos de forma intuitiva, com interface visual e informações detalhadas sobre CPU, memória, rede e disco. Já o top é uma ferramenta de linha de comando, focada em monitoramento em tempo real, mais voltada a usuários avançados.


2. Monitoramento de CPU: Como você usaria cada uma das três ferramentas para identificar qual processo está consumindo a maior parte da CPU em tempo real? Descreva os passos básicos para cada sistema operacional.

R= No Mac, basta abrir o Monitor de Atividade e ordenar pela aba CPU. No Windows, usa-se o Gerenciador de Tarefas e observa-se a coluna CPU. No Linux, o comando top mostra em tempo real, e a tecla P ordena pelo maior consumo.

3. Análise de Memória: O Monitor de Atividade e o Gerenciador de Tarefas apresentam detalhes sobre o uso de memória (como memória física e swap). Como o top em Linux exibe essa informação e quais métricas de memória são mais relevantes para entender o consumo de um processo?

R= No top do Linux, a memória é exibida com métricas como : 
VIRT (memória total alocada),
RES (memória física usada) e 
SHR (memória compartilhada).
As mais relevantes para analisar um processo são RES, que mostra o uso real de RAM, e %MEM, que indica a proporção da memória total ocupada pelo processo.

4. Processos e PIDs: Explique a importância do PID (ID do Processo) e como ele é exibido em cada uma das ferramentas. Como você usaria o PID para encerrar um processo que não responde em cada sistema operacional?
   
R= O PID é um número único que identifica cada processo, permitindo monitorar e encerrar processos específicos. No Monitor de Atividade e no Gerenciador de Tarefas, o PID aparece em uma coluna chamada “PID”. No top, ele aparece na primeira coluna de cada processo. Para encerrar um processo pelo PID: no Windows, é usado taskkill /PID <número> /F; no macOS/Linux GUI, é necessário selecionar o processo e clicar em “Encerrar” ou “Forçar Encerrar”; no Linux terminal, use kill <PID> ou kill -9 <PID> para forçar.

5. Diferença na Interface:Descreva as principais diferenças na interface do usuário (UI) entre as três ferramentas. Qual delas é mais orientada a comandos de texto e qual é mais visual?
   
R= As principais diferenças de interface são que o Monitor de Atividade e o Gerenciador de Tarefas têm interfaces gráficas, mostrando processos e recursos de forma visual e permitindo ações com cliques, sendo mais acessíveis a usuários comuns. Já o top é orientado a comandos de texto, exibindo informações em tempo real no terminal, voltado para usuários avançados e administradores de sistema.

6. Monitoramento de Rede: Como o Monitor de Atividade e o Gerenciador de Tarefas permitem inspecionar o tráfego de rede de diferentes aplicativos? Qual comando ou técnica similar é usada no Linux para obter informações detalhadas sobre a atividade de rede de processos?

R= O Monitor de Atividade e o Gerenciador de Tarefas têm abas que mostram tráfego de rede por aplicativo. No Linux, usam-se comandos como iftop, nethogs ou netstat.   

7. Análise de Disco: O Monitor de Atividade e o Gerenciador de Tarefas possuem abas ou seções dedicadas para monitorar a atividade do disco (leitura/escrita). Qual a importância de monitorar o disco e como o top (ou uma ferramenta complementar do Linux) pode ser usado para obter essa mesma informação?

R= No Mac e no Windows existem abas para ver leitura e gravação no disco. Isso é importante, pois processos que usam muito o disco deixam o sistema lento. No Linux, essa função pode ser feita com ferramentas como iotop.

8. Hierarquia de Processos: Em que medida o Monitor de Atividade e o Gerenciador de Tarefas são capazes de exibir a hierarquia de processos (processos pais e filhos)? E como o top pode ser configurado ou complementado com outro comando para mostrar essa hierarquia?

R= O Monitor de Atividade e o Gerenciador de Tarefas não exibem bem a relação pai e filho. No Linux, essa hierarquia pode ser vista no htop ou com o comando ps --forest.

9. Uso em Servidores vs. Desktops: Qual das três ferramentas é mais adequada para monitoramento em ambientes de servidor (especialmente sem interface gráfica)? Justifique sua resposta, explicando como as características de cada uma se encaixam melhor em cenários de servidor ou de desktop.

R= O top é ideal para servidores porque funciona no terminal e não precisa de interface gráfica. Já o Monitor de Atividade e o Gerenciador de Tarefas são melhores em desktops por serem gráficos e intuitivos.
