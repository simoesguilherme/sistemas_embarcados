Para todas as questões, escreva os comandos correspondentes no terminal.

#### 1. Escreva o texto "Ola mundo cruel!" em um arquivo denominado "Ola_mundo.txt". Apresente o conteúdo deste arquivo no terminal.
``` bash
echo Ola mundo cruel > Ola_mundo.txt
```
#### 2. Apresente o nome de todos os arquivos e pastas na pasta 'root'.
``` bash
ls /
```

#### 3. Apresente o tipo de todos os arquivos e pastas na pasta 'root'.
``` bash
ls -la /
```
#### 4. Apresente somente as pastas dentro da pasta 'root'.
``` bash
 cd / [TAB]
```

#### 5. Descubra em que dia da semana caiu o seu aniversário nos últimos dez anos.
``` bash
cal 03 2009 | grep 27
cal 03 2010 | grep 27
cal 03 2011 | grep 27
cal 03 2012 | grep 27
cal 03 2013 | grep 27
cal 03 2014 | grep 27
cal 03 2015 | grep 27
cal 03 2016 | grep 27
cal 03 2017 | grep 27
cal 03 2018 | grep 27
cal 03 2019 | grep 27
```

Para as questões a seguir, use a pasta no endereço https://github.com/DiogoCaetanoGarcia/Sistemas_Embarcados/raw/master/Questoes/02_Intro_Linux_arqs.zip

#### 6. Liste somente os arquivos com extensão .txt.
``` bash
ls *.txt
```

#### 7. Liste somente os arquivos com extensão .png.
``` bash
ls *.pnng
```

#### 8. Liste somente os arquivos com extensão .jpg.
``` bash
ls *.jpg
```

#### 9. Liste somente os arquivos com extensão .gif.
``` bash
ls *.gif
```

#### 10. Liste somente os arquivos que contenham o nome 'cal'.
``` bash
ls *cal*
```

#### 11. Liste somente os arquivos que contenham o nome 'tux'.
``` bash
ls *tux*
```

#### 12. Liste somente os arquivos que comecem com o nome 'tux'.
``` bash
ls tux*
```
