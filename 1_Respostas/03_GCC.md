Para todas as questões, compile-as com o gcc e execute-as via terminal.

1. Crie um "Olá mundo!" em C.

```
$ cat > main.c #iniciando escrita do código no arquivo main.c
```

``` 
//Escrevendo o código através do "bloco de notas"
#include <stdio.h> //biblioteca que contém função printf

  int main(){
  
    printf("Olá mundo!\n");
  
  return 0;} // para finalizar o "bloco de notas" aperta-se ctrl+Z
```

```
$ gcc main.c -o ola_mundo #compila-se o programa usando o gcc e salva-o com o nome ola_mundo

$ ./ola_mundo #executa o programa criado
```

2. Crie um código em C que pergunta ao usuário o seu nome, e imprime no terminal "Ola " e o nome do usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_1':

```bash
$ ./ola_usuario_1
$ Digite o seu nome: Eu
$ Ola Eu
```

```
$ cat > main.c #iniciando escrita do código no arquivo main.c
```

```
#include <stdio.h>    //biblioteca printf

#include <stdlib.h>   //biblioteca strings

int main(){

int i=0;    

char *c;

char l;

c = (char*)malloc(sizeof(char));  //ajuste na variável c (remover lixo)

printf("Digite o seu nome: ");      //texto inicial

while(scanf("%c", &l) == 1 && l != '\n'){   //scanf até ser digitado enter
      
      c[i] = l;   //armazena cada caractere       
      
      i++;        //incrementado para deslocar os caracteres ao longo de c
       
       c = (char*)realloc(c, (i+1) * sizeof(char)); //ajuste na variável c (remover lixo)
}

printf("Ola %s\n", c); // printf

return 0; // para finalizar o "bloco de notas" aperta-se ctrl+Z

}
```

```
$ gcc main.c -o ola_usuario_1 #compila-se o programa usando o gcc e salva-o com o nome ola_usuario_1

$ ./ola_usuario_1  #executa o programa criado
```


3. Apresente os comportamentos do código anterior nos seguintes casos:

(a) Se o usuário insere mais de um nome.
```bash
$ ./ola_usuario_1
$ Digite o seu nome: Eu Mesmo
```

```
Digite o seu nome: Eu Mesmo

Ola Eu Mesmo
```

(b) Se o usuário insere mais de um nome entre aspas duplas. Por exemplo:
```bash
$ ./ola_usuario_1
$ Digite o seu nome: "Eu Mesmo"
```

```
Digite o seu nome: "Eu Mesmo"
Ola "Eu Mesmo"
```


(c) Se é usado um pipe. Por exemplo:
```bash
$ echo Eu | ./ola_usuario_1
```

```
Digite o seu nome: Ola Eu
```

(d) Se é usado um pipe com mais de um nome. Por exemplo:
```bash
$ echo Eu Mesmo | ./ola_usuario_1
```

```
Digite o seu nome: Ola Eu Mesmo
```

(e) Se é usado um pipe com mais de um nome entre aspas duplas. Por exemplo:
```bash
$ echo "Eu Mesmo" | ./ola_usuario_1
```

```
Digite o seu nome: Ola Eu Mesmo
```

(f) Se é usado o redirecionamento de arquivo. Por exemplo:
```bash
$ echo Ola mundo cruel! > ola.txt
$ ./ola_usuario_1 < ola.txt
```

```
Digite o seu nome: Ola Ola mundo cruel!
```

4. Crie um código em C que recebe o nome do usuário como um argumento de entrada (usando as variáveis argc e *argv[]), e imprime no terminal "Ola " e o nome do usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_2':

```bash
$ ./ola_usuario_2 Eu
$ Ola Eu
```

```
$ cat > main.c #iniciando escrita do código no arquivo main.c
```

```
  #include <stdio.h>

  #include <stdlib.h>

  int main(int argc, char *argv[]){

    printf("Ola "); //printa Ola, sem o \n pra não pular linha

    for (int i = 1; i < argc; ++i) // enquanto ainda haver variáveis de entrada (argc armazena a quantidade de entradas)

  {

    printf("%s ", argv[i]);       //printa a entrada

    }

    printf("\n");

    return 0;

  }

```

```
$ gcc main.c -o ola_usuario_2 #compila-se o programa usando o gcc e salva-o com o nome ola_usuario_2

$ ./ola_usuario_2 Eu  #executa o programa criado
```


5. Apresente os comportamentos do código anterior nos seguintes casos:

(a) Se o usuário insere mais de um nome.
```bash
$ ./ola_usuario_2 Eu Mesmo
```

```
Ola Eu Mesmo
```

(b) Se o usuário insere mais de um nome entre aspas duplas. Por exemplo:
```bash
$ ./ola_usuario_2 "Eu Mesmo"
```

```
Ola Eu Mesmo
```

(c) Se é usado um pipe. Por exemplo:
```bash
$ echo Eu | ./ola_usuario_2
```

```
Ola
```

(d) Se é usado um pipe com mais de um nome. Por exemplo:
```bash
$ echo Eu Mesmo | ./ola_usuario_2
```

```
Ola
```

(e) Se é usado um pipe com mais de um nome entre aspas duplas. Por exemplo:
```bash
$ echo Eu Mesmo | ./ola_usuario_2
```

```
Ola
```

(f) Se é usado o redirecionamento de arquivo. Por exemplo:
```bash
$ echo Ola mundo cruel! > ola.txt
$ ./ola_usuario_2 < ola.txt
```

```
Ola
```

6. Crie um código em C que faz o mesmo que o código da questão 4, e em seguida imprime no terminal quantos valores de entrada foram fornecidos pelo usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_3':

```bash
$ ./ola_usuario_3 Eu
$ Ola Eu
$ Numero de entradas = 2
```

```
$ cat > main.c #iniciando escrita do código no arquivo main.c
```

```
  #include <stdio.h>

  #include <stdlib.h>

  int main(int argc, char *argv[]){

    printf("Ola "); //printa Ola, sem o \n pra não pular linha

    for (int i = 1; i < argc; ++i) // enquanto ainda haver variáveis de entrada (argc armazena a quantidade de entradas)

  {

    printf("%s ", argv[i]);       //printa a entrada
    

    }
    printf("\nNumero de Entradas = %d", argc); //pula linha e printa o número de entradas

    printf("\n");

    return 0;

  }

```

```
$ gcc main.c -o ola_usuario_3 #compila-se o programa usando o gcc e salva-o com o nome ola_usuario_3

$ ./ola_usuario_3 Eu  #executa o programa criado
```



7. Crie um código em C que imprime todos os argumentos de entrada fornecidos pelo usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_argumentos':

```bash
$ ./ola_argumentos Eu Mesmo e Minha Pessoa
$ Argumentos: Eu Mesmo e Minha Pessoa
```

```
$ cat > main.c #iniciando escrita do código no arquivo main.c
```

```
  #include <stdio.h>

  #include <stdlib.h>

  int main(int argc, char *argv[]){

    printf("Argumentos: "); //printa Ola, sem o \n pra não pular linha

    for (int i = 1; i < argc; ++i) // enquanto ainda haver variáveis de entrada (argc armazena a quantidade de entradas)

  {

    printf("%s ", argv[i]);       //printa a entrada

    }

    printf("\n");

    return 0;

  }

```

```
$ gcc main.c -o ola_argumentos #compila-se o programa usando o gcc e salva-o com o nome ola_argumentos

$ ./ola_argumentos Eu Mesmo e Minha Pessoa  #executa o programa criado
```

8. Crie uma função que retorna a quantidade de caracteres em uma string, usando o seguinte protótipo:
`int Num_Caracs(char *string);` Salve-a em um arquivo separado chamado 'num_caracs.c'. Salve o protótipo em um arquivo chamado 'num_caracs.h'. Compile 'num_caracs.c' para gerar o objeto 'num_caracs.o'.

```
$ cat > num_caracs.h #iniciando escrita do código no arquivo main.c
```

```
#include <stdio.h>

#include <stdlib.h>

int Num_Caracs(char *string);
```

```
$ cat > num_caracs.c #iniciando escrita do código no arquivo num_caracs.c
```

```
  
#include "num_caracs.h"

int Num_Caracs(char *string){

  int i=0;

  char c = 0;

        do{
          
          c = string[i]; //c recebe cada caractere da entrada
          
          if(c != '\0') //incrementa i enquanto não chega no espaço
          
          i++;
        
        }while(c != '\0');  //enquanto não for recebido o espaço
        
  
   return i;  //retorna i
   
} 
```

```
gcc -c num_caracs.c #comando que cria num_caracs.o
```

9. Re-utilize o objeto criado na questão 8 para criar um código que imprime cada argumento de entrada e a quantidade de caracteres de cada um desses argumentos. Por exemplo, considerando que o código criado recebeu o nome de 'ola_num_caracs_1':

```bash
$ ./ola_num_caracs_1 Eu Mesmo
$ Argumento: ./ola_num_caracs_1 / Numero de caracteres: 18
$ Argumento: Eu / Numero de caracteres: 2
$ Argumento: Mesmo / Numero de caracteres: 5
```

```
$ cat > ola_num_caracs_1.c #iniciando escrita do código no arquivo num_caracs.c
```

```
#include <stdio.h>

#include <stdlib.h>

#include "num_caracs.h"

int main(int argc, char *argv[]){

        int c = 0;
        
        for (int i = 0; i < argc; ++i)
        
        {       
        
                c = Num_Caracs(argv[i]); //c recebe o número de caracteres de cada palavra
                
            printf("Argumento: %s / Número de caracteres: %d\n", argv[i], c); //printa cada palavra  numero de caracteres
            
        }
        
        printf("\n");
        
        return 0;

}
```

10. Crie um Makefile para a questão anterior.


```
$ cat > makefile #iniciando escrita do código
```

```
num_caracs: ola_num_caracs_1.o num_caracs.o

        gcc $(CFLAGS) -o num_caracs ola_num_caracs_1.o num_caracs.o
        
ola_num_caracs_1.o: ola_num_caracs_1.c num_caracs.h

        gcc $(CFLAGS) -c ola_num_caracs_1.c
        
num_caracs.o: num_caracs.c num_caracs.h

        gcc $(CFLAGS) -c num_caracs.c
        
clean:

        rm -f *.o num_caracs
   ```
   
11. Re-utilize o objeto criado na questão 8 para criar um código que imprime o total de caracteres nos argumentos de entrada. Por exemplo, considerando que o código criado recebeu o nome de 'ola_num_caracs_2':

```bash
$ ./ola_num_caracs_2 Eu Mesmo
$ Total de caracteres de entrada: 25
```


```
$ cat > ola_num_caracs_2.c #iniciando escrita do código
```

```
#include <stdio.h>

#include <stdlib.h>

#include "num_caracs.h"


int main(int argc, char *argv[]){

        int sum = 0, c = 0;
        
        for (int i = 0; i < argc; ++i)
        {       
        
                c = Num_Caracs(argv[i]);    //pega os caracteres de cada palavra
                
                sum += c;                   //soma os caracteres de todas as palavras
                
        }
        
        printf("Total de caracteres de entrada: %d\n", sum);
        
        return 0;
}
```

12. Crie um Makefile para a questão anterior.

```
$ cat > ola_num_caracs_2.c #iniciando escrita do código

```

```
num_caracs: ola_num_caracs_2.o num_caracs.o

        gcc $(CFLAGS) -o num_caracs ola_num_caracs_2.o num_caracs.o
        
ola_num_caracs_2.o: ola_num_caracs_2.c num_caracs.h

        gcc $(CFLAGS) -c ola_num_caracs_2.c
        
num_caracs.o: num_caracs.c num_caracs.h

        gcc $(CFLAGS) -c num_caracs.c
        
clean:

        rm -f *.o num_caracs
```
