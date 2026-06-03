Introdução ao Shell

Aprender a usar o shell do Linux é muito importante, pois muitos servidores são baseado no Linux. São frequentemente usado porque o Linux é 
menos propenso a ter erros do que os servidores Windows. Exemplo, servidores web são baseados em Linux. Saber como o sistema operacional funciona 
para poder controlalo de forma eficaz requer entender e dominar a parte essencial do Linux. Um terminal Linux que é chamado também de linha de comando, fornece 
uma interface de entrada/saída (I/O) que é baseado em texto entre usuário e o karnel do sistema de computadores. O termo console é bem típico, mas não se refere 
a janela, mais sim em uma tela no modo texto. No terminal, o comando pode ser escrito para controlar o sistema, podemos pensar em um shell como uma 
interface gráfica que se basea em texto aonde digitamos o comando para realizar ações como: navegar para outro diretório, trabalhar com arquivos e 
obter informações do sistema.

Emulador de Terminal

Um software que emula a função de um terminal. Ele permite o uso de programas baseado em textos dentro de uma interface gráfica de um usuário. Existe também as 
interfaces de linha de comando que funciona como terminais adicionais a um terminal. Resumo, o terminal serve para interpretar o shell.

Exemplo de Terminal: Imagine que você está em um grande prédio de escritórios onde o shell é a sala principal de servidores que processa todos os dados e comandos 
da empresa. O terminal é como uma mesa de recepcionista que serve como ponto de comunicação com a sala de servidores. Você vai até a recepcionista (terminal) 
para entregar instruções ou pedidos na sala de servidores (shell).

Exemplo de um Emulador de Terminal:Agora, suponha que você esteja trabalhando remotamente. O software de emulação de terminal funciona como a mesa virtual de 
recepcionista na tela do seu computador (a interface gráfica), permitindo que você interaja com a sala de servidores sem estar fisicamente presente 
no escritório. Ele emula a função da mesa real da recepcionista, permitindo que você use programas e comandos baseados em texto dentro de um ambiente gráfico.

Emuladores de terminal e multiplexadores são extensão benéficas para o terminal. Fornece diferentes métodos e funções para trabalhar, dividir o terminal em 
uma única janela, trabalhar em múltiplos diretórios, criar diferentes espaços de trabalho. Exemplo, o multiplicador chamado tmux.

Shell

O shell mais comumente usado no Linux, faz parte do projeto GNU. Tudo que fazemos com a interface gráfica podemos fazer com a carcaça. O shell nos da 
a possibilidade de interagir com programas e processos para obter informações rapidamente. Além de que, muitos processos podem ser automatizados com 
script menores e maiores, que facilita o trabalho manual.

Além do (BASH), também existe outras conchas como TCSH/CSH, KSH, ZSH, FISH shell e outros.

Descrição do Prompt

O prompt é um bash simples de entender. Por padrão, ele mostra as informações do nome de usuário e nome do seu computador (Host) e a pasta/diretório em 
que você está trabalhando atualmente. E uma linha de texto que aparece na tela para mostrar que o sistema está pronto para você. O prompt aparece 
em uma nova linha, e o cursor ( linha piscando ou caixa) é colocado logo após ela, esperando você digitar o comando.

Ele pode ser personalizado para fornecer informações úteis ao usuário. O seu formato:

<nome de usuário>@<nome do host><pasta e o diretório>$

Diretório inicial é marcado com o tilde <> e é a pasta padrão quando fazemos o login. (~)

<nome de usuário>@<nome do host>[~]$

Cifrão neste caso significa usuário e quando mudamos para o root ele fica com (#): (root hash #)

root@htb[/htb]#

Quando executamos o shell no sistema de destino, podemos não ver o nome de usuário, nome do host e diretório atual. Isso pode ser devido à variável do PS1 
no ambiente não estar configurada corretamente. Quando isso ocorre vemos os seguintes prompts:

Sem Privilegio - Usuário Shell Prompt

$

Com Privilegio - Root Prompt Shell

#


Variável nos sistemas Linux controla como seu prompt de comando ira aparecer no terminal. É um modelo que define como você vai ver o comando toda vez 
que estiver pronto para digita-lo no terminal. Quando você personaliza a variável do PS1, você pode alterar seu prompt para exibir informações como o
nome de usuário, nome do computador, pasta atual que você está ou até mesmo adicionar cores e caracteres especiais. Isso permite você personalizar a 
interface para deixar mais informativa ou visualmente mais atraente. (PS1)

Além de exibir informações básicas como o nome de usuário e a pasta atual, você pode personalizar o prompt de comando para mostrar outros detalhes como: 
endereço de IP, data, hora ou falha do último comando. Essa personalização é bem útil em teste de penetração porque ela vai permitir você acompanhar suas 
ações de forma mais eficaz. Exemplo, você pode configurar o prompt para mostrar o caminho completo do diretório de trabalho atual e até incluir o 
endereço de IP do alvo, se for necessário. Uso de ferramenta ou até revisando arquivos (localizado no diretório atual do usuário) você pode 
registrar todos o comandos que usou e organiza-los por data e hora, isso ajuda na documentação e análise. (script .bash_history)

O prompt pode ser personalizado usando caracteres e variáveis especiais no arquivo de configuração do shell (para o shell Bash). 
Exemplo, podemos usar: o caractere para representar o nome de usuário atual, para o nome de host e para o diretório de trabalho 
que você está. ( .bashrc \u, \h, \w )

(\d) Data (seg, 6 de fevereiro)
(\D) Data (YYY-MM-DD)
(\H) Nome completo do Host
(\j) Número de trabalhos gerenciados pela concha
(\n) Newline
(\r) Retorno de vagão
(\s) Nome da concha
(\t) Horário atual 24 horas (HH:MM:SS)
(\T) Tempo atual: 12 horas (HH:MM:SS)
(\@) Nome de Usuário atual
(\w) Caminho Completo do Diretório de trablho

Personalizar o prompt pode ser uma maneira útil de torna sua experiência no terminal mais eficiente. Também pode ser uma ferramenta para resolução 
de problemas, pois pode fornecer informações de como está o sistema a qualquer momento.

Além de personalizar só o prompt, podemos personalizar o ambiente do terminal mudando cores, fontes e outra configuração para tornar o 
ambiente mais atraente visualmente e mais fácil de utilizar.
