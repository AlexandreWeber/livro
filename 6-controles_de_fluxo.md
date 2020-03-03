Assim como em outras linguagens de programação o JavaScript também possui recursos para controle do fluxo de execução do código, ou seja, quando, como e se um determinado trecho de código será executado.

Nesse capítulo iremos ver sobre os seguintes itens:


**IF, IF ELSE** <br/>
**SWITCH** <br/>
**WHILE, DO...WHILE** <br/>
**FOR, FOR IN e FOR OF** <br/>
**BREAK/CONTINUE** <br/>
**LABEL** <br/>

**IF**

Provavelmente o comando mais utilizado, não apenas no JavaScript mas em qualquer linguagem de programação. O IF realiza uma validação lógica e retorna os valores true ou false. Caso o retorna seja true a próxima ou próximas linhas de código serão executadas.

Estrutura do comando:

```
if (condição1)
	...execução1
else if (condição2)
	...execução2
else
	...execução3
```
```
if (condição1) {
	...execução1
	...execução1.1
	...execução1.2
} else if (condição2) {
	...execução2
	...execução2.1
	...execução2.2
} else {
	...execução3
	...execução3.1
	...execução3.2
}
```
Vamos ver alguns exemplos de utilização do IF.

No trecho de código abaixo temos a variável nome e estamos realizando um teste com o **IF**.

```
// O alert será exibido caso nome seja igual a Ariane
if (nome === "Ariane")
	alert("Bem-vinda Ariane");
```

Também é possível utilizar as chaves {} no inicio e fim do comando para indicar que existe mais de uma linha a ser executada após a validação do **IF**.

No trecho de código abaixo temos a variável nome e estamos realizando um teste com o **IF**. 

```
// O alert e a atribuição da variável usuarioCorreto só serão executados caso nome seja igual a "Maria"
if (nome === "Maria") {
	alert("Bem-vinda Maria");
	usuarioCorreto = true;
}
```
Também é possível realizar validações usando operadores lógicos (E, OR, NOT), matemáticos (+, -, /, *) e até mesmo invocar funções dentro do IF.

No trecho de código abaixo temos a variável nome, sobrenome e estamos realizando testes utilizando os operador && (e) e || (ou).

```
// O alert só será exibido caso a variável nome seja igual a "Ariane" ou "Maria" ou "Mariela".
if (nome === "Ariane" || nome === "Maria" || nome === "Mariela") {
	alert("Seja bem-vinda usuária");
}

// O alert será exibidido caso a variável nome seja igual a Alexandre e o sobrenome igual a Weber.
if (nome === "Alexandre" && sobrenome === "Weber") {
	alert("Seja bem-vindo");
}
```
No trecho de código abaixo temos as variáveis valor e imposto e estamos realizando um teste utilizando operadores matemáticos.

```
// O alert será exibidido caso a soma de valor + imposto seja maior que 100.
if (valor + imposto > 100) {
	alert("O valor com imposto é maior que 100");
}

// O alert será exibidido caso a soma de valor - imposto seja igual a 100.
if (valor - imposto === 100) {
	alert("O valor com imposto é maior que 100");
}
```
No trecho de código abaixo estamos invocando a função retornaNome() e realizando um teste com o valor retornado.

```
// O alert será exibidido caso o retorno de retornaNome() seja igual a Alexandre.
if (retornaNome() === "Alexandre") {
	alert("Olá Alexandre");
}
```
ELSE

Caso a validação realizada no IF não retorne TRUE, é possível executar outro trecho de código através do comando ELSE, assim como no IF as chaves {} são necessárias somente quando o trecho possuir mais de uma linha. Vale lembra que o comando ELSE só pode ser utilizado quando houver um IF junto.

No trecho de código abaixo temos a variável nome e estamos realizado um teste que irá retornar FALSE.

```
let nome = "Douglas";

// A validação irá retornar false pois o usuário é Douglas e não Alexandre
// O trecho de código dentro das {} do IF não será executado, mas sim o trecho entre as {} do ELSE
if (nome === "Alexandre") {
	alert("Olá Alexandre");
} else {
	// Esse alert será exibido
	alert("Você não é o Alexandre");
}
```

Combinando IF e ELSE

Também podemos usar os comandos ELSE IF juntos para criarmos múltiplas validações. 
No trecho de código abaixo temos a variável nome e estamos realizados diversos testes combinando o IF, ELSE e ELSE IF.

```
let nome = "Maria";

// Realiza o primeiro teste e retorna false, pois a variável nome é igual a Maria 
if (nome === "Alexandre)  {
	alert("Olá Alexandre");

	// Realiza o segundo teste e retorna false, pois a variável nome é igual a Maria 
} else if (nome === "Ariane") {
	alert("Olá Alexandre");

	// E por fim realiza o terceito teste e retorna true
	// com isso a linha dentro das {} é executada
} else if (nome === "Maria") {
	alert("Olá Alexandre");
}
```

**SWITCH**

O comando IF que vimos anteriormente pode em alguns casos resultar em um código muito extenso e por vezes até mesmo complexo, dependendo da quantidade de verificações que são feitas, muitos IF e ELSE IF aninhados. Uma alternativa para evitar essa situação é o SWITCH. O SWITCH avalia uma condição através da opção CASE e caso a condição do CASE seja true executa o trecho de código

Estrutura do comando:

```
switch (valor) {
	case validação1:
		...trecho a ser executado
		break;
	case validação2:
		...trecho a ser executado
		break;
	case validação3
		...trecho a ser executado
		break;
	default:
		...trecho a ser executado
		break;
}
```
Um ponto importante é que o SWITCH é recomendado quando as condições a serem validadas possuem valores pré-definidos.

Vamos ver alguns exemplos de utilizaçao do SWITCH.

No trecho de código abaixo temos a variável diaDaSemana e estamos realizando um teste com o **SWITCH** combinado com o **CASE**.

```
const diaDaSemana = 3;

// A variável diaDaSemana foi selecionada para executar as validações (case)
switch (diaDaSemana) {
// Em cada um dos case será realizada uma comparação
case 1: // diaDaSemana === 1
	alert("Domingo");
	break;
case 2: // diaDaSemana === 2
	alert("Segunda-feira");
	break;
case 3: // diaDaSemana === 3
	alert("Terça-feira");
	break;
case 4: // diaDaSemana === 4
	alert("Quarta-feira");
	break;
case 5: // diaDaSemana === 5
	alert("Quinta-feira");
	break;
case 6: // diaDaSemana === 6
	alert("Sexta-feira");
	break;
case 7: // diaDaSemana === 7
	alert("Sábado");
	break;
}
```
As comparações realizadas nos case são sempre do tipo estrita, ou seja, o valor deve ser igual tanto no valor quanto no tipo.

Exemplo: 1  === 1 true
        "1" === 1 false

Default

No switch além das comparações utilizando o case também é possível utilizar a opção default. O trecho de código da opção default será executada quando nenhum dos case retorne true.

No trecho de código abaixo foi adicionada a opção default.

```
const diaDaSemana = 8;

// A variável diaDaSemana foi selecionada para executar as validações (case)
switch (diaDaSemana) {
	// Em cada um dos case será realizada uma comparação
	case 1: // diaDaSemana === 1
		alert("Domingo");
		break;
	case 2: // diaDaSemana === 2
		alert("Segunda-feira");
		break;
	case 3: // diaDaSemana === 3
		alert("Terça-feira");
		break;
	case 4: // diaDaSemana === 4
		alert("Quarta-feira");
		break;
	case 5: // diaDaSemana === 5
		alert("Quinta-feira");
		break;
	case 6: // diaDaSemana === 6
		alert("Sexta-feira");
		break;
	case 7: // diaDaSemana === 7
		alert("Sábado");
		break;
	default: // O trecho será executado, pois 8 não é um dia válido
		alert("Dia inválido");
		break;
}
```

Múltiplos case

Caso seja necessário é possível agrupar os cases para que o mesmo trecho de código seja executado para diferentes valores.

No trecho de código abaixo está sendo utilizado múltiplos cases para validar a variável diaDaSemana

```
const diaDaSemana = 1;

// A variável diaDaSemana foi selecionada para executar as validações (case)
switch (diaDaSemana) {
	// Em cada um dos case será realizada uma comparação
 	case 1: // diaDaSemana === 1
 	case 7: // diaDaSemana === 7
  	alert("Fim de semana");
  	break;
 	case 2: // diaDaSemana === 2
 	case 3: // diaDaSemana === 3
 	case 4: // diaDaSemana === 4
 	case 5: // diaDaSemana === 5
 	case 6: // diaDaSemana === 6
  	alert("Dia útil");
  	break;
 	default:
  	alert("Dia inválido");
  	break;
}
```
**WHILE**

O comando while cria um laço de repetição que executa um determinado trecho de código enquanto uma determinada condição testada retornar true. No while a condição é avaliada antes da execução do trecho de código.

Estrutura do comando:

```
	while (...condição de teste) {
		...trecho a ser executado
	}
```

Vamos ver um exemplo de utilização while.

No trecho de código abaixo temos a variável contador iniciada com valor 1, e vamos exibir o valor dessa variável enquanto ele for menor igual a 10 utilizando o **WHILE**

```
let contador = 1;

while(contador <= 10) {
	alert('O número é ' + contador);
	contador++;
}
```

Um ponte importante é a linha em que a variável contador é incrementada, sem isso o while entraria em um laço infinito, visto que contador seria sempre menor igual a 10.

**DO...WHILE**
