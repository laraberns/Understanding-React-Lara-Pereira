## JavaScript - Logic Programming

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