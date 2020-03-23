Para todas as questões, compile-as com o gcc e execute-as via terminal.

### 1. Crie um "Olá mundo!" em C.

```C
#include <stdio.h>
#include <stdlib.h>
int main() {
  printf("Ola mundo!\n");
  return 0;
}
```

### 2. Crie um código em C que pergunta ao usuário o seu nome, e imprime no terminal "Ola " e o nome do usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_1':

```bash
$ ./ola_usuario_1
$ Digite o seu nome: Eu
$ Ola Eu
```
**Resposta:**
```C
#include <stdio.h>
#include <stdlib.h>
int main() {
  char nome[200];
  printf("Digite o seu nome:\n");
  scanf("%s",nome);
  printf("Ola %s!\n",nome);
  return 0;
}
```
### 3. Apresente os comportamentos do código anterior nos seguintes casos:

##### (a) Se o usuário insere mais de um nome.
```bash
$ ./ola_usuario_1
$ Digite o seu nome: Eu Mesmo
```
**Resposta:**  saida: Ola Eu

##### (b) Se o usuário insere mais de um nome entre aspas duplas. Por exemplo:
```bash
$ ./ola_usuario_1
$ Digite o seu nome: "Eu Mesmo"
```
**Resposta:**  saida: Ola "Eu

##### (c) Se é usado um pipe. Por exemplo:
```bash
$ echo Eu | ./ola_usuario_1
```
**Resposta:**  
```bash
$ Digite o seu nome:
$ Ola, Eu!
```
##### (d) Se é usado um pipe com mais de um nome. Por exemplo:
```bash
$ echo Eu Mesmo | ./ola_usuario_1
```
**Resposta:**  
```bash
$ Digite o seu nome:
$ Ola, Eu!
```

##### (e) Se é usado um pipe com mais de um nome entre aspas duplas. Por exemplo:
```bash
$ echo "Eu Mesmo" | ./ola_usuario_1
```
**Resposta:**  
```bash
$ Digite o seu nome:
$ Ola, "Eu!
```

##### (f) Se é usado o redirecionamento de arquivo. Por exemplo:
```bash
$ echo Ola mundo cruel! > ola.txt
$ ./ola_usuario_1 < ola.txt
```
**Resposta:** 
```bash
$ Digite o seu nome:
$ Ola, Ola!
```
### 4. Crie um código em C que recebe o nome do usuário como um argumento de entrada (usando as variáveis argc e *argv[]), e imprime no terminal "Ola " e o nome do usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_2':

```bash
$ ./ola_usuario_2 Eu
$ Ola Eu
```
**Resposta:**
```C
#include <stdio.h>
#include <stdlib.h>
int main(int argc, char **argv){
  int i=1;
  printf("Ola ");
  while (i != argc ) {
    printf("%s ",argv[i]);
    i++;
  }
  printf("\n");
}
```

### 5. Apresente os comportamentos do código anterior nos seguintes casos:

##### (a) Se o usuário insere mais de um nome.
```bash
$ ./ola_usuario_2 Eu Mesmo
```
**Resposta:** 
```bash
$ ./Ola_usuario_2 Eu Mesmo
Ola Eu Mesmo 

```
##### (b) Se o usuário insere mais de um nome entre aspas duplas. Por exemplo:
```bash
$ ./ola_usuario_2 "Eu Mesmo"
```
**Resposta:** 
```bash
$ ./Ola_usuario_2 "Eu Mesmo"
Ola Eu Mesmo 

```
##### (c) Se é usado um pipe. Por exemplo:
```bash
$ echo Eu | ./ola_usuario_2
```
**Resposta:** 
```bash
$ echo Eu | ./Ola_usuario_2
Ola 

```

##### (d) Se é usado um pipe com mais de um nome. Por exemplo:
```bash
$ echo Eu Mesmo | ./ola_usuario_2
```
**Resposta:** 
```bash
$ echo Eu Mesmo | ./Ola_usuario_2
Ola 

```

##### (e) Se é usado um pipe com mais de um nome entre aspas duplas. Por exemplo:
```bash
$ echo "Eu Mesmo" | ./ola_usuario_2
```
**Resposta:** 
```bash
$ echo "Eu Mesmo" | ./Ola_usuario_2
Ola 

```
##### (f) Se é usado o redirecionamento de arquivo. Por exemplo:
```bash
$ echo Ola mundo cruel! > ola.txt
$ ./ola_usuario_2 < ola.txt
```
**Resposta:** 
```bash
$ ./Ola_usuario_2 < ola.txt
Ola 

```
### 6. Crie um código em C que faz o mesmo que o código da questão 4, e em seguida imprime no terminal quantos valores de entrada foram fornecidos pelo usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_3':

```bash
$ ./ola_usuario_3 Eu
$ Ola Eu
$ Numero de entradas = 2
```
**Resposta:**
```C
#include <stdio.h>
#include <stdlib.h>
int main(int argc, char **argv){
  int i=1;
  printf("Ola ");
  while (i != argc ) {
    printf("%s ",argv[i]);
    i++;
  }
  printf("\n");
  printf("Numero de entradas = %d\n",argc);
  return 0;
}
```

### 7. Crie um código em C que imprime todos os argumentos de entrada fornecidos pelo usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_argumentos':

```bash
$ ./ola_argumentos Eu Mesmo e Minha Pessoa
$ Argumentos: Eu Mesmo e Minha Pessoa
```

**Resposta:**
```C
#include <stdio.h>
#include <stdlib.h>
int main(int argc, char **argv){
  int i=1;
  printf("Argumentos: ");
  while (i != argc ) {
    printf("%s ",argv[i]);
    i++;
  }
  printf("\n");
}
```
### 8. Crie uma função que retorna a quantidade de caracteres em uma string, usando o seguinte protótipo:
`int Num_Caracs(char *string);` Salve-a em um arquivo separado chamado 'num_caracs.c'. Salve o protótipo em um arquivo chamado 'num_caracs.h'. Compile 'num_caracs.c' para gerar o objeto 'num_caracs.o'.

**Resposta:**
```C
//num_caracs.c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include "num_caracs.h"

int num_caracs(char *string)
{
  return stlen(string);
}
}
//num_caracs.h
int num_caracs(char *string);
```
### 9. Re-utilize o objeto criado na questão 8 para criar um código que imprime cada argumento de entrada e a quantidade de caracteres de cada um desses argumentos. Por exemplo, considerando que o código criado recebeu o nome de 'ola_num_caracs_1':

```bash
$ ./ola_num_caracs_1 Eu Mesmo
$ Argumento: ./ola_num_caracs_1 / Numero de caracteres: 18
$ Argumento: Eu / Numero de caracteres: 2
$ Argumento: Mesmo / Numero de caracteres: 5
```
**Resposta:**
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include "num_caracs.h"

int main(int argc, char **argv)
{
	int i=0;
	int numC;
  while (i != argc ) {
    printf("Argumento: %s",argv[i]);
    numC = num_caracs(argv[i]);
    printf(" | Numero de caracteres: %d\n", numC);
    i++;
  }
  printf("\n");
	return 0;
}
```
### 10. Crie um Makefile para a questão anterior.

**Resposta:**
```script
num_caracs_1: main.o num_caracs.o
	gcc $(CFLAGS) -o ola_num_caracs_1 main.o num_caracs.o
main.o: main.c num_caracs.h
	gcc $(CFLAGS) -c main.c
num_caracs.o: num_caracs.c num_caracs.h
	gcc $(CFLAGS) -c num_caracs.c
clean:
	rm -f *.o num_caracs
```

### 11. Re-utilize o objeto criado na questão 8 para criar um código que imprime o total de caracteres nos argumentos de entrada. Por exemplo, considerando que o código criado recebeu o nome de 'ola_num_caracs_2':

```bash
$ ./ola_num_caracs_2 Eu Mesmo
$ Total de caracteres de entrada: 25
```
**Resposta:**
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include "num_caracs.h"

int main(int argc, char **argv)
{
	int i=0;
	int numC = 0;
  while (i != argc ) {
    numC = numC + num_caracs(argv[i]);
    i++;
  }
  printf("Total de caracteres de entrada: %d\n",numC);
	return 0;
}

```
### 12. Crie um Makefile para a questão anterior.
**Resposta:**
```script
num_caracs_1: main.o num_caracs.o
	gcc $(CFLAGS) -o ola_num_caracs_2 main.o num_caracs.o
main.o: main.c num_caracs.h
	gcc $(CFLAGS) -c main.c
num_caracs.o: num_caracs.c num_caracs.h
	gcc $(CFLAGS) -c num_caracs.c
clean:
	rm -f *.o num_caracs

```
