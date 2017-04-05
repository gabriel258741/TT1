# TT1
trabalho
#!/bin/bash
clear
exercicio1(){
# Autor: Leonardo Souza Alves
clear
echo "Digite um numero"
read MENO
echo "Digite outro numero"
read MAIO

if (( $MENO > $MAIO )); then
	XXX=$MAIO
	MAIO=$MENO
	MENO=$XXX
fi

while (( $MENO <= $MAIO )); do
	if (( $MENO%2 != 0 )); then
		echo "$MENO"
	fi
	let MENO=($MENO+1)
done 
echo "Pressione [enter] para voltar para o menu"
read XXX
}
exercicio2(){
# Autor: Alisson Ferreira Lima
clear
echo "digite quantos numeros voce vai querer:"
read VAR

echo  "digite um numero, por favor"  
read N2
while (( $VAR > 1 )); do
        echo  "digite um numero, por favor:"  
        read N1
        if (( $N1 > $N2 )); then
               N2=$N1
        fi
        let VAR=($VAR-1) 
done
echo "O maior eh $N2"
echo "Pressione [enter] para voltar para o menu"
read XXX

}
exercicio3(){
# Autor: Matheus Henrique dos santos
clear
VAR=0
echo "Digite um salário:"
read SAL
while (( $SAL != 0 )); do
	if (( $SAL <= 500 )); then
		let VAR=($SAL*20/100)
		let SAL=($SAL+$VAR)
		echo "Seu salário é de R$ $SAL"
		echo "Digite um salário:"
		read SAL
	else
		let VAR=($SAL*10/100)
		let SAL=($SAL+$VAR)
		echo "Seu salário é de R$ $SAL"
		echo "Digite um salário:"
		read SAL
	fi
done
echo "Pressione [enter] para voltar para o menu"
read XXX
}
exercicio4(){
# Gabriel Silva Fernandes
clear
QNT=1
echo "Digite um numero:"
read DIG
VAR=$DIG
while (( $DIG != 0 )); do
	echo "Digite um número:"
	read DIG
	if (( $DIG != 0 )); then
		if (( $DIG <= $VAR )); then
			if (( $DIG < $VAR )); then
				VAR=$DIG
				QNT=1
			else
				let QNT=($QNT+1)	
			fi
		fi
	fi
done
echo "O menor valor digitado é $VAR, e foi escolhido $QNT vez(es)."
echo "Pressione [enter] para voltar para o menu"
read XXX
}
exercicio5(){
# Autor: Matheus do Nascimento Rocha e Daniele Campos
clear
MAIOR=0; MEDIO=0; MENOR=0
echo "Digite um Salário"
read SALARIO
while (( $SALARIO != 0 )); do
	(( $SALARIO == $MAIOR )) && let SALARIO=($MENOR-1)
	(( $SALARIO == $MEDIO )) && let SALARIO=($MENOR-1)
	if (( $SALARIO > $MAIOR )); then
		MENOR=$MEDIO
		MEDIO=$MAIOR
		MAIOR=$SALARIO
	else
	   	if (( $SALARIO > $MEDIO )); then
			MENOR=$MEDIO
			MEDIO=$SALARIO
		else
			(( $SALARIO > $MENOR )) && MENOR=$SALARIO
		fi
	fi
	echo "Digite outro Salário"
	read SALARIO
done
echo "Os Maiores número foram: $MAIOR, $MEDIO e $MENOR."
echo "Pressione [enter] para voltar para o menu"
read XXX
sair(){
clear
echo "pressione [enter] para sair"
read SAIR
}
ESC=0
while (( $ESC != 6 )); do
	clear
	echo "Escolha o exercicio:"
	echo "1) Exercicio 1"
	echo "2) Exercicio 2"
	echo "3) Exercicio 3"
	echo "4) Exercicio 4"
	echo "5) Exercicio 5"
	echo "6) Sair" 
	read ESC
	(( $ESC == 6 )) && sair
	(( $ESC == 1 )) && exercicio1
	(( $ESC == 2 )) && exercicio2
	(( $ESC == 3 )) && exercicio3
	(( $ESC == 4 )) && exercicio4 
	(( $ESC == 5 )) && exercicio5
done
