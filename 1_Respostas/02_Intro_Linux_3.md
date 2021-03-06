Para todas as questões, escreva os scripts e as chamadas correspondentes no terminal.

1. Crie um arquivo com nome _teste1.txt_, e escreva nele o texto "Número do arquivo = 1". Repita o procedimento para os arquivos _teste2.txt_, _teste3.txt_, ..., _teste100.txt_, escrevendo o texto correspondente para cada um deles ("Número do arquivo = 2", "Número do arquivo = 3", ..., "Número do arquivo = 100").

```
$ cat > exe1.sh   #inicia um documento de texto em branco (o script). com a função cat que torna possível usar o terminal como um "bloco de notas" para escrever arquivos de texto longos, também seria possível usar função echo e digitar linha por linha
```

```
#!/bin/bash   

for i in {1..100}

do

echo Número do arquivo = $i > teste$i.txt

done

#esse é todo o escopo de texto necessário para o programa. Para finalizar o "bloco de notas" usa-se ctrl+z
```

`
$ chmod +x teste.sh   # caso o script não esteja executável, basta usar o comando chmod +x

$ ./exe1.sh           # executa o script que cria os arquivos txt
`

2. Faça um script chamado _cals.sh_ que apresente o calendário de vários meses indicados pelo usuário, usando o seguinte formato:

```script
./cals.sh MES1 ANO1 MES2 ANO2 MES3 ANO3
```

Não limite o script a 3 meses. Ele deve funcionar para vários casos, como por exemplo:

```script
./cals.sh 1 2020
./cals.sh 1 2019 2 2020 3 2021 1 2010
```

```
cat > cals.sh #mais uma vez usando a função cat para escrever o script
```

```
#!/bin/bash

flag=0                      #flag usada para determinar o que é mes e o que é ano

mes=""                      #variáveis que vai armazenar os meses  

for vars in $@              #enquanto haver variáveis passadas, ele roda o loop

do

if [ $flag -eq 0 ]; then    #se for uma entrada par (mes)

mes=$vars           #salva o mes na variável

flag=1              #ativa a flag

elif [ $flag -eq 1 ]; then  #se for uma entrada impar (ano)

cal $mes $vars      #usa função cal para chamar o mes e ano

flag=0              #reseta flag, para valer para mais de 1 mes

fi                          #finaliza o if

done

#para finalizar novamente, basta apertar ctrl + Z
```

```
./cals.sh 3 2020 4 2020 #apenas um exemplo de chamada do script para o mês atual e próximo mes, para confirmar o funcionamento
```

3. Utilizando a lógica do script anterior, descubra em que dia da semana caiu o seu aniversário nos últimos dez anos.

```
cat > dates.sh #mais uma vez usando a função cat para escrever o script
```

```
#!/bin/bash

flag=0                      #flag usada para determinar o que é dia e o que é mes

mes=""                      #variáveis que vai armazenar o mes ou meses

for vars in $@              #enquanto haver variáveis passadas, ele roda o loop

do

if [ $flag -eq 0 ]; then    #se for uma entrada par (mes)

mes=$vars           #salva o mes na variável

flag=1              #ativa a flag

elif [ $flag -eq 1 ]; then  #se for uma entrada impar (dia)

for i in 10 11 12 13 14 15 16 17 18 19 #ultimos 10 anos, já que 2020 ainda não chegou

do date -d $vars/$mes/20$i    #printa as datas nos ultimos 10 anos
done 

flag=0                         #reseta flag, para valer para mais de 1 aniversário

fi                          #finaliza o if

done

#para finalizar novamente, basta apertar ctrl + Z
```

```
./dates.sh  4 4 5 4      #para o caso do dia 4/4 e 5/4, meu aniversário (4/4) e mais um dia para teste de multiplas datas
```

4. Crie um arquivo _sites.txt_ com o seguinte conteúdo:

```
https://github.com/DiogoCaetanoGarcia/Sistemas_Embarcados/raw/master/Aulas/01_Linux%20b%C3%A1sico.pdf
https://github.com/DiogoCaetanoGarcia/Sistemas_Embarcados/raw/master/Aulas/01_Linux%20b%C3%A1sico_Shell_Script.pdf
https://github.com/DiogoCaetanoGarcia/Sistemas_Embarcados/raw/master/Aulas/01_Sistemas%20Embarcados%20-%20Aula%201%20-%20Introdu%C3%A7%C3%A3o.pdf
```

Estes são links para slides de 3 aulas desta dsciplina, um para cada linha do arquivo _sites.txt_. Faça um script que faz o download destes slides automaticamente, a partir do arquivo _sites.txt_. (DICA: use o comando wget.)

```
cat > sites.sh #mais uma vez usando a função cat para escrever o script
```

```
#!/bin/bash

wget https://github.com/DiogoCaetanoGarcia/Sistemas_Embarcados/raw/master/Aulas/01_Linux%20b%C3%A1sico.pdf
wget https://github.com/DiogoCaetanoGarcia/Sistemas_Embarcados/raw/master/Aulas/01_Linux%20b%C3%A1sico_Shell_Script.pdf
wget https://github.com/DiogoCaetanoGarcia/Sistemas_Embarcados/raw/master/Aulas/01_Sistemas%20Embarcados%20-%20Aula%201%20-%20Introdu%C3%A7%C3%A3o.pdf

#novamente se finaliza com ctrl + Z
```

```
./sites.sh     #para acessar os sites, basta rodar o script
```
5. Faça um script chamado _up.sh_ que sobe _N_ níveis na pasta onde você estiver, usando $1 como parâmetro de entrada. Por exemplo, se você estiver em **/home/aluno/Documents** e executar **./up.sh 2**, você automatica

```
cat > up.sh #mais uma vez usando a função cat para escrever o script
```

  ```
 #!/bin/bash
  var=$@                #passa a variável para var
  while [ $var -ge 1 ]  # enquanto a for diferente de 0
  do
  cd ..                 #volta uma pasta
  var=$((var-1))        #decrementa a variável
  done
  #novamente se finaliza com ctrl + Z
```

```
. ./up2.sh 6      #o ponto no inicio se faz necessário para rodar o script fora do subshell

```
