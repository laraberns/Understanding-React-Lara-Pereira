## JavaScript - Logic Programming

### How to declare variables
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

### Types of data - Strings, Numbers, Boolean, Object...
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

### Arithmetic operators
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

### Getting Elements from HTML
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

### Selection Structures (If/Else and Switch/Case)
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

### Repeating Structures (while, do/while, for)
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