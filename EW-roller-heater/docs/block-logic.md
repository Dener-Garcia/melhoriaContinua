## Call block OB01 NW5 

	UC FC 500
	
## FUNCTION BLOCK FC500

> Network 1 - Compara se vel. máquina é maior que 60
	
	MW 500
	L 60
	> =I
	= M 510.0

> Network 2 - Toff para segurar saida por 5s
	
	A M 510.0
	L S5T#5s
	A T 500
	= M 510.1
	
> Network 3 - Ativa e desativa valvula
	
	O M 510.0
	O M 510.1
	= Q 12.6
	
	AN M 510.1
	R T 500	 
