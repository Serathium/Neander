O enunciado do problema é este:
O programa a ser desenvolvido deve ler um valor do teclado e apresentar, como saída no
visor, a quantidade de números ímpares existentes entre 0 e o número informado.
Observação: Sempre será informado no teclado um valor positivo e maior do que 10 .
Ou seja, se o número informado for 15, o valor que deve aparecer no visor é 7, pois os
números ímpares entre 0 e 15 são 1, 3 ,5, 7, 9, 11 e 13, totalizando 7 números ímpares.
Note que, neste caso, não incluo o número 15, pois foi pedido a quantidade entre 0 e o
número informado no teclado, sem contabilizar o próprio número informado.
Com isso em mente, a estratégia adotada para a criação deste algoritmo foi dividi-lo em
duas seções: FIM e LOOP. LOOP é um loop dividido em duas partes imaginárias.
Na primeira parte do LOOP, incrementa em 1 o valor armazenado no endereço que
representa o contador (chamei essa variável de QUANTNUM, inicializada com o valor 0) e
incrementa em 1 o valor armazenado no endereço que representa a quantidade de números
ímpares (chamei essa variável de QUANTIMP, inicializada com o valor 0). Caso
QUANTNUM seja igual ao número informado no teclado (variável NUM), o programa pula
para a seção FIM, que apresenta no visor o valor da variável QUANTIMP e encerra o
programa. Caso não seja igual, o programa segue para a próxima parte do LOOP.
Na segunda parte do LOOP, incrementa em 1 o QUANTNUM, sem incrementar o
QUANTIMP. Caso QUANTNUM seja igual ao número informado no teclado (variável NUM),
o programa pula para a seção FIM, que apresenta no visor o valor da variável QUANTIMP e
encerra o programa. Caso não seja igual, o programa pula para o início do LOOP.
Em outros termos, ao inicializar QUANTNUM com o valor 0 e incrementar em 1 na primeira
parte do LOOP, sei que o valor de QUANTNUM agora é 1, um número ímpar, logo
incremento QUANTIMP em 1. Na segunda parte do LOOP, o valor de QUANTNUM se torna
2, logo não incremento 1 em QUANTIMP pois 2 é par.
Para realizar a comparação entre QUANTNUM e NUM, criei a variável COMPNUM, sendo o
complemento de 2 do valor da variável NUM. Se a soma de QUANTNUM e COMPNUM
resultar em 0, sabemos que o valor de QUANTNUM é igual ao de NUM, portanto o
programa deve ser encerrado, pulando para a seção FIM.
