Encontrar Arquivos e Diretórios 

É fundamental conseguir encontrar arquivos e pasta que precisamos. Quando se tem acesso a um sistema Linux ou baseado em Linux, é essencial encontrar arquivos 
de configuração, scripts criados pelos usuários ou pelo administrador, além de outros arquivos e pasta. E não precisamos navegar manualmente por cada pasta e 
verificar quando foi modificada pela última vez. Existe alguns comandos que pode facilitar esse trabalho.

Which

Um dos comandos mais comum é (which). Esse comando retorna o caminho para o arquivo ou link que deve ser executado. Isso nos permite determinar se programas 
específicos, como cURL, netcat, wget, python, gcc, estão disponíveis no sistema operacional.
Exemplo: Utiliza-lo para buscar o Python.
(which python)
Resultado: /usr/bin/python
Caso o programa não existe no sistema, não aparecerá nenhum resultado.

Find

Um comando muito útil é o (find), pois além da função de encontrar arquivos e pastas, essa ferramenta também contém a função de 
filtrar os resultados. Podemos usar parâmetros de filtros como o tamanho ou a data e também podemos especificar se estamos buscando
apenas arquivos ou pastas.
Exemplo:(findo diretório/caminho filtro/nome, tipo tamanho e etc expreção/como ser executada o arquivo encontrado)
Agora um exemplo do comando sendo usado com as opções.
(find / type f -name *.conf -user root -size +20k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null)
Vamos enteder o que significa cada opção que usamos no comando anterior.

Opções

(type f): Aqui, definimos o tipo de objeto buscado. Neste caso, "f" significa "file(arquivo)".

(name *.conf): Com o "name" indicamos o nome do arquivo q estamos procurando. O asterisco (*) representa arquivos 'todos' com a extensão ".conf".

(user root): Essa opção filtra todos os arquivos cujo o dono é o usuário root.

(size +20k): Podemos filtrar todos os arquivos localizado e especificar que queremos os que são maiores que 20 KiB.

(newermt 2020-03-03): Essa opção, marcamos a data. Apenas os arquivos mais recentes que a data especificada serão apresentados.

(exec ls -al {} \;): Essa opção executa comandos especificados, usando os colchetes curvados como marcadores para cada resultado. 
A barra inversa escapa do próximo caractere para ser interpretado pela shell porque, caso contrário, o ponto e vírgula termina o comando 
e não alcançaria o redirecionamento.

(2>/dev/null): Esta é uma redirecionação para o "STDERR null device not", que voltaremos na próxima seção. Essa redireção garante que 
nenhum erro seja exibido no terminal. Esse redirecionamento deve ser uma opção do comando 'encontrar'.

Locate

Leva muito tempo para pesquisar em todo o sistema os arquivos e diretórios para realizar várias busca diferente. O comando (locate) nos oforece 
uma maneira mais rápida de pesquisar pelo sistema. Em contraste com o comando, funciona com o banco de dados que contém todas as 
informações sobre arquivos e pasta existente. Podemos atualizar esse banco de dados com o seguinte comando:

(sudo updatedb)

Se buscarmos todos os arquivos com a extensão ".conf find", você verá que essa busca produz mais resultado e mais rápido do que usar o comando:

(locate *.conf)

No entanto, esse comando não tem muitas opções de filtro para usar. Portanto, sempre vale a pena considerar se podemos usar o
comando ou usar o comando (locate), sempre dependendo do que estamos procurando.
