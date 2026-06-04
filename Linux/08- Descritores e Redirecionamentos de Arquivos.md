Descritores e Redirecionamentos de Arquivos

Um descritor de arquivo (FD) de um sistema operacional Unix/Linux é uma referência, mantida pelo kernel, que permite ao sistema gerenciar 
operações de Entrada/Saída (I/O,I/O), ele atua como um identificador único para um arquivo aberto, socket ou qualquer recurso de E/S. 
Num sistema operacionais em Windows ou baseado em Windows, é conhecido como handle de arquivos. Em resumo, o descritor de arquivos é uma 
forma do sistema de acompanhar conexões ativas, ler ou gravar em um arquivo
Pense nisso como o número de um ingresso que aparece ao você despachar seu casaco em um guarda-volume. O ingresso (descritor de arquivo) representa 
sua conexão com seu casaco (arquivo ou recurso), sempre que você precisar recuperar seu casaco (realizar I/O), você apresenta o ticket ao atendente 
(sistema operacional), que sabe exatamente aonde seu casaco está armazenado (a qual recurso o descritor do arquivo se refere). Sem o ingresso, você não iria 
conseguir acessar seu casaco de forma eficiente entre os muitos outros armazenado, assim como sem um descritor de arquivo, o sistema não iria saber com qual 
recurso interagir.

Padrão, esses são os 3 primeiros descritores de arquivos Linux:

1- Fluxo de Dados para Entrada
 - (STDIN - 0)
2- Fluxo de Dados para Saída
 - (STDOUT - 1)
3- Fluxo de dados para Saída relacionada a um erro ocorrendo
 - (STDERR - 2)

STDIN e STDOUT

Agora iremos ver um exemplo, ao rodar o comando, damos ao programa em execução nossa entrada padrão (cat STDIN - FD 0), marcada na cor verde, 
onde neste caso é "ALGUMA ENTRADA". Assim que confirmamos nossa entrada com a tecla [ENTER], ela é retornada ao terminal com a saída padrão 
(STDOUT - FD 1) e marcada na cor vermelha.

STDOUT e STDERR

Nesse exemplo, usando o comando (find STDOUT - FD 1), veremoas a saída padrão (STDERR - FD 2) marcada em verde e o erro padrão marcado em vermelho.

(find /etc/ -name shadow)

O que é marcado geralmente é exibido com "Permission denied". Podemos verificar isso redirecionando o descritor de arquivo dos erros 
(FD 2) para "- STDERR /dev/null", nessa forma vamos redirecionar os erros resultantes para o "dispositivo nulo", que descarta todos os dados.

(find /etc/ -name shadow 2>/dev/null > results.txt)

Redirecionar STDOUT para um Arquivo

Agora podemos ver que todos os erros (STDERR) anteriormente apresentados com "Permission denied" não são mais exibidos. O único resultado 
que vemos agora é a saída padrão (STDOUT), que também podemos redirecionar para um arquivo com o nome results.txt, que só conterá a saída 
padrão sem os erros padrão.

(find /etc/ -name shadow 2>/dev/null > results.txt)

Redirecionar STDIN

Como já vimos, nas combinação com os descritores do arquivo, podemos redirecionar erros e sair com caracteres maiores que (>), isso também 
funciona com o sinal de menor que (<). No entanto, o sinal de menor que serve como entrada padrão (FD 0 - STDIN). Esse caractere pode ser visto
como "Direction" na forma de uma seta que diz "from where" e "where to" que os dados devem ser redirecionado. Usamos o comando (cat < stdout.txt) 
para usar o conteúdo do arquivo "stdout.txt" como "STDIN".

(cat < stdout.txt)

Redirecione STDOUT e anexe a um arquivo

Quando usamos o sinal de maior que (>) para redirecionar STDOUT, um novo arquivo é criado automaticamente se ele ainda não existir. 
Se esse arquivo existir, ele será sobre escrito sem necessidade de confirmação. Se quisermos acrescentar ao nosso arquivo existente, 
podemos usar o sinal duplo de maior que (>>).

(find /etc/ -name passwd >> stdout.txt 2>/dev/null)

Redirecione o fluxo STDIN para um arquivo

Podemos usar os caracteres duplos menos que (<<) para adicionar nossa entrada padrão através de um fluxo. Podemos usar a chamada (End-Of-File(EOF)) 
de um arquivo de sistema Linux, que define o fim da entrada. No próximo exemplo, usaremos o comando (cat) para ler nossa entrada de streaming pelo 
fluxo e direcioná-la para um arquivo chamado (stream.txt).

(cat << EOF > stream.txt)

Tubos

Uma outra forma de redirecionar é usando o pipes (|). Esses são úteis quando queremos usar o STDOUT de um programa para ser processado para outro. 
Uma das ferramentas mais usadas é o (grep). (grep) é usado para filtrar STDOUT de acordo com o padrão que definimos, o comando (find) para buscar 
todos os arquivos no diretório /etc/ com uma extensão (.conf). Quaisquer erros que tiver são redirecionado para o null device (/dev/null). Usando o (grep), 
filtramos os resultados e especificamos que apenas as linhas contendo o padrão (systemd) devem ser exibidas.

(find /etc/ -name *.conf 2>/dev/null | grep systemd)

 Os redirecionamentos funcionam não só uma vez, podemos usar os resultados obtidos para redirecioná-los para outro programa. Temos o comando (wc) 
 que realiza a contagem de números total de resultados obitidos.

(find /etc/ -name *.conf 2>/dev/null | grep systemd | wc -l)

Para saber quantos pacotes tem instalado no sistema, usamos o comando: (dpkg -l | grep '^ii' | wc -l)
