Navegação

A navegação é essencial, com ela conseguimos nos deslocar pelo sistema, trabalhamos em diretórios e com arquivos que precisamos e queremos. 
Por esse motivos, utilizamos comandos e ferramentas para imprimir informações sobre um diretório ou arquivos e também podemos utilizar opções 
avançadas (flags) para otimizar nossas pesquisas, busca e saída conforme nossa necessidade.

Passo a Passo de uma Navegação pelo Sistema

1- Primeiro vamos localizar o diretório que estamos, usamos o comando (pwd).

2- Vamos listar todo o conteúdo que tem nesse diretório que estamos, usamos o comando (ls).

3- Caso a gente queira uma listagem com mais informações sobre o conteúdo que tem no diretório atual, usamos o comando + a flag (ls -l).

Quando utilizamos o comando (ls-l) ele nos da uma quantidade de blocos total de (1024 bytes) usado pelo arquivos e diretórios listado no diretório atual, 
isso indica o tamanho total utilizado. Significa que usava 32 blocos = 1024 bytes/32 blocos= 32.768 bytes ou 32KB de espaço no disco.

O (ls -l) nos fornece outras informações também, Exemplo:

drwxr-xr-x: Tipos de permissão que o usuário tem no arquivo.

2: Número de links rígidos para o arquivo/diretório.

cry0l1t3: Esse seria o nome do proprietário do arquivo/diretório.

htbacademy: Seria o nome do proprietário do grupo do arquivo/diretório.

4096:Tamanho do arquivo ou número de blocos usados para armazenar as informações do diretório.

Nov 13 17:37: Data e hora.

Desktop: Nome do diretório.

Mesmo assim ainda não conseguimos ver tudo que está na pasta, pois um diretório também possui arquivos ocultos. Esse arquivos possui um (.) no inicio do seu nome,
Exemplo: .bashrc

Para conseguirmos ver esse arquivos, utilizamos o comando (ls -la) vai nos fornecer uma listagem com informações completa e nos mostrar os arquivos ocultos.

Para listar o conteúdo de um diretório especifico, podemos usar "/" para especificar o caminho. Exemplo: (ls -l /var/) vai listar os arquivo do diretório "/var/".

Para mudar de diretório seguimos o mesmo raciocínio só que utilizamos o comando (cd) para podermos trocar o diretório. Exemplo: (cd /dev/shm).

E para podermos voltar ao diretório inicial (home) utilizamos o comando: (cd /home/nome do usuário) ou (cd ~).

Se digitar (cd .) mostra o diretório atual que você esta e quando usamos (cd ..) vamos para o diretório pai.

O numero de índice de um arquivo, é um identificador único atribuído para cada arquivo ou diretório do sistema. Cada índice contém informações sobre o 
arquivo como tipo, permissões, proprietário, grupo, tamanho, data de criação e localização física no disco.

Para acharmos o número do índice de um arquivo, usamos :(ls -li) ou (ls -i nome do arquivo)

Assim como no Windows, no Linux possuímos alguns atalhos.

Quando vc estiver digitando um comando exemplo ( cd /d + [TAB]) a tecla [TAB] ira completar o comendo.

Quando o terminal está cheio de coisas escrita e você deseja limpar ele, basta digitar o comando (clear) ou a tecla [CTRL + L].
