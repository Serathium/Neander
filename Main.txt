;VARIAVEIS
;Funcionalidade esperada: Definir o endereço de memória das variáveis.

NUM EQU 128         ;Define o endereço de memória da variável NUM como 128.
COMPNUM EQU 129         ;Define o endereço de memória da variável COMPNUM como 129.
QUANTNUM EQU 131    ;Define o endereço de memória da variável QUANTNUM como 131.
QUANTIMP EQU 133        ;Define o endereço de memória da variável QUANTIMP como 133.

;PROGRAMA
;Funcionalidade esperada: Armazenar os valores em seus respectivos endereços.

ORG 0                ;Indica ao montador o início do programa.

IN 0                ;Carrega o valor informado no “teclado” no AC.
STA NUM            ;Armazena o valor informado no endereço 128 (NUM).
NOT                ;Nega os bits do valor informado.
STA COMPNUM             ;Armazena o valor negado no endereço 129 (COMPNUM).
LDI 1                ;Carrega o valor 1 no AC.
ADD COMPNUM        ;Soma o valor do endereço 129 (COMPNUM) ao AC.
STA COMPNUM        ;Armazena o valor do AC no endereço 129 (COMPNUM).

LDI 0                ;Carrega o valor 0 no AC.
STA QUANTIMP         ;Armazena o valor do AC no endereço 133 (QUANTIMP).
STA QUANTNUM         ;Armazena o valor do AC no endereço 131 (QUANTNUM).

LOOP:                ;Início do loop.
;Funcionalidade esperada: Loop que incrementa em 1 o valor em QUANTIMP quando QUANTNUM for ímpar. Saltar para a seção FIM se a soma de ; ;QUANTNUM e COMPNUM resultar em 0.

LDI 1                 ;Carrega o valor 1 no AC.
ADD QUANTNUM         ;Soma o valor do endereço 131 (QUANTNUM) ao AC.
STA QUANTNUM         ;Armazena o valor do AC no endereço 131 (QUANTNUM).

LDA QUANTNUM         ;Carrega o valor do endereço 131 (QUANTNUM) no AC.
ADD COMPNUM          ;Soma o valor do endereço 129 (COMPNUM) ao AC.
JZ FIM                 ;Se o resultado da soma for 0, salta para a seção FIM.

;Se o resultado não for 0, segue para a instrução seguinte.

LDI 1                 ;Carrega o valor 1 no AC.
ADD QUANTNUM         ;Soma o valor do endereço 131 (QUANTNUM) ao AC.
STA QUANTNUM         ;Armazena o valor do AC no endereço 131 (QUANTNUM).
LDI 1                 ;Carrega o valor 1 no AC.
ADD QUANTIMP         ;Soma o valor do endereço 133 (QUANTIMP) ao AC.
STA QUANTIMP         ;Armazena o valor do AC no endereço 133 (QUANTIMP).

LDA QUANTNUM         ;Carrega o valor do endereço 131 (QUANTNUM) no AC.
ADD COMPNUM          ;Soma o valor do endereço 129 (COMPNUM) ao AC.
JZ FIM                 ;Se o resultado da soma for 0, salta para a seção FIM.

                 ;Se o resultado não for 0, segue para a instrução seguinte.

JMP LOOP            ;Salta para a seção LOOP.

FIM:                 ;Seção FIM que leva ao encerramento do programa.
;Funcionalidade esperada: Exibir no visor a quantidade de números ímpares entre 0 e NUM e encerrar o programa.
LDA QUANTIMP        ;Carrega o valor do endereço 133 (QUANTIMP) no AC.
OUT 0                ;Exibe no visor o valor do endereço 133 (QUANTIMP).
HLT                 ;Termina o programa.
