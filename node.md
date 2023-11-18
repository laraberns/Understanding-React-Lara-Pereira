![node badge](./assets/node-js.png)

- [Node.js - Modules](#modules)
- [Node.js - First Server](#firstserver)
- [Node.js - NPM Command Guide](#commandguide)
- [Node.js - Publishing on NPM](#npmpublish)
- [Node.js - Express Server](#express)
- [Node.js - API REST](#rest)
- [Node.js - Path Names](#pathnames)

### Node.js - Modules <a id="modules"></a>
~~~

    ### soma.js

    //EXPORTING FUNCTION SO IT CAN BE USED IN ANOTHER FILE
    module.exports = function (a, b) {
    return a + b 
    }

~~~

~~~

    ### subtracao.js

    var subtracao = function(a, b){
    return a - b 
    }

    //EXPORTING VARIABLE SO IT CAN BE USED IN ANOTHER FILE
    module.exports = subtracao

~~~

~~~

    ### calculadora.js

    const somar = require("./soma.js") //REQUIRE FUNCTION THAT IS EXPORTED IN SOMA.JS
    const subtrair = require("./subtracao.js") //REQUIRE VARIABLE THAT IS EXPORTED IN SOMA.JS (SUBTRACAO)

        console.log(somar(2, 3)); //5
        console.log(subtrair(5, 2)) //3

~~~

### Node.js - First Server <a id="firstserver"></a>
~~~

    ### server.js

    //CREATING HTTP REQUIRE
    const http = require("http")

    //CREATING SERVER WITH UNNAMED FUNCTION WITH REQ AND RESP AS PARAMS
    const servidor = http.createServer(function(req, resp){

    //WHAT WILL DISPLAY ON SCREEN (RESP)
    resp.end(
        `
            <html>
                <head>
                    <meta charset="utf-8">
                </head>
                <body>
                    <h1>Olá Pessoal!!!!</h1>
                </body>
            </html>
        `
        )
    })

    //WHICH PORT THE SERVER WILL BE CREATED
    servidor.listen(3001)

~~~

~~~

    ### serverRotas.js

    //CREATING HTTP REQUIRE
    const http = require("http")

    //CREATING SERVER WITH UNNAMED FUNCTION WITH REQ AND RESP AS PARAMS
    const servidor = http.createServer(function(req, resp){

    // HTML VAR = WHERE RESP WILL BE SET
    let html 

    //ENDPOINT = REQ URL
    if (req.url == "/") {
        html = 
        `
            <html>
                <head>
                    <meta charset="utf-8">
                </head>
                <body>
                    <h1>Olá Pessoal!!!!</h1>
                </body>
            </html>
        `
    }else if(req.url == "/livros"){
        html = 
        `
            <html>
                <head>
                    <meta charset="utf-8">
                </head>
                <body>
                    <h1> Meus livros favoritos </h1>
                </body>
            </html>
        ` 
    }    
   
    //RESP TO THE CLIENT WILL BE HTML VARIABLE
    resp.end(html)
    })

    //WHICH PORT THE SERVER WILL BE CREATED
    servidor.listen(3001)

~~~

### Node.js - NPM Command Guide <a id="commandguide"></a>
~~~

Checking if npm is installed:

Returns the installed npm version, if installed...

>npm -v 


Setting up the Project as a Node Project:
Creates the package.json file; the system will prompt for the value of each variable.

>npm init   

The "-y" parameter initializes package.json variables with default values.

>npm init -y 


Installing the Express package:

>npm install express@4.16.3 --save-exact

// (version = @4.16.3)


Downloading all project dependencies:

To share the project, delete the node_modules folder from the project. This way, when installing the project on another operating system, simply download the dependencies again to maintain OS compatibility.

>npm install 

Optionally, the install parameter can be abbreviated:

>npm i


Installing nodemon:

>npm install nodemon -g 

// The -g means that the installation will be global and not just for the project


Returns the npm path:
>npm  config get prefix 
~~~

### Node.js - Publishing on NPM <a id="npmpublish"></a>

~~~
1. Create your account on NPM
    https://www.npmjs.com/

2. Create a repository on GitHub and clone it to your machine

3. Create a Node project
    npm init

4. Create your module in index.js

5. While in the project folder, log in to NPM
    npm login

6. Test if you are really logged in
    npm whoami

7. Publish the Module 
    npm publish
~~~

### Node.js - Express Server <a id="express"></a>
~~~
    const express = require("express")
    const app = express()
    const conversorJson = require("body-parser")
    const cors = require("cors")

    //MIDDLEWARE
    app.use(conversorJson.urlencoded({extended: false}))
    app.use(conversorJson.json())

    //HEADER
    app.use(function(req, resp, next){
    resp.header("Access-Control-Allow-Origin", "*")

    app.use(cors())
    next()
    })

    //ROUTES
    app.get("/", function (req, resp) {

    resp.send(
        `<html>
            <head>
                <meta charset="utf-8">
            </head>
            <body>
                <h1> Olá Pigmeu!!! </h1>
            </body>
        </html>
        ` 
    )
    })

    app.get("/livros", function(req, resp){

    resp.send(
        `<html>
            <head>
                <meta charset="utf-8">
            </head>
            <body>
                <h1> Listagem de Livros </h1>
            </body>
        </html>
        `   
    )
    })

    //ROUTE WITH JSON
    app.get("/livro", function(req, resp){

    const livro = {
        "titulo" : "Silencio dos inocentes", 
        "autor" : "Thomas Harris" 
    }

    resp.json(livro)

    })


    //GET ROUTE WITH PARAMS
    app.get("/usuario", function (req, resp) {
    
    let nome = req.query.nmNome
    let cpf = req.query.nmCpf

    console.log("Chegou na rota usuario",  nome, cpf);

    resp.json({
        "nomeUsu": nome, 
        "cpfUsu:": cpf
        })
    })

    //POST ROUTE WITH PARAMS
    app.post("/usuario", function(req, resp){

    let nome = req.body.nmNome
    let cpf = req.body.nmCpf

    resp.json({
        "nomeUsu": nome, 
        "cpfUsu:": cpf
        })
    })

    //DINAMIC ROUTES
    app.get("/ola/:nome/:cargo", function(req, resp){
    console.log(req.params.nome);
    console.log(req.params.cargo);

    resp.send("<h1> Ola " + req.params.nome + "</h1>")
    } )


    //CREATING SERVER WITH EXPRESS
    app.listen(3001)
 
~~~

~~~
    ### FRONT-END - GETTING DATA WITH EXPRESS

    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    </head>
    <body>
    <form action="" method="">
        <label for="idNome">Nome:</label><br>
        <input type="text" name="nmNome" id="idNome"><br>
        <label for="idCpf">CPF:</label><br>
        <input type="text" name="nmCpf" id="idCpf"><br><br>
        <input type="button" value="enviarGet" onclick="requisicaoGet()">
        <input type="button" value="enviarPost" onclick="requisicaoPost()">
    </form> 

    <script>

        //GET
        async function requisicaoGet() {

            let nome = document.getElementById("idNome").value
            let cpf = document.getElementById("idCpf").value

            let resposta = await fetch(`http://localhost:3001/usuario?nmNome=${nome}&nmCpf=${cpf}`)
            console.log(await resposta.json()) 

        }

        //POST
        async function requisicaoPost() {
            let nome = document.getElementById("idNome").value
            let cpf = document.getElementById("idCpf").value

            var option = {
                method : "POST", 
                body: JSON.stringify({
                    nmNome: nome,
                    nmCpf: cpf
                }),
                headers: {"Content-Type":"application/json" }
            }

            let resposta = await fetch("http://localhost:3001/usuario", option)
            console.log(await resposta.json());
        }

    </script>

    </body>
    </html>
~~~

### Node.js - API REST <a id="rest"></a>

    REST API (Representational State Transfer)

    - It is an architectural model for distributed systems.

    - Roy Fielding, one of the main authors of the HTTP protocol, in 2000 listed some architectural models that could be used for the development of distributed systems, among them REST.

    - The REST model served as the foundation for the HTTP protocol.

    CONCEPTS:

    - Resources:

        -- Student
        -- Topic
        -- Course
        -- Disciplines
        -- Resource Identifier (URI):

        -- Student (/students)
        -- Topic (/topics)
        -- Course (/courses)
        -- Disciplines (/discipline)

        -- Resource Manipulation (HTTP Verbs):
               CRUD - Create, Read, Update, Delete
       ====== 
            Queries     GET/student
                        GET/student/{id}
            Create New  POST/student
            Update      PUT/student
                        PUT/student/{id}
            Delete      DELETE/student
                        DELETE/student/{id}

        - Representation of Resources (Media Type):
           
            - JSON 
            "student":{
            "userId" : "XPTO123", 
            "name" : "John Von Neumann", 
            "type" : "admin" 
            }

            - XML 
            <student>
            <userId>XPTO123</userId>
            <name>John Von Neumann</name>
            <type>admin</type>
            </student>
    
            - TXT, HTML, Binary, etc.
            - Stateless Communication (does not maintain an open session)

            HTTP status codes

            - https://developer.mozilla.org/en-US/docs/Web/HTTP/Status 

### Node.js - Path Names <a id="pathnames"></a>
~~~

    ### server.js

    const express = require("express")
    const path = require("path")

    const app = express()

    app.listen(3001)

    // WHEN 3001 TERMINAL IS OPENED IT WILL DISPLAY THE CONSOLE.LOGS BELOW
    app.get("/", function(req, resp){

    console.log("__dirname: " + __dirname); 
    //__dirname: C:\Users\Lara\Desktop\Entra 21 - 2023\006-Node\006-Devolver Paginas Html

    console.log("basename: " + path.basename(__dirname));
    //basename: 006-Devolver Paginas Html

    console.log("dirname: " + path.dirname(__dirname));
    //dirname: C:\Users\Lara\Desktop\Entra 21 - 2023\006-Node

    console.log("extname: " + path.extname("index.html"));
    //extname: .html

    resp.sendFile(path.join(__dirname + "/paginas/index.html"))
    // WILL DISPLAY WHAT IS ON INDEX.HTML PAGE ON SERVER 3001
})

~~~

