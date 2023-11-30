![node badge](./assets/node-js.png)

- [Node.js - Common Modules](#modules)
- [Node.js - Es6 Modules](#es6modules)
- [Node.js - First Server](#firstserver)
- [Node.js - NPM Command Guide](#commandguide)
- [Node.js - Publishing on NPM](#npmpublish)
- [Node.js - Express Server](#express)
- [Node.js - API REST](#rest)
- [Node.js - Path Names](#pathnames)
- [Node.js - Static Files](#staticfiles)
- [Node.js - Middlewares](#middlewares)
- [Node.js - Saving Files](#savingfiles)
- [Node.js - Environment Vars](#environmentvars)
- [Node.js - Authentication with JWT](#jwt)

### Node.js - Common Modules <a id="modules"></a>
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

~~~

    ### mate.js

    const mult = (a, b) => {
    return a * b
    }

    const div = (a, b) => {
        return a / b
    }

    module.exports = {
        mult,
        div
    }

~~~

~~~

    ### calculadora.js

    const mate = require("./mate.js")

    console.log(mate.div(6, 3)) //2
    console.log(mate.mult(2, 4)); //8

~~~

~~~

    ### mate.js

    exports.mult = (a, b) =>{
    return a * b
    }

    exports.div = (a, b) => {
        return a / b 
    }


~~~

~~~

    ### calculadora.js

    const {div, mult} = require("./mate.js")

    console.log(div(6, 3)) //2
    console.log(mult(2, 4)); //8

~~~

### Node.js - Es6 Modules <a id="es6modules"></a>
~~~

    ### SUBTRACAO.JS

    var subtracao = function(a, b){
        return a - b 
    }

    export default subtracao

~~~

~~~

    ### MODULOS.JS

    export const getNomeCompleto = (nome, sobreNome) => {
        return nome + " " + sobreNome;
    }

    export const getSobrenome = (nome, sobreNome) => {
        return sobreNome
    }

~~~

~~~

    ### CALCULADORA.JS

    import subtrair from "./subtracao.js";
    import { getNomeCompleto, getSobrenome } from "./modulos.js";

    console.log(subtrair(5, 2)) //3

    console.log(getNomeCompleto("Joao", "da Silva")); //Joao da Silva
    console.log(getSobrenome("Joao", "da Silva")); //da Silva
    
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

    // index.js file

    const express = require("express") 
    const cors = require("cors")

    const app = express() 

    //Global Middlewares
    app.use(express.urlencoded({extended: false})) 
    app.use(express.json())

    app.use(cors())

    app.use(function(req, resp, next){
        resp.setHeader("Access-Control-Allow-Origin", "*")
        resp.setHeader("Access-Control-Allow-Headers", "Content-Type, x-requested-wit")
        next()
    })

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

    app.get("/livro", function(req, resp){

        const livro = {
            "titulo" : "Silencio dos inocentes", 
            "autor" : "Thomas Harris" 
        }

        resp.json(livro)

    })

    // GET
    app.get("/usuario", function (req, resp) {
        
        let {nmNome: nome, nmCpf: cpf} = req.query

        resp.json({
            "nomeUsu": nome, 
            "cpfUsu:": cpf
            })
    })

    // POST
    app.post("/usuario", function(req, resp){

        let {nmNome, nmCpf} = req.body

        resp.json({
            "nomeUsu": nmNome, 
            "cpfUsu:": nmCpf
            })
    })

    //DINAMIC ROUTES
    app.get("/ola/:nome/:cargo", function(req, resp){

        resp.send("<h1> Ola " + req.params.nome + "</h1>")
    } )

    app.listen(3000)

~~~

~~~
    // index.html file

    <!DOCTYPE html>
        <html lang="en">
            <head>
                <meta charset="UTF-8">
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
                <title>Document</title>
            </head>
            <body>
                <form action="http://localhost:3000/usuario" method="post">

                <label for="idNome">Nome:</label><br>
                <input type="text" name="nmNome" id="idNome"><br>
                <label for="idCpf">CPF:</label><br>
                <input type="text" name="nmCpf" id="idCpf"><br><br>
                <input type="submit">

                </form> 

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

### Node.js - Static Files <a id="staticfiles"></a>
~~~

    // index.js

    const express = require("express")
    const path = require("path")

    const app = express() 

    //Maping static files

   // This Express middleware is used to serve static files. It maps files in the "public" folder to the root of the server. The path.join(__dirname, "public") constructs the full path to the "public" folder from the directory where the script is being executed (__dirname represents the current directory).

    app.use(express.static(path.join(__dirname, "public"))); 

    app.use(express.static(path.join(__dirname, "livros")));

    app.get("/", function (req, resp) {
        resp.sendFile(__dirname + "/index.html")
    })

    app.listen(3001)

~~~

~~~
    //index.html

    <html>
    <head>
        <meta charset="utf-8">
        <link rel="stylesheet" href="css/estilos.css">
    </head>

    <body>
        <div>
            <h1> Meus Livros Favoritos 3.1 </h1>
        </div>

        <!-- Front-end is sent by NODE -->
        <img id="idImagem" src="img/autolah.jpg" alt="" width="15%">

        <!--  Front-end is developed in a project not together with Back-end -->
        <img id="idImagem" src="http://localhost:3001/img/joinha.jpg" alt="" width="15%">

        <!--  External server --> 
        <img id="idImagem" src="https://ivan-j-borchardt.github.io/imagens/joinha.jpg" alt="" width="15%">       
        
        <!-- Download Link-->
        <p>baixe o livro <a href="Clean Code.pdf" download>Clean Code</a> aqui</p>
    </body>

    <!-- JS file -->
    <script src="js/log.js"></script>

    </html>
~~~

### Node.js - Middlewares <a id="middlewares"></a>
~~~

    // index.js

    const express = require("express")
    const app = express()

    //GLOBAL MIDDLEWARE
    app.use(function (req, resp, next) {
        if (req.query.nmUser == "XPTO" && req.query.nmSenha == 1234) {
            resp.token = {
                teste: "OK"
            }

            console.log("Middleware 1");

            next()
        } 

        resp.status(401).end() 

    })

    //http://localhost:3001/?nmUser=XPTO&nmSenha=1234
    app.get("/", function (req, resp) {
        resp.json({msn: "Chegou na rota raiz"})
    })


    //http://localhost:3001/rota1?nmUser=XPTO&nmSenha=1234
    app.get("/rota1", function (req, resp) {
        resp.json({msn: "Chegou na rota 1"})
    })

    //ROUTE MIDDLEWARE

    //http://localhost:3001/usuario?nmUser=XPTO&nmSenha=1234
    app.get("/usuario", verificarUser ,function (req, resp) {

        resp.json({msn: "Chegou na rota usuario - GET",
            user: req.query.nmUser, 
            cod: req.query.nmSenha
            })
    })

    function verificarUser(req, resp, next) {
        if (req.query.nmUser == "XPTO" && req.query.nmSenha == 1234) {
            resp.token = {
                teste: "OK"
            }
            next()
        } 
        resp.status(401).end()  
    }


    app.listen(3001)

~~~

### Node.js - Saving Files <a id="savingfiles"></a>
~~~

    // index.js

    const fs = require("fs/promises")

    const config = {
        param1: "Parametro1", 
        param2: 1234, 
        param3: "Direita"
    }

    // save on config.txt -> {"param1":"Parametro1","param2":1234,"param3":"Direita"}
    salvar(JSON.stringify(config))

    lerArquivo()

    async function salvar(dado) {
        await fs.writeFile("config.txt", dado)
    }

    async function lerArquivo() {
        const dado = await fs.readFile("config.txt", "utf-8")

        console.log(dado); // {"param1":"Parametro1","param2":1234,"param3":"Direita"}
    }

~~~

### Node.js - Environment Vars <a id="environmentvars"></a>

~~~

    ### index.js

    require('dotenv').config({ path: 'index.js' });

    PORTA=3000
    NOME='Lara'

    // Access PORTA
    const porta = process.env.PORTA;

    // Access NOME
    const nome = process.env.NOME;

    console.log(`Porta: ${porta}`); //Porta: 3000
    console.log(`Nome: ${nome}`); //Nome: Lara
~~~

### Node.js - Authentication with JWT <a id="jwt"></a>
~~~

    import express from "express" //CREATE SERVER
    import jwt from "jsonwebtoken" //AUTHENTICATION TOKENS
    const SECRET = process.env.SECRET || "dfghj&%$GHH5/hbj54"

    const app = express()
    app.use(express.json()) //ANALYZE BODY WITH JSON

    //MIDDLEWARE FOR CHECKING JWT
    function verificarJWT(req, res, next) {
        const token = req.header("x-access-token")

        jwt.verify(token, SECRET, function(error, decoded) {
            if (error) {
                res.status(401).end()
            }

            next()
        })
        
    }

    //ROOT ROUTE
    app.get("/", (req, res)=>{
        res.status(200).send("Olá")
    })

    //GENERATE TOKEN IF LOGIN IS CORRECT
    app.post("/login", (req, res)=>{

        if (req.body.user == "FT012" && req.body.password == "SohEuSei") {

            const token = jwt.sign({userId: 123}, SECRET, {expiresIn: 60})

            res.status(200).json({auth: true, token})
        } 

        res.status(403).end()
        
    })

    //IF TOKEN IS OK, STATUS = 200 AND DISPLAY LISTA DE USUARIOS
    app.get("/user", verificarJWT,  (req, res)=>{
        res.status(200).send("Lista de usuarios")
    })


    const PORT = process.env.PORT || 3000
    app.listen(3000)
~~~
