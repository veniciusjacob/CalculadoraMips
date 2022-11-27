.data
	message1: .asciiz "\nEscolha a operação desejada: \n 1 - Adição\n 2 - Subtração\n 3 - Multiplicação\n 4 - Divisão\n 5 - Potenciação\n 6 - Raiz Quadrada\n 7 - Tabuada\n 8 - Cancelar\n"
	esperaUsuario: .asciiz "Digite sua escolha: "
	n1: .asciiz "Digite o primeiro número: "
	n2: .asciiz "Digite o segundo número: "
	base: .asciiz "Digite a base: "
	expoente: .asciiz "Digite o expoente: "
	raiz: .asciiz "Digite um valor para raiz quadrada: "
	valor_tabuada: .asciiz "Digite o número para ver sua tabuada: "
	pular: .asciiz "\n"
	sinalMult: .asciiz  "x"
	sinalIgual: .asciiz " = " 
	mQuit: .asciiz "Programa Finalizado com sucesso."
	rSoma: .asciiz "\nO resultado da soma é: "
	rSubtracao: .asciiz "\nO resultado da subtração é: "
	rMultiplicacao: .asciiz "\nO resultado da multiplicação é: "
	rDivisao: .asciiz "\nA parte inteira da divisão é: "
	rPotencia: .asciiz "\nO valor de x^y é: "
	rRaiz: .asciiz "\nRaiz Quadrada: "
.text	
	loop: #rotulo do jump para recomeçar novamente o programa
	
	# Escolha da operação desejada: 

	la $a0, message1 #movimenta o dado da memória para o registrado $a0 e passa como argumento na funcão para imprimir
	jal imprimeString #chamada da função para imprimir string
	
	#Espera escolha do usuario
	
	la $a0, esperaUsuario #movimenta o dado da memória para o registrado $a0 e passa como argumento na funcão para imprimir
	jal imprimeString #chamada da função para imprimir string
		
	#ler escolha do usuário:
	
	jal lerInteiro #chamada da função lerInteiro
	move $t1, $v0 #move o valor do registrador $v0 para $t1
	
	ble $t1, 4, input_op_basicas #se o valor em $t1 for menor ou igual a 4, então execute input_op_basicas
	
	return: 
	
	#execução da escolha do usuario:
	
	beq $t1, 1, soma #caso 1: soma
	beq $t1, 2, subtracao #caso 2: subtração
	beq $t1, 3, multiplicacao #caso 3: multiplicação
	beq $t1, 4, divisao #caso 4: divisão
	beq $t1, 5, potencia #caso 5: potencia
	beq $t1, 6, sqrt #caso 6: raiz quadrada
	beq $t1, 7, tabuada #caso 7: tabuada
	beq $t1, 8, quit #caso 8: cancelar
	
	li $v0, 10 #encerra programa
	syscall #faça	
#-----------------------------------------------------------------------------------------------------------------------------------
    	#RÓTULOS DAS CONDIÇÕES:
    	
   	input_op_basicas:
   		la $a0, n1 #movimenta o dado da memória para o registrado $a0
   		jal imprimeString #chamada da função imprimeString
   		jal lerInteiro #chamada da função lerInteiro
   		
   		move $s0, $v0 #salva o valor lido no registrador $s0
   		
   		la $a0, n2 #movimenta o dado  de n2 na memória para o registrado $a0
   		jal imprimeString #chamada da função imprimeString
   		jal lerInteiro #chamada da função lerInteiro
   		
   		move $s1, $v0 #salva o valor lido no registrador $s1
   		
   		j return #retorna para a parte do rotulo passado na linha 40
   		
   	soma:
   		la $a0, rSoma #movimenta o dado de rSoma na memória para o registrado $a0
   		jal imprimeString # hamada da função imprimeString
   		
   		add $a0, $s0, $s1 #adição dos valores passados pelo usuario, o resultado é salvo em $a0
   		
   		jal imprimeInteiro #chamada da função imprimeInteiro
   		
   		la $a0, pular #pular uma linha após o resultado
   		jal imprimeString
   		
   		j loop #recomeça o programa na linha 21
   		
   	subtracao:
   		la $a0, rSubtracao #movimenta o dado de rSubtracao na memória para o registrado $a0
   		jal imprimeString # chamada da função imprimeString
   		
   		sub  $a0, $s0, $s1 #adição dos valores passados pelo usuario, o resultado é salvo em $a0
   		jal imprimeInteiro #chamada da função imprimeInteiro
   		
   		la $a0, pular #pular uma linha após o resultado
   		jal imprimeString
   		
   		j loop #recomeça o programa na linha 21
   
   	multiplicacao:
   		la $a0, rMultiplicacao #movimenta o dado de rSubtracao na memória para o registrado $a0
   		jal imprimeString #chamada da função imprimeString
   		
   		mul $a0, $s0, $s1 #multiplica $s0 por $s1
   		jal imprimeInteiro #chamada da função imprimeInteiro
   		
   		la $a0, pular #pular uma linha após o resultado
   		jal imprimeString
   		
   		j loop #recomeça o programa na linha 21
   		
   	divisao:
   		la $a0, rDivisao #movimenta o dado de rSubtracao na memória para o registrado $a0
   		jal imprimeString #chamada da função imprimeString
   		
   		div $s0, $s1   	#divide $s0 por $s1
   		
   		mflo $a0 #move de lo para $a0
   	
   		jal imprimeInteiro #chamada da função imprimeInteiro
   		
   		la $a0, pular #pular uma linha após o resultado
   		jal imprimeString
   		
   		j loop #recomeça o programa na linha 21
   		
   	potencia:
   		la $a0, base #movimenta o dado de base na memória para o registrado $a0
   		jal imprimeString #chamada da função imprimeString
   		 
   		jal lerInteiro #chamada da função lerInteiros
   		
   		move $s0, $v0 #salva a base em $s0
   		
   		la $a0, expoente #movimenta o dado de expoente na memória para o registrado $a0
   		jal imprimeString #chamada da função imprimeString
   		
   		jal lerInteiro #chamada da função lerInteiros
   		
   		move $a0, $s0 #salva em $a0 o valor lido da base e passa como argumento
   		move $a1, $v0 #salva o expoente lido em $a1 e passa como argumento
   		
   		# argumentos passados:
   		# $a0 = base
   		# $a1 = expoente
   		
   		jal potenciacao #chamada função potenciacao
   		
   		# retorno em $v0
   		
   		move $s0, $v0 #salva o valor retornado em $s0
   		
   		la $a0, rPotencia #movimenta o dado de rPotencia na memória para o registrado $a0
   		jal imprimeString  #chamada da função imprimeString
   				
   		move $a0, $s0	#move para $a0, o valor do retorno para imprimir	
   		jal imprimeInteiro #chamada da função imprimeInteiro
   		
   		la $a0, pular #pular uma linha após o resultado
   		jal imprimeString
   			
   		j loop #recomeça o programa na linha 21
   	
   	sqrt:
   		la $a0, raiz #movimenta o dado de raiz na memória para o registrado $a0
   		jal imprimeString #chamada função imprimeString
   		
   		li $v0, 6 #Ler um float
   		syscall #faça
   		
   		la $a0, rRaiz #movimenta o dado de Rraiz na memória para o registrado $a0
   		jal imprimeString #chamada função imprimeString
   		
   		sqrt.s $f12, $f0 #faz a raiz quadrade de $f0 e coloca em $f12
   	
   		li $v0, 2 #imprime um float
   		syscall #faça
   		
   		la $a0, pular #pular uma linha após o resultado
   		jal imprimeString
   		
   		j loop #recomeça o programa na linha 21
   		
   	tabuada:
   		la $a0,valor_tabuada  #movimenta o dado de valor_tabuada na memória para o registrado $a0
   		
   		jal imprimeString #chamada da função imprimeString
   		
   		jal lerInteiro #ler o valor que será feito a tabuada
   		
   		move $t0, $v0 #salva o valor lido em $t0
   	
   		move $t1, $zero # t1 = 0 (inicio do loop)
   		
   		while:
   			beq $t1, 11, exit #se o valor em $t1 for igual a 11, então execute exit
   			
   			move $a0, $t0 #passa o valor lido em $t0 para $a0 em cada interação
   			
   			jal imprimeInteiro #imprime o valor lido
   			
   			la $a0, sinalMult #imprime o sinal de multiplicação
   			jal imprimeString #chamada da função imprimeString
   			
   			move $a0, $t1 #imprime o valor de $t1 em cada interação
   			jal imprimeInteiro #chamada da função imprimeInteiro
   			
   			la $a0, sinalIgual #movimenta o dado de vsinalIgual na memória para o registrado $a0
   			jal imprimeString  #chamada da função imprimeString
   			
   			mul $a0, $t0, $t1 #multiplica o valor lido pelo valor de $t1 em cada interação começando por 0
   			
   			jal imprimeInteiro #imprime a multiplicação que já está em $a0
   			
   			la $a0, pular #pula linha
   			jal imprimeString #imprime \n
   			
   			addi $t1, $t1, 1 # t1 = t1 + 1
   			j while #volta para o loop while
   		
   		exit:
   			j loop #recomeça o programa na linha 21
   	
   	quit:
   		la $a0, mQuit #movimenta o dado de mQuit na memória para o registrado $a0
   		jal imprimeString #chamada da função imprimeString
   		
   		li $v0, 10 #finaliza o programa
   		syscall #faça
#--------------------------------------------------------------------------------------------------------------------------------	
	#FUNÇÕES DO PROGRAMA
	
	#função para imprimir string
	imprimeString:
		li $v0, 4
		syscall
		jr $ra
	
	#função para imprimir inteiros	
	imprimeInteiro:
		li $v0, 1
		syscall
		jr $ra
		
	#função para ler um número inteiro	
	lerInteiro:
		li $v0, 5
		syscall
		jr $ra	
		
	#função de potenciação
	potenciacao:
		add $t0, $zero, $zero #inicia $t0 = 0 
		move $v0, $zero #zera $v0, uma vez que ele será o retornado com o valor da potencia.
		addi $v0, $v0, 1  #$v0 = 1
	potencia_loop:
		beq $t0, $a1, exit_loop #se o valor de $t0 for igual a $a1, sai do loop
		mul $v0, $v0, $a0 # $v0 = $v0 * $a0
		addi $t0, $t0, 1 #incrementa $t0
		j potencia_loop #retorna para o loop
	exit_loop:
		jr $ra #retorna o valor da potencia pra onde chamou
