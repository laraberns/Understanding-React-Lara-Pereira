![js badge](./assets/js.png)

- [JS - How to declare variables](#declare)
- [JS - Types of data - Strings, Numbers, Boolean, Object...](#data)
- [JS - Arithmetic operators](#operators)
- [JS - Getting Elements from HTML](#gettingelements)
- [JS - Selection Structures (If/Else and Switch/Case)](#selection)
- [JS - Repeating Structures (while, do/while, for)](#repeating)
- [JS - Arrays - Declaring an Array, Array methods (push( ), pop( ), shift( ), unshift( ), lenght)](#arrays)
- [JS - Functions](#functions)
- [JS - Events](#events)
- [JS - Strings Methods](#stringsmethods)
- [JS - CSS with JavaScript](#csswithjs)
- [JS - Creating Elements with .innerHTML and .write](#innerhtml)
- [JS - Creating Elements with .createElement and .appendChild](#createelement)
- [JS - Object - Structure](#objectstructure)
- [JS - Where To Save Script](#jsfiles)
- [JS - Windows Types of Alerts](#alertstypes)
- [JS - Objects](#jsobjects)
- [JS - Arrays Methods](#arraysmethods)
- [JS - Let x Var x Const](#letvarconst)
- [JS - Matrix](#matrix)
- [JS - Console](#console)
- [JS - Short Circuit](#shortcircuit)
- [JS - Async - Timing](#asynctiming)
- [JS - Async - API - Buscar CEP - AJAX](#ajaxcep)
- [JS - Async - API - Buscar CEP - Await](#awaitcep)
- [JS - Sets](#sets)
- [JS - Maps](#maps)
- [JS -  Stack and Queue](#stackqueue)
- [JS -  Linked List](#linkedlist)
- [JS -  Local Storage](#localstorage)
- [JS -  Session Storage](#sessionstorage)
- [JS -  API Coins](#apicoins)
- [JS -  Callback - Basics](#callbasics)
- [JS -  Callback](#callback)
- [JS -  Promisses - Fetch](#promisesfetch)
- [JS -  Promisses](#promisses)
- [JS -  Destructuring](#destructuring)


### JS - How to declare variables <a id="declare"></a>
~~~
    <script>
        //Global scope variables
        variavel = 0 // Prefere not to use
        var variavel1 // Prefere this type of declaring variables for global variables
        let variavel2
        const contantes = 3.14 
        var nome = "Julia"
        var idadeUsario // Give semantic names for the variables - use camelCase
        let idade = 0
            
        idade = idade + 1 


        function pegarNome() {
            let nome  // Local scope variable
            nome = document.getElementById("idNome").value
            idade = Number(document.getElementById("idIdade").value)

            console.log("Nome: " + nome);
            console.log(typeof(idade));

            

            document.getElementById("idOut").value = "Nome: "+ nome + "-  Idade: " + idade

        }

        console.log("Nome 2: " + nome);

    </script>

~~~

### JS - Types of data - Strings, Numbers, Boolean, Object... <a id="data"></a>
~~~
   <script>
        /*
            5 types of data:
            -------------------
            - string     -  'isso é uma string'  "isso é uma String" "123"
            - number     -   123  12.5 
            - boolean    -   true  false 
            - Object 
            - function 

            2 - special types of data
            ------------------------------
            - null 
            - undefined 

            6 - type of objects
            -------------------------
            - Object 
            - Date 
            - Array 
            - Number 
            - String 
            - Boolean 

            operators to test data types
            -------------------------------------
            typeOf
            isNaN (Not a Number)

        */

        var nomeUsuario = true
        console.log(typeof(nomeUsuario));
        console.log(isNaN(nomeUsuario));

        
        /*
          2 - How to convert type of dates
          ------------------------------------------------
          - Implicit:

        */

        console.log(5 + "2"); // convert to string
        console.log(5 + null); //convert to number
        console.log("5" + undefined); //convert to string
        console.log("5" + null); //convert to string
        console.log("5" - 2); //convert to number
        console.log("5" * "2"); //convert to number

        /*
          - Functions for converting
        */

        var variavel
        var x = 345

        variavel = String(x)
        console.log("tipo: " + typeof(variavel) + " " + variavel);
        variavel = String(123)
        console.log("tipo: " + typeof(variavel) + " " + variavel);

        var salBase = 1000.00;
        console.log("salBase 1 " + typeof(salBase));
                 
        salBase = salBase.toString(); 
        console.log("salBase 2 " + typeof(salBase));

        // Working with numbers - functions
        var h = 75.345675467;
        console.log("h.tofixed(2) " + h.toFixed(2));
        console.log("h.toExponencial(3) " + h.toExponential(3));
        console.log("h.toPrecision(5) " + h.toPrecision(5));

        /*
         - converting
         -----------------------
         - String to Number
        */

        //1. Forma 

        var y = "5"
        var j = + y 

        console.log("j " + typeof(j));

       
        console.log("'3.14' to Number " + Number("3.14"))
        console.log("true to Number " + Number(true))
        console.log("false to Number " + Number(false))
        console.log("'89 90' to Number " + Number("89 90")) // NaN
        console.log("espaço to Number " + Number(" "))
        console.log("vazio to number " + Number(""))

        console.log("parseFloat('10.5') " + parseFloat("10.5"));
        console.log("parseFloat('10') " + parseFloat("10"));

        console.log("parseInt('10.5') " + parseInt("10.5"));
        console.log("parseInt('10') " + parseInt("10"));

        /*
          convert Number to Boolean 
        */
        var teste = 1
        if (teste == true) {
          console.log(typeof(teste));
          console.log("Entrou True");
        } else {
          console.log("Entrou false");
        }



    </script>

~~~

### JS - Arithmetic operators <a id="operators"></a>
~~~
   <script>

        var num1 = 3 //document.getElementbyId("algumID").value
        var num2 = 2
        var resultado

        //----- Sum 
        const resulConst = num1 + num2
        console.log("resulConst " + resulConst);
       
        //----- Sum (increment)
        num1 += num2
        console.log("Adição 2: " + num1);

        //----- Subtraction
        resultado = num1 - num2
        console.log("Subtração: " + resultado);

        //----- Subtraction (increment)
        num1 -= num2
        console.log("Subtração 2: " + num1);

        //----- Multiplication
        resultado = num1 * num2
        console.log("Multiplicação: " + resultado);

        //----- Multiplication (increment)
        num1 *= num2
        console.log("Multiplicação 2: " + num1);

        //----- Division  
        resultado = num1 / num2
        console.log("Divisão: " + resultado);

        Division (increment)
        num1 /= num2
        console.log("Divisão 2: " + num1);

        //---- Module 
        resultado = num1 % num2
        console.log("Resto: " + resultado);

        //---- Module (increment)
        num1 %= num2;
        console.log("Resto 2: " + num1);

        //---- Potentiation
        resultado = num1 ** num2
        console.log("Potenciação: " + resultado);

        //---- Potentiation (increment)
        num1 **= num2
        console.log("Potenciação 2: " + num1);

        //---- Increment  +1
        resultado = num1++  // num1 = num1 + 1

        //---- Decrement  -1
        resultado = num1--

        //---- Increment  +1
        resultado = ++num1  // num1 = num1 + 1

        //---- Decrement  -1
        resultado = --num1

        //Radiciation
        num1 = 25
        var raiz = 3

        resultado = num1 ** (1 / raiz)
        console.log("Raiz 'n'esima: " + resultado)

        //-------- Percentage
        /*
          100%  -  640
          10%      x 
          100x = 6400
          x = (640 * percentual)/100


          640 * percentual/100 = x 
          640 * 0.1 = x 

        */

        //Math operators
        var pi = Math.PI; 
        console.log("PI " + pi);

        resultado = Math.pow(5, 6); 
        console.log("Math.pow " + resultado);

        resultado = Math.sqrt(25); 
        console.log("Math.sqrt " + resultado); 

        resultado = Math.cbrt(27);
        console.log("Math.cbrt " + resultado);

        //Generating Pseudo-Random numbers between 0 and 10
        var numRand = parseInt(Math.random() * 10);
        console.log("Num Randomico " + numRand);

    </script>

~~~

### JS - Getting Elements from HTML <a id="gettingelements"></a>
~~~
    <script>
        var texto
        var texto2
        var texto3
        var numero 
        var data
        var senha
        var op1
        var op2 
        var op3
        var feminino
        var masculino
        var estado
        var uf
        var itemSelected
        var pergunta
        var navegador


        function capturaTela() {
            //Example 001 - Text box
            texto = document.getElementById("idTexto").value
            console.log("Texto: " + texto);

            
                //#id  
                texto2 = document.querySelector("#idTexto").value
                console.log("Texto2: " + texto2);

                //.class 
                texto3 = document.querySelectorAll(".inputTexto")
                console.log(texto3);

           
            //Example 002 - Text box - Number 
            numero = Number(document.getElementById("idNumero").value)
            console.log("Numero: " + numero)

            //Example 003 - Text box - Data 
            data = document.getElementById("idData").value
            console.log("Data: " + data)

            //Example 004 - Text box - Password
            senha = document.getElementById("idSenha").value
            console.log("Senha: " + senha)

            //Example 005 - Checkbox
            isOp1 = document.getElementById("idOpcao1").checked
            isOp2 = document.getElementById("idOpcao2").checked
            isOp3 = document.getElementById("idOpcao3").checked
            console.log("Op1: " + op1 + " Op2: " + op2 + " Op3: " + op3);

            //Example 006 - Radio button
            feminino = document.getElementById("idFeminino").checked
            masculino = document.getElementById("idMasculino").checked
            console.log("Masculino: " + masculino + " Feminino: " + feminino);


                //Verifyng which radio button is selected... 
                var sexo = document.querySelector("input[name=nmGenero]:checked").value
                console.log("Example Radio 2: " + sexo);


            //Example 007 - Select
            itemSelected = document.getElementById("idSelect")
            uf = itemSelected.value
            console.log("UF: " + uf);

                //Getting innerText of selected element
                console.log("Estado: " + itemSelected.options[itemSelected.selectedIndex].innerText);

            //Example 008 - Data List
            navegador = document.getElementById("idNavegadores").value
            console.log("Navegador: " + navegador);

            //Example 009 - Textarea
            pergunta = document.getElementById("idTextArea").value
            console.log("Pergunta: " +  pergunta);
            
        }
    </script>

~~~

### JS - Selection Structures (If/Else and Switch/Case) <a id="selection"></a>
~~~
   <script>

        function exemplosEstruturasSelecao() {

            //Simple selection structure
            var idade = 18
            if (idade > 18) {
                console.log("é maior de idade");
            }

            //Composite Selection Structure  && -> AND  || -> OR   ! -> NOT
            var num = 25
            if (num < 10 || (num > 23 && num < 50)) {
                console.log("o numero é menor que 10 ou está no intervalo entre 23 e 50");
            }

            //Chained selection structure
            var menu = 3//document.getElementById("idMenu").value
            if (menu == 0) {
                console.log("Opcao 0 selecionada");
            } else {
                if (menu == 1) {
                    console.log("Opcao 1 selecionada");
                } else {
                    if (menu == 2) {
                        console.log("Opcao 2 selecionada");
                    } else {
                        if (menu == 3) {
                            console.log("Opcao 3 selecionada");
                        } else {
                            console.log("Opção Inválida")
                        }
                    }
                }
            }

            //Chained selection structure with IF-ELSE-IF
            if (menu == 0) {
                console.log("Opcao 0 selecionada");
            } else if (menu == 1) {
                console.log("Opcao 1 selecionada");
            } else if (menu == 2) {
                console.log("Opcao 2 selecionada");
            } else if (menu == 3) {
                console.log("Opcao 3 selecionada");
            } else {
                console.log("Opção Inválida")
            }
    
            //switch-case {
            switch (menu) {
                case 0:
                    console.log(" - Opcao 0 selecionada");
                    break;
            
                case 1:
                    console.log(" - Opcao 1 selecionada");
                    break;

                case 2:
                    console.log(" - Opcao 2 selecionada");
                    break;

                case 3:
                    console.log(" - Opcao 3 selecionada");
                    break;

                default:
                    console.log(" - Opção Inválida");
                    break;
            }

            //Ternary
            var opcao = (menu == 0)? "ternario falso" : "ternario falso"
            console.log(opcao);

        }

        // EXAMPLE -->
        function testarGenero() {
            let masculino = document.getElementById("idMasc").checked
            let feminino = document.getElementById("idFem").checked
            let lgbt = document.getElementById("idNaoBinario").checked

            //IF
            if (masculino == true) {
                console.log("o genero masculino está selecionado");
            }

            if (feminino == true) {
                console.log("o genero feminino está selecionado");
            }

            if (lgbt == true) {
                console.log("o genero nao binário está selecionado");
            }

            //IF / ELSE
            if (masculino == true) {
                console.log("o genero masculino está selecionado");
            } else {
                if (feminino == true) {
                    console.log("o genero feminino está selecionado");
                } else {
                    console.log("o genero nao binário está selecionado");
                }
            }

            //IF / ELSE IF
            if (masculino == true) {
                console.log("o genero masculino está selecionado");
            } else if (feminino == true) {
                console.log("o genero feminino está selecionado");
            } else {
                console.log("o genero nao binário está selecionado");
            }

        }

    </script>
~~~

### JS - Repeating Structures (while, do/while, for) <a id="repeating"></a>
~~~
    <script>

        var contador = 10 

        //while  - we use when we don´t know how many times
     
        while (contador < 10) {
            contador++
            console.log("while " + contador);
        }


        //do while - need one loop at least
        
        contador = 0 

        do { //iteração = 1 passada dentro da estrura 
            contador++
            console.log("do-while " + contador);
        } while (contador < 10);


        //for - we use when we know how many times

        for (let i = 0; i> 10; i++) {
            console.log("For: " + i);
        }

        var vetor = ["item1", "item2", "item3", "item4", "item5"]

        var pessoa = {
            nome : "Joao", 
            sobrenome : "Silva", 
            idade : 25, 
            sexo : "m"
        }

        //forEach Array 
        vetor.forEach((element, index, array) => {
            console.log(element);
            console.log(index);
            console.log(array);
        });

        //for in
        for (const key in vetor) {
            console.log("for in 1:" + key);
        }

        for (const key in pessoa) {
            console.log("for in 2:" + pessoa[key]);
        }

        //for of (objetos iteraveis - alguma coisa parecida com um array...)
        for (const iterator of vetor) {
            console.log(iterator);
        }

    </script>
~~~

### JS - Arrays - Declaring an Array, Array methods (push( ), pop( ), shift( ), unshift( ), lenght) <a id="arrays"></a>
~~~
    <script>
        //Empty array
        var carro = []

        //Pre-initialized Array
        const fruta = ['laranja', 'morango', 'abacate']

        //Declaraing an Array with constructor
        let legumes = new Array('brócolis', 'cenoura', 'alface')

        //Positions
        var frutaCitrica = fruta[2]

        fruta[3] = "limao"
        fruta[4] = "fisalis"
        fruta[6] = "melancia"

        //Array lenght
        console.log(fruta.length);

        //Push an element - end of an Array
        fruta[fruta.length] = "melão"
        fruta.push("Amora")

        //Push an element - start of an Array
        fruta.unshift("Banana")
        
        //Remove an element - start of an Array
        var fruta3 = fruta.shift()

        //Remove an element - end of an Array
        var fruta4 = fruta.pop()

        //Iterating an Array
        for (let index = 0; index < fruta.length; index++) {
            let element = fruta[index];
            console.log(fruta[index]);
        }

        //Transform Array to String
        console.log(fruta.toString());

        //Passing the reference from Array to Var
        var fruta2 = fruta
        fruta[2] = "Limão"

    </script>
~~~

### JS - Functions <a id="functions"></a>
~~~
    <script>

        var pesoIdealF = calcularPesoIdeal("f", 1.60)
        console.log(pesoIdealF);

        pesoIdealM = calcularPesoIdeal("m", 1.60)
        console.log(pesoIdealM);

        /*
            - Functions are "Tasks"/"Actions" performed as soon as they are called or based of some event.
            - A function can take parameters and return a result. 
        */

        // declaring a function
        function calcularPesoIdeal(genero, altura) {

            let pesoIdeal = 0
            if (genero == "f") {
                pesoIdeal = (62.1 * altura) - 44.7
            } else {
                pesoIdeal = (72.7 * altura) - 58
            }

            return pesoIdeal
        }

        // declaring a var - the content is a function
        var pesoIdeal2 = function(genero, altura) {

            let pesoIdeal = 0
            if (genero == "f") {
                pesoIdeal = (62.1 * altura) - 44.7
            } else {
                pesoIdeal = (72.7 * altura) - 58
            }

            return pesoIdeal
        }

        console.log("peso Ideal 2 : " + pesoIdeal2("f", 1.57));

         // arrow function 
        var pesoIdeal3 = (genero, altura) => { //arrow 

            let pesoIdeal = 0
            if (genero == "f") {
                pesoIdeal = (62.1 * altura) - 44.7
            } else {
                pesoIdeal = (72.7 * altura) - 58
            }

            return pesoIdeal
        }

        // arrow function with one parameter and one line of instruction
        var dobro = num => num * 2
        console.log(dobro(5));

    </script>
~~~

### JS - Events <a id="events"></a>
~~~
    <script>

    // <input type="button" id="idBotao" value="CLique Me" onclick="testarClique()">

        //Event Handler Inline
        function testarClique() {
            console.log("Clicou em clique me!!!");
        }

        //Event Handler Nivel 1 
        var botao = document.getElementById("idBotao2")
    
        botao.onclick = tratamentoBotao2

        function tratamentoBotao2() {
            console.log("Clicou Botão 2");  
        }

        //Anonymous Functions
        botao.onmouseover = function(){
            console.log("Passou o mouse por cima do botão 2");
        }

        //Event Handler Level 2
        var botao3 = document.getElementById("idBotao3")

        botao3.addEventListener("click", tratamentoBota3) //Callback Function

        function tratamentoBota3() {
            console.log("Clicou Botão 3");  
        }

        //Event Handler - Submit Input
        const botao4 = document.getElementById("idBotao4")

        botao4.addEventListener("click", function(event){
            event.preventDefault() //previne o comportamento padrao do formulario 
            console.log(event);

            let email = document.getElementById("idEmail").value
            console.log("Email: " + email);
        })


    </script>
~~~

### JS - Strings Methods <a id="stringsmethods"></a>
~~~
     <script>

        // How to declare Strings (typeof = string)
        const string1 = "A string primitive"; 
        const string2 = 'Also a string primitive';
        const string3 = `Yet another string primitive`;
        const string4 = String(1); 
        const string5 = String(true);
        const string6 = String("Teste");

        // How to declare Strings (typeof = object)
        const string7 = new String("A String object")

        // .valueOf() Property
        console.log(string6.valueOf()); // "Teste"
        console.log(string7.valueOf()); // "A String object"

        // String Methods 
        var gato = "cat"
        console.log(gato[2]);
        console.log("cat"[1]);
        console.log("catwerr".length);
        console.log("cat".charAt(2));

        // Comparing Strings
        const a = "a";
        const b = "b";
 
        // ASCII - Table / CharCode
        if (a < b) {
            console.log(`${a} is less than ${b}`);
        } else if (a > b) {
            console.log(`${a} is greater than ${b}`);
        } else {
            console.log(`${a} and ${b} are equal.`);
        }

           console.log(String.fromCharCode(79,51)); //Return the character from ASCII Table

        // Comparing Variables - Text - Lower case/Upper case
        const upperA = "A"
        console.log(a == upperA); //false
        console.log(a.toLowerCase() == upperA.toLowerCase()); //true
        console.log(a.toUpperCase() == upperA.toUpperCase()); //true
        console.log(areEqualCaseInsensitive(a, upperA));

        function areEqualCaseInsensitive(str1, str2) {
            return str1.toLowerCase() === str2.toLowerCase()
        }

        // Comparing Variables - Number/String
        const numUm = 1
        const charUm = "1" 
        if (numUm == charUm){
            console.log("numUm é igual charUm"); //numUm é igual charUm
        }

        if (numUm === charUm){
            console.log("numUm é igual charUm");
        }else{
            console.log("numUm é diferente de charUm"); //"numUm é diferente de charUm
        }

        // String Template / Literal Template
        const total = 12.4
        const totalComDesconto = 10.00
       
        console.log(`o total da conta é: ${total} , com desconto fica: ${totalComDesconto}`);

        // String.raw
        const filePath = String.raw`C:\Development\profile\aboutme.html`
        console.log(`The file was uploaded from: ${filePath}`);

        // Instance Methods
        const texto1 = "texto"
        const text2 = "123"
        console.log(texto1.charAt(2)); // x
        console.log(texto1.charCodeAt(2)); // 120
        console.log(texto1.concat(text2, " ad", " 12")); // texto 123 ad 12

        const str1 = 'Cats are the best!';
        console.log(str1.endsWith('best!')); // true
        console.log(str1.endsWith('best', 17)); // true

        const sentence = 'The quick brown fox jumps over the lazy dog.';
        const word = 'fox';

        console.log(sentence.includes(word)); // true
    
        let text = "Apple, Banana, Kiwi";
        console.log(text.slice(7, 13)); // Banana
        console.log(text.substring(7, 13)); // Banana
        console.log(text.substr(7, 6)); // Banana
        
        let text3 = "Please visit Microsoft!";
        let newText = text3.replace("Microsoft", "W3Schools"); // Please visit W3Schools!

        let text4 = "Please visit Microsoft!";
        let newText2 = text4.replace(/MICROSOFT/i, "W3Schools"); // Please visit W3Schools!

        let text5 = "Please visit Microsoft and Microsoft!";
        let newText5 = text5.replace(/Microsoft/g, "W3Schools"); // Please visit W3Schools!

        let text6 = "5";
        let padded = text6.padStart(4,"1"); // 1115

        let text7 = "Please, visit, Microsoft, and, Microsoft!";
        let array7 = text7.split(",") ['Please', ' visit', ' Microsoft', ' and', ' Microsoft!']

    </script>
~~~

### JS - CSS with JavaScript <a id="csswithjs"></a>
~~~

   <style>
        body{
            --cor : pink;
        }
        :root {
            --tituloPrincipal: #ffff00; 
        }

        .verde{
            color: var(--cor);
        }

        .violeta{
            color: violet;
        }

    </style>

   <script>

        var btCor = document.getElementById("idBtCor")

        // changing property of var --tituloPrincipal
        btCor.onclick = function(){
            let cor = document.getElementById("idCor").value
            document.body.style.setProperty('--tituloPrincipal', cor);
        }

        // changing classList of titulo1 when mouseenter
        titulo1.onmouseenter = function(){
            titulo1.classList.add("verde")
            titulo1.classList.remove("violeta")
        }

        // changing classList of titulo1 when mouseout
        titulo1.onmouseout = function() {
            titulo1.classList.add("violeta")
            titulo1.classList.remove("verde")
        }

    </script>
~~~

### JS - Creating Elements with .innerHTML and .write <a id="innerhtml"></a>
~~~

   <script>
        var texto = "Teste teste teste"

        var elementoDiv = document.getElementById("idDiv")
        
        var elementoDiv2 = document.getElementById("idDiv2")
        elementoDiv2.innerHTML = `
                                    <p>${texto}</p>
                                    <input type='submit'> 
                                 `

        document.write("<DIV>" + texto + "</DIV>")

    </script>

~~~

### JS - Creating Elements with .createElement and .appendChild <a id="createelement"></a>
~~~

    <script>
        var btInclui = document.getElementById("btIdIncluir")

        btInclui.addEventListener("click", function(event) {
            event.preventDefault()

            //capture whole form 
            let formulario = document.getElementById("frmIdAdiciona")

            //extract date from user
            let usuario = obtemUsuario(formulario)

            //create row from user info
            let usuarioTr = montaTr(usuario)

            //show row on body
            let tBody = document.getElementById("tboIdLinha") 
            tBody.appendChild(usuarioTr)

            //reset form - clear fields
            formulario.reset()
        })


        function obtemUsuario(formulario) {
            let usuario = {
                userId   : formulario.inNmUserId.value,
                password : formulario.inNmPass.value,
                name     : formulario.inNmNome.value,
                cpf      : formulario.inNmCpf.value,
                tipo     : formulario.inNmTipoUser.value
            }

            return usuario
        }

        // create row (tr)
        function montaTr(usuario) {
            let usuarioTr = document.createElement("tr")

            usuarioTr.classList.add("trClUsuarioData")
            
            usuarioTr.appendChild(montaTd(usuario.userId, "tdClInfoUserId"))
            usuarioTr.appendChild(montaTd(usuario.password, "tdClInfoSenha"))
            usuarioTr.appendChild(montaTd(usuario.name, "tdClInfoNome"))
            usuarioTr.appendChild(montaTd(usuario.cpf, "tdClInfoCpf"))
            usuarioTr.appendChild(montaTd(usuario.tipo, "tdClInfoTipoUser"))

            return usuarioTr
        }

        // create column (td)
        function montaTd(dado, classe){
            let usuarioTd = document.createElement("td")

            usuarioTd.textContent = dado
            usuarioTd.classList.add(classe)

            return usuarioTd
        }
    </script>

~~~

### JS - Object - Structure <a id="objectstructure"></a>
~~~
 <script>

        //JavaScript Object - Structure
        let usuario = {
           userId : "User1", //Atributo... 
           password : "SohEuSei",
           nome : "Joao" 
        }

        usuario.userId = "XPTO"
        console.log(usuario.userId); 

        //JSON
    </script>
~~~

### JS - Where To Save Script <a id="jsfiles"></a>
![Alt text](./assets/image.png)


### JS - Windows Types of Alerts <a id="alertstypes"></a>
~~~
<script>
            //Alerts 
             function alerta(){
                console.log("antes do alert ");
                alert("Olá isso é um alerta")    
                console.log("depois do alert ");
            }

            //Window Confirm
             function confirmar(){
                var confirma;
             
                confirma = window.confirm("Confirma a exclusão?");
                
                if (confirma) {
                    console.log("Você clicou em confirmar");
                }else{
                    console.log("Você clicou em cancelar");
                }
            }

            //Prompt alert
             function perguntar(){
                var idade; 

                idade = window.prompt("Digite sua idade:"); 
                console.log(idade); 
            }
    </script>
~~~

### JS - Objects <a id="jsobjects"></a>
~~~
    <script>

        //JSObject 
        const user = {
            id : "XPTO123", 
            funcao: "Administrador", 
            bloqueado: true, 
            instancias: 2, 
            navegadores : ["IE", "chrome", "edge"], 
            pessoa1: {
                nome : "Joao", 
                sobrenome : "Silva", 
                idade : 25, 
                sexo : "m",
                nomeCompleto : function(){
                    return this.nome + " " + this.sobrenome
                }
            } 
        }

        console.log(user.pessoa1.nomeCompleto());
        console.log(user.pessoa1.nome + " " + user.pessoa1.sobrenome);
        console.log(user.navegadores[1]);

    </script>
~~~

### JS - Arrays Methods <a id="arraysmethods"></a>
~~~
   <script>

        //join array into string and add separator (arquivos .csv)
        const fruits = ["Banana", "Orange", "Apple", "Mango"];
        console.log(fruits.join(";"));

        //delete position (stay undefined)
        delete fruits[1];
        console.log(fruits);

        //Concat arrays into new array
        const myGirls = ["Cecilie", "Lone"];
        const myBoys = ["Emil", "Tobias", "Linus"];
        const arr3 = ["Robin", "Morgan"];

        const myChildren = myGirls.concat(myBoys, arr3);
        console.log(myChildren);

        //Transformando matrix into an array
        const myArr = [[1, 2], [3, 4], [5, 6]];
        const newArr = myArr.flat();
        console.log(newArr);

        //insert two itens into array at position 2
        const fruits2 = ["Banana", "Orange", "Apple", "Mango"];
        fruits2.splice(2, 0, "Lemon", "Kiwi");
        console.log(fruits2);

        /erasing element from defined position
        fruits2.splice(3, 1)
        console.log(fruits2);

        //Copy of part of an array
        const fruits3 = ["Banana", "Orange", "Apple", "Mango"];
        const fruits4 = fruits3.slice(1);
        console.log(fruits4);

        //Finding index of item
        const fruits6 = ["Apple", "Orange", "Apple", "Mango"];
        let position = fruits6.indexOf("Apple", 1);

        //filter 
        let over18 = idades.filter(buscarMaior18)
        console.log(over18);

        function buscarMaior18(value, index, array) {
            return value > 18
        }

        //arrow function
        let over18_3 = idades.filter(value => value > 18)
        console.log(over18_3);

        //map
        var numbers3 = numbers1.map(function(value, index, array){
            return value * 2
        })
        console.log(numbers3);

        //reduce
        var numbers4 = [4, 3, 4, 1, 4]
        var soma = numbers4.reduce(somarValores, 0)
        console.log(soma);

        function somarValores(total, value, index, array) {
            return total = total + value 
        }        
        
        //sort
        var num = [2, 30, 10, 1, 0, 23, 12, 21, 100]
        num.reverse()
        console.log(num);

        //sort increasing
        num.sort(function(a, b){
            if (a > b) {
                return 1
            }
            if (a < b) {
                return -1
            }
            return 0 
        })
        console.log(num);
        
        //sort decreasing
        num.sort(function(a, b){
            if (a < b) {
                return 1
            }
            if (a > b) {
                return -1
            }
            return 0 
        })
        console.log(num);
    </script>
~~~

### JS - Let x Var x Const <a id="letvarconst"></a>
~~~
    <script>

        //3 Scopes - Global, Functional, Local/Block
        //4 ways to declare: var, let, const e "no words"
        
        //global scope ONLY - no word reserved
        texto1 = "Texto" 

        //var - global scope - can be redeclared - problem!
        var nome = "Joao"
        var nome = "Igor"

        /*Hoisting of var 
            Hoisting is a JavaScript mechanism that makes
            variable and function declarations are moved to
            the top of its scope before code execution.
        */
        testeHoisting = "12345667"
        console.log("Log 4: " + testeHoisting); //1234567
        var testeHoisting = "Teste Hoisting"

        //let
        let sobreNome = "Silva"
        //let sobreNome = "teste let" //error - cant be redeclared

        let testeLetGlobal = "teste let global" //Let - block scope
        testeEscopoLet()
   
        function testeEscopoLet() {
            console.log("Log 7:" + testeLetGlobal); //"teste let global"
        
            let testeLetLocal = "teste let local" 
            console.log("Log 8:"+ testeLetLocal);   //"teste let local" 
            
            let testeLetLocal2 = "teste let local 2"
            console.log("Log 9:" + testeLetLocal2); //"teste let local 2" 

            if (true) {
                let testeLetLocal2 = 123
                console.log("Log 10:" +  testeLetLocal2); //123
            }
        }

        //const - array and elements can be changed of a const
        const x = [1, 2, 3]
        //x = [3,4,5,6]
        x.push(4)
        x[4] = 8

        console.log(x);

        const aviador = {
            nome: "Santos Dumont", 
            aeronave: "14 Bis", 
            data: "23 de outubro de 1906"
        }

        aviador.nome = "Albero Santos Dumont"
        console.log(aviador);

      // parameters of functions
        testeParamtros("valor1")

        function testeParamtros(params) {
            console.log(params); //"valor1"
            params = "valor2"
            console.log(params); //"valor2"
        }

        console.log("antes do for " + index);  //"antes do for undefined"
     
        for (var index = 5;index < 10; index++) {
            console.log("dentro do For " + index);
        }
        console.log("depois do for " + index); //"depois do for 10"

        while(testeEscopoX != false) //testeEscopoX = undefined
        {
            console.log("Passou pelo while..."); //going to read it one time
            var testeEscopoX = false
        }

    </script>
~~~

### JS - Matrix <a id="matrix"></a>
~~~
    <script>

        //matrix = array of arrays     

        //j=           0   1   2   3      i
        var matriz = [[1, 34, 45, 5],//  0
                      [4, 25, 11, 5],//  1 
                      [6,  2, 35, 6],//  2
                      [7,  4,  7, 8]]//  3

        //Acessing specific position
        let i = 3
        let j = 2
        var x = matriz[i][j]
        console.log(x); //7
        
        //Iterating array - 2d
        console.log(matriz.length); //4
        console.log(matriz[1].length) //4
        
        //Iterating matrix - 2d
        for (let i = 0; i < matriz.length; i++) {
            for (let j = 0; j < matriz[i].length; j++) {
                console.log(matriz[i][j]);
            }
        }

        //matrix - 3d
        var matriz3D = [[[1,   2], [3,   4], [5,   6]], 
                        [[7,   8], [9,  10], [11, 12]], 
                        [[13, 14], [15, 16], [17, 18]]]

        console.log(matriz3D[0][0][1]); //2

        //Example
        var pizzas = []
        
        var pizza1 = []
        pizza1[0] = "Grande"
        pizza1[1] = 35
        pizza1[2] = 35.00
        pizzas.push(pizza1)
        
        var pizza3 = []
        pizza3[0] = "pequena"
        pizza3[1] = 15
        pizza3[2] = 15.00
        pizzas.push(pizza3)

        var pizza = []
        pizza[0] = "Gigante"
        pizza[1] = 50        //diâmetro    
        pizza[2] = 50.00     //preço 
        pizzas.push(pizza)
        
        var pizza2 = []
        pizza2[0] = "media"
        pizza2[1] = 25
        pizza2[2] = 25.00
        pizzas.push(pizza2)

        console.table(pizzas) //matrix of each array

        //calculando a area da pizza
        pizzas.forEach(pizza => {
            let raio = pizza[1] / 2;
            let area = Math.PI * (raio * raio)
            console.log(area);
            pizza.push(area)

            let precoCm2 = pizza[2] / area
            pizza.push(precoCm2)
        })
        console.table(pizzas);

        //Sort matrix of pizzas using "precoCm2"
        pizzas.sort(function(a, b){
            if (a[3] > b[3]) {
                return 1
            }
            if (a[3] < b[3]) {
                return -1
            }
            return 0 
        })

        console.table(pizzas)

    </script>
~~~

### JS - Console <a id="console"></a>
~~~
    <script>

        //Log
        console.log("Isso é um log...")

        //Clear
        //console.clear()

        //Error
        console.error("Isso é uma mensagem de erro!")

        //Warnings
        console.warn("Isso é uma mensagem de aviso!")
        
        //Hided for user
        console.debug("Isso é um registro para debug")
        
        //Info
        console.info("Isso é uma informação")
        
        //Table - works with arrays, objects, matrix, array of objects
        var vetor = [25, 20, 45, 50]
        console.table(vetor)
        
        //Time - count time to execute task
        console.time("label")
        var teste = 0
        for (let index = 0; index < 10000; index++) {
            teste++
            if (index == 5000) {
                console.timeLog("label")   
            } 
        }
        console.timeEnd("label")
        
        //List of object
        var obj = {
            nome: "Eu mesmo",
            idade: 35,
            cpf: "004.742.879.12",
            cargo: "Tecnico"
        }
        console.dir(obj)
        
        //List of object - xml
        console.dirxml(obj)
        
        //Assert - save message if its false on the console 
        const msn = "# é ímpar!"
        for (let index = 0; index < 10; index++) {
            console.assert(index % 2 == 0, { index, msn })
        }
        
        //Count() - how mandy times function is called
        let user = "";
        
        function greet() {
            console.count("gree");
            return `hi ${user}`;
        }
        
        user = "bob";
        greet(); //1
        user = "alice";
        greet(); //2
        greet(); //3
        
        //CountReset(): count = 0
        console.countReset("gree")
        greet(); //1
        
        //Group() - organize the console into topics - like a summary
        console.log("Este é o nível externo");
        console.group();
        console.log("Nível 2");
        console.group();
        console.log("Nível3");
        console.warn("Mais uma mensagem no nível 3");
        console.groupEnd();
        console.log("Devolta ao nível 2");
        console.groupEnd();
        console.log("Devolta ao nível externo");
        
        //Trace() - track functions 
        function funcao1() {
            funcao2();
        }

        function funcao2() {
            funcao3();
        }
        
        function funcao3() {
            console.trace();
        }

        funcao1();
        
    </script>
~~~

### JS - Short Circuit <a id="shortcircuit"></a>
~~~
    <script>

      function testar() {
            if (retornaFalse() && retornaTrue()) {
                console.log("Entrou no IF (&&) - bloco True");
            } else {
                console.log("Entrou no IF (&&) - bloco False");
            }

            //passou False
            //Entrou no IF (&&) - bloco False  

            if (retornaFalse() & retornaTrue()) {
                console.log("Entrou no IF (&) - bloco True");
            } else {
                console.log("Entrou no IF (&) - bloco False");
            }

            //passou False
            //passou True
            //Entrou no IF (&&) - bloco False 

            if (retornaTrue() || retornaFalse()) {
                console.log("Entrou no IF (||) - bloco True");
            } else {
                console.log("Entrou no IF (||) - bloco False");
            }

            //passou True
            //Entrou no IF (&&) - bloco True

            if (retornaTrue() | retornaFalse()) {
                console.log("Entrou no IF (|) - bloco True");
            } else {
                console.log("Entrou no IF (|) - bloco False");
            }

            //passou False
            //passou True
            //Entrou no IF (&&) - bloco True

        function retornaFalse() {
            console.log("passou False");
            return false
        }
        function retornaTrue() {
            console.log("Passou True");
            return true
        }
        }

    </script>
~~~

### JS - Async - Timing <a id="asynctiming"></a>
~~~
       <script>

       //Execute a task in an interval - multiple times
        var cont = 0 
        var intId = setInterval(contar, 1000) 

        function contar() {
            console.log(++cont); // 1 2 3 4 5... (every second)
        }

        //Execute a task in in one click - set all numbers between 0 and 100 at the same time
        function tarefaQualquer(){
            for (let index = 0; index < 100; index++) {
                console.log("Tarefa: " + index); // 1 2 3 4 5... (same time)
            }
        }

        console.log("Primeira Ação");
        setTimeout(function(){
                console.log("Segunda Ação");
        }, 2000)
        console.log("Terceira Ação");

        // "Primeira Ação"
        // "Terceira Ação"
        // "Segunda Ação" - Only shows after 2 seconds

    </script>
~~~

~~~
      <script>

        //JS is Assync
        //Single Thread 
        //non-blocking I/O

        console.log("Primeira Ação");

        setTimeout(function () {
            console.log("Segunda Ação");
        }, 2000)

        console.log("Terceira Ação");

        setTimeout(function () {
            console.log("Quarta Ação");
        }, 2000)

        console.log("Quinta Ação");

        // Order:
        //"Primeira Ação"
        //"Terceira Ação"
        //"Quinta Ação"
        //"Segunda Ação"
        //"Quarta Ação"

    </script>
~~~

### JS - Async - API - Buscar CEP - AJAX <a id="ajaxcep"></a>

~~~
<script>

        var btBuscarCep = document.getElementById("idBtBuscarCep")

        btBuscarCep.onclick = function () {
            buscarCEP(document.getElementById("idCep").value)
        }

        //API - Application Programing Interface
        //Endpoint - URL for web service
        //Latency - amount of time it takes for a data packet to go from one place to another

        function buscarCEP(cep){
            //AJAX - HTTPs Request
            var xhr = new XMLHttpRequest()

            xhr.open("GET", "https://viacep.com.br/ws/" + cep + "/json/" )
            
            xhr.addEventListener("load", function(){
                let resposta = xhr.responseText
                imprimirEndereco(resposta)
            })
            
            xhr.send()
        }

        function imprimirEndereco(enderecoJSON){
            console.log(enderecoJSON)

            let enderecoOBJ = JSON.parse(enderecoJSON) //Convert JSON to JSObject

            console.log(enderecoOBJ);

            console.log("Logradouro " + enderecoOBJ.logradouro);

            let endJSON =  JSON.stringify(enderecoOBJ) //Convert JSObject to JSON

            console.log(endJSON);
        }

    </script>
~~~

### JS - Async - API - Buscar CEP - Await <a id="awaitcep"></a>

~~~
<script>

       var btBuscarCep = document.getElementById("idBtBuscarCep")
        
        btBuscarCep.onclick =  async function () {
            let endereco = await buscarCEP(document.getElementById("idCep").value)
            console.log(endereco); //return JSON object
        }
        
        async function buscarCEP(cep){
            
                var resposta = await fetch("https://viacep.com.br/ws/" + cep + "/json/")
                //console.log(resposta.json()); - returns promise
            return resposta.json()
        }
        
    </script>
~~~

### JS - Sets <a id="sets"></a>

~~~
    <script>

        /*
           Set objects are collections of values. 
           A value in the set may only occur once; it is unique in the set's collection.
        */

        //create set
        let colors = new Set()

        //add elements
        colors.add("red")
        colors.add("blue")
        colors.add("green")
        colors.add("violet")
        colors.add("red") //will not be added

        //display set 
        console.log(colors);

        console.log(colors.has("blue")); //true

        //Remove elements
        colors.delete("blue")

        //Iterate set
        for (const color of colors) {
            console.log(color);
        }

    </script>
~~~

### JS - Maps <a id="maps"></a>

~~~
    <script>

        /*
            The Map object holds key-value pairs and remembers the original insertion order of the keys. Any value (both objects and primitive values) may be used as either a key or a value.
        */

        //Create Map
        let pontuacao = new Map()

        //Add data
        pontuacao.set("Joao", 90)
        pontuacao.set("Alberto", 24)
        pontuacao.set("Joana", 15)

        console.log(pontuacao);

        //Access values
        console.log(pontuacao.get("Joao")); //90

        //Deleting elements
        pontuacao.delete("Alberto")

        //Iterate map 
        for (const [nome, pontos] of pontuacao) {
            console.log(nome + ": " + pontos);
        }

    </script>
~~~

### JS - Stack and Queue <a id="stackqueue"></a>

~~~
    <script>

        //Stack - LIFO (Last In First Out)
        let pilha = []
        pilha.push(1)
        pilha.push(2)
        pilha.push(3)
        pilha.pop() // Remove number 3


        //Queue - FIFO (First In First Out)
        let queue = []
        queue.push(1)
        queue.push(2)
        queue.push(3)
        queue.shift() //Remove number 1

    </script>
~~~

### JS - Linked List <a id="linkedlist"></a>

~~~
   <script>

        /*
            A linked list is a linear data structure similar to an array. However, unlike arrays, elements are not stored in a particular memory location or index. Rather each element is a separate object that contains a pointer or a link to the next object in that list.
        */

        class Node {
            constructor(value){
                this.value = value;
                this.next = null;
            }
        }

        //Criando a lista encadeada 
        let head = new Node(1)
        head.next = new Node(2)
        head.next.next = new Node(3)

    </script>
~~~

### JS - Local Storage <a id="localstorage"></a>

~~~
  <script>

        const inventor = {
            nome: "Alberto Santos Dummont", 
            inventos: ["Balão a hélio", "Dirigivel", "Avião"],
            nacionalidade: "Brasileiro" 
        } 
        const inventorJSON = JSON.stringify(inventor)

        //Create localstorage
        localStorage.setItem("inventor", inventorJSON)

        //Read localstorage
        const engenheiro = localStorage.getItem("inventor")
        const JSONToInventor = JSON.parse(engenheiro)

        console.log(JSONToInventor);

        JSONToInventor.inventos.push("14-Bis")

        //Att register
        localStorage.setItem("inventor", JSONToInventor)

        //Remove register
        localStorage.removeItem("inventor")

    </script>
~~~

### JS - Session Storage <a id="sessionstorage"></a>

~~~
  <script>
        /*
            Data is deleted when browser is closed
        */

        const inventor = {
            nome: "Alberto Santos Dummont", 
            inventos: ["Balão a hélio", "Dirigivel", "Avião"],
            nacionalidade: "Brasileiro" 
        } 
        const inventorJSON = JSON.stringify(inventor)

        //Create sessionstorage
        sessionStorage.setItem("inventor", inventorJSON)

        //Read sessionstorage 
        const engenheiro = sessionStorage.getItem("inventor")
        const JSONToInventor = JSON.parse(engenheiro)

        console.log(JSONToInventor);

        JSONToInventor.inventos.push("14-Bis")

        //Att register
        sessionStorage.setItem("inventor", JSONToInventor)

        //Remove register
        sessionStorage.removeItem("inventor")

    </script>
~~~

### JS - API Coins <a id="apicoins"></a>

~~~
    <script>

        //AJAX
        function buscarMoedasAJAX() {
            //AJAX - HTTPs request
            var xhr = new XMLHttpRequest()

            xhr.open("GET", "https://olinda.bcb.gov.br/olinda/servico/PTAX/versao/v1/odata/Moedas?$top=100&$format=json&$select=simbolo,nomeFormatado,tipoMoeda")

            xhr.addEventListener("load", function () {
                let resposta = xhr.responseText
                let moedas = JSON.parse(resposta)
                //console.log(lMoedas);
                carregarSelectMoedas(moedas)

            })

            xhr.send()
        }

         function carregarSelectMoedas(moedas) {
            //display on screen
            let listaMoedas = document.getElementById("idMoedas")
            for (let i = 0; i < moedas.value.length; i++) {
                console.log(moedas.value[i].simbolo)

                let optionMoeda = document.createElement("option")
                optionMoeda.value = moedas.value[i].simbolo
                optionMoeda.innerText = moedas.value[i].nomeFormatado

                listaMoedas.appendChild(optionMoeda)
            }
        }

        //Fetch
        (async function () {
            let moedas = await buscarMoedasFETCH()
            console.log(moedas);
            carregarSelectMoedas(moedas)
        })()

        async function buscarMoedasFETCH() {

            var resposta = await fetch("https://olinda.bcb.gov.br/olinda/servico/PTAX/versao/v1/odata/Moedas?$top=100&$format=json&$select=simbolo,nomeFormatado,tipoMoeda")

            return resposta.json();

        }

    </script>
~~~

### JS - Callback - Basics <a id="callbasics"></a>

~~~
     <script>

        function somar(a, b, funcaoCB) {
            var res = a + b;
            funcaoCB(res);
        }

        function subtrair(a, b, funcaoCB) {
            var res = a - b;
            funcaoCB(res);
        }

        somar(2, 3, function (params) {
           console.log("Resul: " + params); //Resul: 5
        });

        console.log(subtrair(8, 2, exibirResultado)); // undefined

        function exibirResultado(resul) {
            console.log(resul); //6
        }

    </script>
~~~

### JS - Callback <a id="callback"></a>

~~~
      <script>

        //Assync
        //Single Thread 
        //IO Non Blocking

        console.log("Primeira Ação");

        buscarCEP("89107000", imprimir);//the time to execute depends to latency

        console.log("Terceira Ação");

        setTimeout(function () {
            console.log("Quarta Ação");
        }, 2000)

        console.log("Quinta Ação");


        function buscarCEP(cep, funcaoCB){
            //AJAX - HTTP Request
           
            var xhr = new XMLHttpRequest()

            xhr.open("GET", "https://viacep.com.br/ws/" + cep + "/json/" )
           
            
            xhr.addEventListener("load", function(){
                let resp = xhr.responseText
                funcaoCB(resp)
            })
            
            xhr.send()
        }

        function imprimir(end) {
            console.log(end);
        }

    </script>
~~~

### JS - Promisses - Fetch <a id="promisesfetch"></a>

~~~
     <script>

        //-- Promisses Fetch
       
        fetch("https://viacep.com.br/ws/89107000/json/")
        .then(function(resposta) { 
            return resposta.json()
        })
        .then(function(responseText){
            console.log(responseText);
        })
        .catch(function(erro){
            console.log("Erro no buscarCep: " + erro);
        })
        .finally(function(){
            console.log("Esta tarefa sempre será executada"); //even with error this line will display
        })

    </script>
~~~

### JS - Promisses <a id="promisses"></a>

~~~
    <script>

        //Promises have four states:
        //Pending: When a request has just been made and has not yet brought the result
        //Fulfilled: When the request result was returned successfully
        //Rejected: When the request result was returned with “error”
        //Settled: it is the final state regardless of whether it was carried out or rejected.

        function promiseRealizada() {
            return Promise.resolve("Promise resolvida")
        }

        promiseRealizada().then(function (param) {
            console.log(param);//<---
        })


        function promiseRejeitada() {
            let erro = {
                msn: "Erro Http xxx",
                cod: 500
            }
            return Promise.reject(erro)
        }

        promiseRejeitada().catch(function (erro) {
            console.log(erro);
        })

        //-----------------------------------------------------

        function fetch2(url) {
            return new Promise(function (resolve, reject) {
                //requisição assincrona... 
                var xhr = new XMLHttpRequest()

                xhr.open("GET", url)


                xhr.addEventListener("load", function () {
                    let resposta = xhr.responseText
                    if (resposta) {
                        resolve(resposta)
                    }else{
                        reject("Erro da Requisição")
                    }  
                })

                xhr.send()

            })
        }

        console.log("Inicio do Script");

        fetch2("https://viacep.com.br/ws/89107000/json/").then(function(resolve){
            console.log(resolve);
        })

        console.log("Fim do Script");

    </script>
~~~

### JS - Destructuring <a id="destructuring"></a>

~~~
   <script>

       const alfabeto = ["A", "B", "C", "D", "E", "F"]
       const numbers = [1, 2, 3, 4, 5, 6] 

       //"Breaking" array into variables
       var [a,, c, ...resto] = alfabeto 
       
       console.log(a, c, resto) // A, C ["D","E","F"]

       //Concat two arrays
       var novoArray = [...alfabeto, ...numbers]

       console.log(novoArray); //['A', 'B', 'C', 'D', 'E', 'F', 1, 2, 3, 4, 5, 6]

       //Desconstructing with default values 
       function calculos(a, b) {
            return [a+b, a*b, a/b]
       }

       var [som, mul, div = "indefinido"] = calculos(2, 5)

       console.log(som, mul, div) // 7 10 0.4

       //Destructuring of Objects 
       const usuario = {
            nome : "Alan Turing", 
            cargo: "Matemático",
            endereco: {
                cidade: "london",
                pais: "Inglaterra"
            }, 
            idade: 26
        }

        const usuario2 = {
            idade: 31, 
            filmePredileto: "A bela adormecida"
        }

        const {nome: nomeUso, cargo = "Programador", idade, ...restante} = usuario

        const {endereco: {cidade}} = usuario

        console.log(nomeUso, cargo, idade, restante) //Alan Turing Matemático 26 endereco{…}

        console.log(cidade) //london

        //Concat two objects
        const usuario3 = {...usuario, ...usuario2}

        console.log(usuario3) //{nome: 'Alan Turing', cargo: 'Matemático', endereco: {…}, idade: 31, filmePredileto: 'A bela adormecida'}

        //Destructuring with function

        function imprimirUsuario({nome, idade, filmePredileto = "Não Tem"}) {
            console.log(`Nome: ${nome}. Idade: ${idade}. Filme Predileto: ${filmePredileto}`);
        }

        imprimirUsuario(usuario) //Nome: Alan Turing. Idade: 26. Filme Predileto: Não Tem
        imprimirUsuario(usuario3) //Nome: Alan Turing. Idade: 31. Filme Predileto: A bela adormecida



    </script>

~~~