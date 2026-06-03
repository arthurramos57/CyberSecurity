Trabalhando com Arquivos e Diretórios

A diferença de trabalhar com arquivos no Linux e no Windows está em como acessamos o gerenciamos esse arquivos. No Windows utilizamos ferramentas como Explore 
para encontra, abrir e editar arquivos. Já no Linux o próprio terminal oferece uma alternativa aonde arquivos podem ser acessados e editados usando apenas os 
comandos. Esse método além de ser mais rápido e mais eficiente, pois ele nos permite editar os arquivos de forma mais interativa e sem precisa de editores.

A eficiência do terminal vem da capacidade de acessar os arquivos com apenas os comandos e nos permite modificar arquivos seletivamente usando apenas as flags. 
Além de poder executar vários comandos ao mesmo tempo, redirecionar a saída para arquivos e automatizar tarefas de edição em lote, isso economiza muito 
tempo quando você está lidando com vários arquivos ao mesmo tempo. Essa abordagem de usar a linha de comandos simplifica o fluxo de trabalho, tornando-se uma 
ferramenta inestimável para tarefas que demorariam mais se fosse feita por uma interface gráfica.

Criar, Mover e copiar

Para criar arquivos vazios utilizamos o comando (touch nome do arquivo).
EXEMPLO: (touch info.txt)
Para criar um diretório utilizamos o comando (mkdir nome do diretório)
EXEMPLO: (mkdir Storage)
Para organizar seu sistema, pode ser necessário criar vários diretórios dentro de outros diretório, e ficar digitando esse comando para cada um seria muito 
demorado. Por esse motivos utilizamos o comando (mkdir) + a flag (-p), que vai nos permitir criar vários diretórios pais automaticamente.
EXEMPLO: (mkdir -p Storage/local/user/documents)
E se a gente quiser analisar a estrutura dos diretórios pais que criamos, utilizamos o comando (tree), mas por padrão ele não vem instalado nos sistemas Linux, 
então utilizamos o comando (sudo apt install tree) para realizar a instalação do comando.
EXEMPLO: (tree .)
Você também pode criar arquivos dentro de diretório específicos apenas especificando o caminho aonde o arquivo deve ser armazenado, pode usar o 
ponto único (.) para poder indicar que você deseja começar pelo diretório atual. Essa é uma forma de você trabalhar na sua localização atual sem precisar 
digitar o caminho completo. Portanto para criar o arquivo dentro do diretório especifico utilizamos o comando (touch e o caminho do diretório).
EXEMPLO:(touch ./Storage/local/user/userinfo.txt)
Após criar você pode analisar a estrutura do diretório para ver se o arquivo foi criado no local certo.
Exemplo: (tree .)
Para mover os arquivos e diretórios utilizamos o comando (mv nome do arquivo ou diretório de origem nome do arquivo ou diretório de destino)
EXEMPLO: Vou mover o arquivo info.txt para o diretório local: (mv info.txt local)
No caso se for mover o diretório user para o diretório perfil: (mv user perfil)
Para renomear arquivos e diretórios utilizamos o comando (mv nome do arquivo e diretório novo nome do arquivo ou diretório)
EXEMPLO: Arquivos (mv info.txt file1.txt)
Diretório (mv History História)
Para copiarmos arquivos e diretórios usamos o comando (cp nome do arquivo ou diretório nome da copia do arquivo ou diretório).
EXEMPLO: Arquivo: (cp file1.txt file1.txt.copy)
Diretório: (cp História História.copy)
Caso você queira copiar o arquivo de um diretório para outro diretório utilizamos o comando (cp diretório/arquivo caminho até esse diretório).
Exemplo: Quero copiar o arquivo readme.txt do diretório Storage para o diretório local, então usamos: (cp Storage/readme.txt Storage/local)
Para verificarmos quando o arquivo foi modificado, usamos (ls -lt).
Para visualizarmos o numero inode do arquivo, usamos (ls -i nome do arquivo).

Edição de Arquivos

Existem várias formas de editar arquivos no Linux e tendo alguns editores de texto bem comuns e mais usado. No entanto, vamos começar pelo editor que é 
menos usado, pois vai ser mais fácil de entender como funciona a edição de arquivo.
Para criar e ditar um arquivo usando o (nano), podemos especificar o nome do arquivo diretamente como primeiro parâmetro ao iniciar o editor.
Quero criar um arquivo, comandado: (nano nome do arquivo), exemplo: (nano file2.txt.g)
Quero apenas editar o arquivo, comando: (nano nome do arquivo), exemplo: (nano file1.txt)
Se o arquivo não existir, o (nano) abre uma tela em branco e cria o arquivo quando você salva com a tecla (Ctrl+0+Enter).
Se o arquivo já existir, ele apenas abre para edição.
Quando você executa esse comando abrirá um editor, permitindo que você comece a editar o arquivo imediatamente. A interface do (nano) é bem fácil de ser 
usada e entendida, isso o torna uma ótima escolha para quem deseja editar arquivos de texto rapidamente, especialmente se você é um iniciante na área.
A tecla ( CTRL + W) é muito utilizada pós ela nos permite pesquisar uma palavra dentro do arquivo.
EXEMPLO: aperto a tecla (CTRL + W) ira abrir uma barra de pesquisa, ire digitar a palavra "você" que estou procurando e apertar a tecla (ENTER), 
quando fizer isso ele irá levar o curso até a primeira palavra "você" e assim conforme eu for apertando e pressionado a tecla (CTRL+W) (ENTER) ele 
ira me levar até outra palavra "você".
É para salvar a edição que fizemos no arquivo, utilizamos a tecla (CTRL+0) (ENTER).
E para sair do editor, utilizamos a tecla (CTRL+X).

Visualizar Arquivos 

Para visualizarmos o conteúdo de um arquivo, utilizamos o comando (cat nome do arquivo)
EXEMPLO: (cat file1.txt)
Em sistemas Linux, há vários arquivos que podem ser extremamente benéficos para testadores de penetração, devido a permissões mal configuradas ou 
configuração de segurança insuficiente por parte dos administradores. Um desses arquivos mais importante é o arquivo (/etc/passwd) esse arquivo 
contem varias informações essenciais sobre usuários do sistema, nomes de usuário registrado, IDs de usuário, IDs de grupo e diretórios iniciais.

O arquivo (/etc/passwd) armazenava também hashes de senha, mas agora os hashes são armazenada em (/etc/shadow) que possui permissões mais restrita. 
No entanto, se as permissões em arquivos críticos ou outros não forem configuradas corretamente, isso pode expor informações sensíveis ou levar a 
uma oportunidade de escalonamento de privilegio.

Como os testadores de penetração, ao identificar arquivos diretos ou permissões inadequadas pode fornecer insights importante sobre vulnerabilidades 
que podem ser exploradas, contas de usuário fracas ou acesso de arquivos mal configurado que deveriam ser restringidos. Compreender esses arquivos é 
vital para avaliar e manter a postura de segurança do sistema.

Editor de Arquivos

Temos também o editor (vim). Em contraste com o (nano), o (vim) é um editor modal que pode distinguir entre texto e entrada de comandos. O (vim) oferece um total de 6 tipos de modo 
que deixam nosso trabalho mais fácil e tornam este editor muito poderoso.

Modo
Normal: Nesse todas as entradas são considerada comandos de editor, não há inserção dos caracteres inseridos no buffer do editor, como acontece na 
maioria dos outros editores. Quando iniciamos o editor entramos no modo normal.
Insert: Com algumas exceções, todas as escritas inseridas são inseridas no buffer.
Visual: Apenas usado para marcar uma parte contígua do texto, que será destacada visualmente. Quando posicionamos o cursor, mudamos a 
área selecionada. A área seleciona pode ser editada de varias formas como exclui-la, copiar ou substitui-la.
Command: Ele nos permite inserir comandos de linha única na parte inferior do editor. Podemos usar isso para ordenar, substituir seções de texto ou 
exclui-las, por exemplo.
Replace: Nesse modo substituir, o texto recém-inserido substituirá caracteres existentes, a menos que não haja mais caracteres antigos na posição atual 
do cursor. Depois, o texto recém-inserido será adicionado.
Ex: Emula o comportamento do editor de texto (Ex), um dos predecessores de (vim). Fornece um modo onde podemos executar múltiplos comandos sequencialmente 
sem retornar ao modo Normal após cada comando.
Quando o editor (vim) está aberto, podemos entrar no modo de comando digitanto ":" e depois degitando "q" para fechar o (vim).
