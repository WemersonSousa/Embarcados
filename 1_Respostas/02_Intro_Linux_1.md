  # Atividade 2 - Sistemas Operacionais Embarcados.


   1. Por que o Linux recebeu esse nome?
      -Linux vem de Linus + Unix, sendo Linu, vindo do nome do criador do Linux, Linus Torvalds e Unix vindo do nome de um sistema operacional já existente.

   2. O que são daemons?
      -Daemon é um programa que executa um serviço em segundo plano, ao invés de ser diretamente controlado pelo usuário.

   3. O que é o shell?
      -Shell nada mais é que uma interface através da qual o usuário tem acesso aos serviços de um sistema operacional.

   4. Por que é importante evitar executar o terminal como super-usuário?
    -Por segurança, uma vez que você possa cometer algum erro enquanto alterando seu sistema, sem pensar direito, e enquanto se digita a senha, tem-se tempo para pensar sobre tal ação. Além disso, todas as aplicações então funcionariam com privilégios de super usuário, o que faz com que qualquer vulnerabilidade existente no seu computador possa levar seu sistema operacional à falha, pois virus teriam acesso à qualquer parte do sistema.

   5. Qual botão do teclado completa o que o usuário escreve no terminal, de acordo com o contexto?
    -A tecla Tab

   6. Quais botões do teclado apresentam instruções escritas anteriormente?
    - As teclas cima, ou baixo
   

   7. Apresente os respectivos comandos no terminal para: 
   
   -(a) Obter mais informações sobre um comando. 
    info comando ; Sendo comando, o comando desejado
    
   -(b) Apresentar uma lista com os arquivos dentro de uma pasta. 
    ls /pasta   ; sendo pasta, o caminho da pasta desejada
    
   -(c) Apresentar o caminho completo da pasta. 
    $pwd
    
   -(d) Trocar de pasta. 
   cd /pasta1/pasta2 ; sendo que inicialmente cd leva para a pasta "home", então a pasta1 tende a ser o usuário
   
   -(e) Criar uma pasta. 
   Estando na pasta onde deseja-se criar nova pasta, usa-se o comando: mkdir [pasta]
   
   -(f) Apagar arquivos definitivamente. 
   rm nomedoarquivo ;desde que se esteja na pasta do arquivo
   
   -(g) Apagar pastas definitivamente. 
   rmdir /diretorio ; desde que a pasta esteja vazia
   rm - r /diretorio ; caso a pasta não esteja vazia
   
   -(h) Copiar arquivos. 
   cp /diretorio/arquivocopiado /diretoriodestino ; sendo diretorio o diretorio do arquivo copiado, e diretorio destino onde ele será colado
   
   -(i) Copiar pastas. 
   cp - r /diretorio1 /diretorio2 ; sendo diretorio1 copiado para dentro do diretório2
   
   -(j) Mover arquivos. 
   mv /diretorio/arquivocopiado /diretoriodestino ; sendo diretorio o diretorio do arquivo copiado, e diretorio destino onde ele será colado
   
   -(k) Mover pastas. 
   mv /diretorio1 /diretorio2 ; sendo diretorio1 copiado para dentro do diretório2
   
   -(l) Renomear pastas. 
   mv /diretorio1 /diretorio01 ; sendo diretorio1 o nome inicial da pasta e diretorio01 o novo nome, desde que já não exista pasta com tal nome
   
   -(m) Apresentar o conteúdo de um arquivo. 
   cat /diretorio/arquivo ; sendo arquivo o nome do mesmo, contendo sua extensão
   
   -(n) Apresentar o tipo de um arquivo. 
   
   
   -(o) Limpar a tela do terminal. 
   clear
   
   -(p) Encontrar ocorrências de palavras-chave em um arquivo-texto. 
   file /diretorio/nomedoarquivo  ; sendo diretorio o local do arquivo e nomedoarquivo seu nome contendo extensão
   
   -(q) Ordenar informações em um arquivo-texto. 
   sort /diretorio/nomedoarquivo  ; sendo diretorio o local do arquivo e nomedoarquivo seu nome contendo extensão
   
   -(r) Substituir ocorrências de palavras-chave em um arquivo-texto. 
   sed -i s/anterior/nova/g diretorio/nomedoarquivo ; sendo diretorio o local do arquivo e nomedoarquivo seu nome contendo extensão
   
   -(s) Conferir se dois arquivos são iguais. 
   cmp ~/diretorio1/nomedoarquivo1 ~/diretorio2/nomedoarquivo2 ; sendo diretorios e nomes dos arquivos como explicados anteriormente
   
   -(t) Escrever algo na tela.
    screen
