![node badge](./assets/node-js.png)

- [Node - How to declare variables](#declare)

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