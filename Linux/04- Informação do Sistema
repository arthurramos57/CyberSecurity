Informações do Sistema

Trabalhamos com vários sistemas Linux, nesse meio é importante entender sua estrutura, detalhe do sistema, processo, configuração de rede, 
usuário/configuração do usuário e diretórios. A maioria das ferramentas já vem pré-instalada, no entanto esse conhecimento não é só para 
tarefas rotineiras no Linux, mas desempenha um papel fundamental na avaliação de configuração de segurança, identificação de vulnerabilidade 
ou prevenção de riscos potencias de segurança em sistemas Linux.

Comandos

(whoami): Exibe o nome de usuário atual.
(id): Retorna a identidade do usuário.
(hostname): Define ou imprime o nome do sistema maquina atual.
(uname): Imprime informações básica sobre o nome do sistema operacional e o hardware.
(pwd): Retorna o nome do diretório funcional.
(ifconfig): É usado para atribuir ou visualizar um endereço a uma interface de rede e/ou configurar parâmetros da interface de rede.
(ip): É uma ferramenta para mostrar ou manipular roteamento, dispositivos de rede, interfaces e túneis.
(netstat): Mostra o status da rede.
(ss): Outra utilidade para investigar tomadas.
(ps): Mostra status do processo.
(who): Mostra quem está logado.
(env): Imprime o ambiente ou define e executa comandos.
(lsblk): Listas, bloqueiam dispositivos.
(lsusb): Lista de dispositivos USB.
(lsof): Lista de arquivos abertos.
(lspci): Lista de dispositivos PCI.

Login via SSH

Um protocolo que permite os clientes acessar e executar comandos ou ações em computadores remotos. Em host e servidores baseados em Linux, assim como os 
sistemas operacionais do tipo Unix, o SSH é uma ferramenta padrão e pré-instalada e é a escolha preferida de muitos administradores para configurar e manter 
um computador por meio de acesso remoto, é um protocolo mais antigo e muito comprovado que não requer e nem oferece uma interface gráfica(GUI). Por isso, ele 
funciona de forma eficiente e ocupa pouquíssimos recursos.

Para conectar nas maquinas remotas: ssh htb-student@[endereço de IP]

Exemplos de Comandos que utilizamos quando acabamos de logar

(hostname): Ele imprime o nome do computador que estamos logados.

(whoami): A gente utiliza ele para obter o nome de usuário atual, esse comando funciona tanto para Linux e Windows. Durante uma avaliação de segurança,
para obtermos acesso reverso ao shell em um host e uma das primeiras etapas que fazemos nessa situação é descobrir o usuário que estamos usando. A partir daí, 
conseguimos descobrir se o usuário tem algum privilégio/acesso especial.

(id): Mostra o id do usuário, isso é bem útil para testadores de penetração pelo fato de que conseguimos saber qual os acessos que usuário tem, 
se ele é administrador, as permissões que ele tem e os grupos que ele está. O grupo é de muito interesse nessa área pois ele mostra se o usuário 
pode ler arquivos de log ou até mesmo obter informações sensíveis que pertence a um grupo particular de administradores de sistema e isso significa que o 
usuário pode executar alguns ou todos os comandos como um super-usúario(usuário Root). Os diretos do comando (Sudo) que só administradores ou usuários q pertence 
a esse grupo eles tem permissões de executar comandos, escalar privilégios, pode auditar permissões de usuários, pode remover usuários de grupos, remover e 
criar arquivos e diretórios e ter acesso a arquivos sensíveis.

(Uname): O comando nos dá todas as informações da maquina em uma ordem especifica: nome do kernel, nome do host, versão do kernel, 
nome do hardware da maquina e sistema operacional, mas podemos utilizar flags para omitir informações separadas.

(uname -a): Conseguimos ver o nome do kernel, nome do host, versão do kernel. E nos dá saída especifica de bits que nos interessa

(uname -r): Nos mostra somente a versão do Kernel, é muito utilizado quando queremos buscar possíveis exploits do kernel.

Para saber as demais flags do comando e suas descrição, utilizamos o comando (man nome do comando).

Para fazer o caminho até a caixa de correios do usuário, usamos: (/var/mail/nome do usuário)

Achar o shell especificado do usuário, usamos: (grep htb-student /etc/passwd | cut -d: -f7)

Para ir até o diretório inicial, usamos: (/home/nome do usuário)
