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
- [Node.js - API Rest P1](#p1rest)
- [Node.js - API Rest P2](#p2rest)
- [Node.js - API Rest P3](#p3rest)
- [Node.js - API Rest P4](#p4rest)
- [Node.js - API Rest P5](#p5rest)
- [Node.js - API Rest P6](#p6rest)
- [Node.js - HTTPs HTTP2](#https)
- [Node.js - Testing with JEST](#jest)
- [Node.js - Connecting with DB PostgreSQL](#postgresql)

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

### Node.js - API Rest P1 <a id="p1rest"></a>
~~~
    ### server.js

    import app from "./src/app.js"

    const PORT = process.env.PORT || 3001
    app.listen(PORT, ()=>{
        console.log(`Server Rodando em http://localhost:${PORT}`);
    } )
~~~

~~~
    ### src/app.js

    import express from "express"

    const app = express()

    //MIDDLEWARES FOR POST
    app.use(express.urlencoded({extended:false}))
    app.use(express.json())

    //Mockup DATABASE
    const autors = [
        {id: 1, nome: "Blaise Pascal", ano: 1642, contribuicao: "Pascalina"},
        {id: 2, nome: "Charles Babbage", ano: 1833, contribuicao: "Engenho analítico"},
        {id: 3, nome: "Ada Lovelace", ano: 1833, contribuicao: "Bases da lógica de Programação"},
        {id: 4, nome: "Reynold B. Johnson", ano: 1956, contribuicao: "Disco Rígido"},
        {id: 5, nome: "Tim Berners Lee", ano: 1956, contribuicao: "World Wide Web"}
    ] 

    function buscarAutorPorId(id) {
        return autors.filter(autor => autor.id == id)[0]
    }

    function buscarIndexAutorPorId(id) {
        return autors.findIndex(autor => autor.id == id)
    }

    //Read all authors
    app.get("/autor", (req, res)=>{
        //lógica de consulta ao Banco de dados 
        //autors 
        res.status(200).send(autors)
    })

    //Get author
    app.get("/autor/:id", (req, res)=>{
        //lógica de consulta ao Banco de dados 
        //autors 
        let autor = buscarAutorPorId(req.params.id)
        res.status(200).json(autor)
    })

    //Create author
    app.post("/autor", (req, res)=>{
        autors.push(req.body)
        res.status(201).send("Autor cadastrado com sucesso")
    })

    //Update author
    app.put("/autor/:id", (req, res)=>{
        let indexAutor = buscarIndexAutorPorId(req.params.id)
        autors[indexAutor].nome = req.body.nome
        autors[indexAutor].ano = req.body.ano
        autors[indexAutor].contribuicao = req.body.contribuicao
        res.status(200).json(autors[indexAutor])
    })

    //Delete author
    app.delete("/autor/:id", (req, res)=>{
        let indexAutor = buscarIndexAutorPorId(req.params.id)
        autors.splice(indexAutor, 1)
        res.status(200).send(`Autor ${req.params.id} excluído com sucesso!`)
    })

    //EXPORTING APP
    export default app 
~~~

### Node.js - API Rest P2 <a id="p2rest"></a>
~~~
    ### server.js

    import app from "./src/app.js"

    const PORT = process.env.PORT || 9000
    app.listen(PORT, () => console.log(`servidor rodando na ${PORT}`))
~~~

~~~
    ### app/app.js

    import express from 'express'
    import AutorController from './app/controllers/AutorController.js'

    const app = express()

    //middlewares post
    app.use(express.urlencoded({ extended: false }))
    app.use(express.json())

    //Read all authors
    app.get('/autor', AutorController.index)

    //Get author
    app.get('/autor/:id', AutorController.show)

    //Create author
    app.post('/autor', AutorController.store)

    //Update author
    app.delete("/autor/:id", AutorController.delete)

    //Delete author
    app.put("/autor/:id", AutorController.update)

    export default app
~~~

~~~
    ### app/database/conexao.js

    //mockup
    const autores = [
        { id: 1, nome: "Blaise", ano: 1642, contribuicao: "Pascalina" },
        { id: 2, nome: "Charles", ano: 1833, contribuicao: "Engenho analítico" }
    ]

    function buscaAutorId(id) {
        return autores.filter((autor) => autor.id == id)[0]
    }

    function buscarIndexAutorId(id) {
        return autores.findIndex((autor) => autor.id == id)
    }

    function getAutores(){
        return autores
    }

    export {
        buscaAutorId,
        buscarIndexAutorId,
        getAutores
    }
~~~

~~~
    ### app/controllers/AutorController.js

    import { buscaAutorId, buscarIndexAutorId, getAutores } from "../database/conexao.js"

    let autores = getAutores()

    class AutorController {
        index(req, res) {
            res.status(200).send(autores)
        }

        show(req, res) {
            let autor = buscaAutorId(req.params.id)
            console.log(autor);
            res.status(200).json(autor)
        }

        store(req, res) {
            autores.push(req.body)
            res.status(201).send("Autor cadastrado")
        }

        update(req, res) {
            let indexAutor = buscarIndexAutorId(req.params.id)
            autores[indexAutor].nome = req.body.nome
            autores[indexAutor].ano = req.body.ano
            autores[indexAutor].contribuicao = req.body.contribuicao
            res.status(200).end()
        }

        delete(req, res) {
            let indexAutor = buscarIndexAutorId(req.params.id)
            autores.splice(indexAutor, 1)
            res.status(200).json("Autor deletado")
        }
    }

    // Singleton (Design Patterns)
    export default new AutorController
~~~

### Node.js - API Rest P3 <a id="p3rest"></a>

~~~
    ### server.js

    import app from "./src/app.js"

    app.listen(9000, ()=>{
        console.log(`Server Rodando`);
    } )
~~~

~~~
    ### .src/app/controllers/AutorController.js

        import AutorRepository from "../repositories/AutorRepository.js"

        class AutorController{

        index(req, res){
            res.status(200).send(AutorRepository.findAll())
        }

        show(req, res){
            res.status(200).json(AutorRepository.findById(req.params.id))
        }

        store(req, res){
            AutorRepository.create(req.body)
            res.status(201).send("Autor cadastrado com sucesso")
        }

        update(req, res){
            res.status(200).json(AutorRepository.update(req.params.id, req.body))
        }

        delete(req, res){
            AutorRepository.delete(req.params.id)
            res.status(200).send(`Autor ${req.params.id} excluído com sucesso!`)
        }
        }

        export default new AutorController
~~~

~~~
    ### .src/app/database/conexao.js

    const autors = [
        {id: 1, nome: "Blaise Pascal", ano: 1642, contribuicao: "Pascalina"},
        {id: 2, nome: "Charles Babbage", ano: 1833, contribuicao: "Engenho analítico"},
        {id: 3, nome: "Ada Lovelace", ano: 1833, contribuicao: "Bases da lógica de Programação"},
        {id: 4, nome: "Reynold B. Johnson", ano: 1956, contribuicao: "Disco Rígido"},
        {id: 5, nome: "Tim Berners Lee", ano: 1956, contribuicao: "World Wide Web"}
    ] 

    function buscarAutorPorId(id) {
        return autors.filter(autor => autor.id == id)[0]
    }

    function buscarIndexAutorPorId(id) {
        return autors.findIndex(autor => autor.id == id)
    }

    function getAutors() {
        return autors
    }

    export {buscarAutorPorId, buscarIndexAutorPorId, getAutors}
~~~

~~~
    ### .src/app/repositories/AutorRepository.js

        import {buscarAutorPorId, buscarIndexAutorPorId, getAutors} from "../database/conexao.js"

    class AutorRepository{
        findAll(){
            return getAutors()
        }

        findById(id){
            return buscarAutorPorId(id)
        }

        create(autor){
            getAutors().push(autor)
        }

        update(id, autor){
            let indexAutor = buscarIndexAutorPorId(id)
            let autors = getAutors()
            autors[indexAutor].nome = autor.nome
            autors[indexAutor].ano = autor.ano
            autors[indexAutor].contribuicao = autor.contribuicao

            return autors[indexAutor]
        }

        delete(id, autor){
            let indexAutor = buscarIndexAutorPorId(id)
            getAutors().splice(indexAutor, 1)
        }
    }

    export default new AutorRepository()
~~~

~~~
 ### .src/app/app.js

    import express from "express"
    import AutorController from "./app/controllers/AutorController.js"

    const app = express()

    //MIDDLEWARES
    app.use(express.urlencoded({extended:false}))
    app.use(express.json())

    //Read
    app.get("/autor", AutorController.index)
    app.get("/autor/:id", AutorController.show)

    //Create
    app.post("/autor", AutorController.store)

    //Update
    app.put("/autor/:id", AutorController.update)

    //Delete
    app.delete("/autor/:id", AutorController.delete)

    export default app 
~~~

### Node.js - API Rest P4 <a id="p4rest"></a>

~~~
### THE ONLY THING BETWEEN P3 AND P4 THAT CHANGES IS THE CREATION OF ROUTES.JS

    ### app/routes.js

        import { Router } from "express";
        import AutorController from "./app/controllers/AutorController.js"

        const router = Router()

        //Read
        router.get("/autor", AutorController.index)
        router.get("/autor/:id", AutorController.show)

        //Create
        router.post("/autor", AutorController.store)

        //Update
        router.put("/autor/:id", AutorController.update)

        //Delete
        router.delete("/autor/:id", AutorController.delete)

        export default router
~~~

~~~

    ### app/app.js

        import express from "express"
        import router from "./routes.js"

        const app = express()

        //MIDDLEWARES
        app.use(express.urlencoded({extended:false}))
        app.use(express.json())

        app.use(router)

        export default app 
~~~

### Node.js - API Rest P5 <a id="p5rest"></a>

~~~
    ### THE ONLY THING BETWEEN P4 AND P5 THAT CHANGES IS THE SERVER

    //server.js

    import app from "./src/app.js"
    import https from "https"
    import fs from "fs"

    const server = https.createServer({
        key:  fs.readFileSync("privatekey.pem", "utf-8"),
        cert: fs.readFileSync("certificate.pem", "utf-8")
    }, app)

    const PORT_HTTPS = 3000
    server.listen(PORT_HTTPS, ()=>{
        console.log(`Server Rodando em https://localhost:${PORT_HTTPS}`);
    } )

    const PORT =  3001
    app.listen(PORT, ()=>{
        console.log(`Server Rodando em http://localhost:${PORT}`);
    } )
~~~

### Node.js - API Rest P6 <a id="p6rest"></a>
~~~

// server.js

    import app from "./src/app.js"
    import https from "https"
    import fs from "fs"

    const server = https.createServer({
        key:  fs.readFileSync("privatekey.pem", "utf-8"),
        cert: fs.readFileSync("certificate.pem", "utf-8")
    }, app)


    //https server
    const PORT_HTTPS = process.env.PORT_HTTPS || 3000
    server.listen(PORT_HTTPS, ()=>{
        console.log(`Server Rodando em https://localhost:${PORT_HTTPS}`);
    } )

    //http server
    const PORT = process.env.PORT_HTTP || 3001
    app.listen(PORT, ()=>{
        console.log(`Server Rodando em http://localhost:${PORT}`);
} )

// app.js

    import express from "express"
    import routes from "./routes.js"

    const app = express()

    app.use(express.urlencoded({extended:false}))
    app.use(express.json())

    app.use(routes)

    export default app 

// routes.js

    import { Router } from "express";
    import AutorController from "./app/controllers/AutorController.js"

    const router = Router()

    //Read All
    router.get("/autor", AutorController.index)

    // Read one author by Id
    router.get("/autor/:id", AutorController.show)

    //Create author
    router.post("/autor", AutorController.store)

    //Update author
    router.put("/autor/:id", AutorController.update)

    //Delete author
    router.delete("/autor/:id", AutorController.delete)

    export default router

// AutorController.js

    import AutorRepository from "../repositories/AutorRepository.js"

    class AutorController{

        // Show All authors
        async index(req, res){
            let autor = await AutorRepository.findAll() 
            res.status(200).send(autor)
        }

        // Show by Id
        async show(req, res){
            let autor = await AutorRepository.findById(req.params.id)
            res.status(200).json(autor)
        }

        // Create author
        async store(req, res){
            let status = await AutorRepository.create(req.body)
            res.status(201).send(status)
        }

        // Update author
        async update(req, res){
            let autor = await AutorRepository.update(req.params.id, req.body)
            res.status(200).json(autor)
        }

        // Delete author
        async delete(req, res){
            let autor = await AutorRepository.delete(req.params.id)
            res.status(200).send(autor)
        }
    }

    export default new AutorController

// AutorRepository.js 

import {consulta} from "../database/conexao.js"

    class AutorRepository{

        //CRUD
        create(autor){
            const sql = 'insert into autor(nome, ano, contribuicao) values ($1, $2, $3) returning *'
            const valores = [autor.nome, autor.ano, autor.contribuicao]
            return consulta(sql, valores, "Erro ao cadastrar Autor!")
        }
        
        findAll(){
            const sql = 'select * from autor'
            const valores = []
            return consulta(sql, valores, "Erro ao buscar Autor!")
        }
        
        findById(id){
            const sql = 'select * from autor where id = $1'
            const valores = [id]
            return consulta(sql, valores, "Erro ao buscar Autor por Id!")
        }
        
        update(id, autor){
            const sql = 'update autor set nome = $2, ano = $3, contribuicao = $4 where id = $1 returning *'
            const valores = [id, autor.nome, autor.ano, autor.contribuicao]
            return consulta(sql, valores, "Erro ao alterar Autor por Id!")
        }

        
        delete(id){
            const sql = 'delete from autor where id = $1 returning *'
            const valores = [id]
            return consulta(sql, valores, "Erro ao deletar Autor por Id!")
        }
    }

    export default new AutorRepository()

// conexao.js 

    import path from 'path'
    import { fileURLToPath } from 'url'
    import pg from 'pg'
    import {config} from 'dotenv'

    const {Pool} = pg

    const __filename = fileURLToPath(import.meta.url)
    const __dirname = path.dirname(__filename)

    config({
        overide: true, 
        path:  path.join(__dirname, "conexao.env") 
    })

    const dadosConexao = {
        user: process.env.USER,
        host: process.env.HOST,
        database: process.env.DATABASE,
        password: process.env.PASSWORD,
        port: process.env.PORT
    }

    const pool = new Pool(dadosConexao)
    var client
    (async function(){
        client =  await pool.connect()
    })()

    export const consulta = (sql, valores, msnErro)=>{
        return new Promise(function(resolve, reject){
            client.query(sql, valores, function(erro, resul){
                if (erro) {
                    return reject(msnErro + " " + erro)
                }
                return resolve(resul.rows)
            })
        })
    }

    ~~~


### Node.js - HTTPs HTTP2 <a id="https"></a>

~~~
    # HTTPS
        ## Why use
        - Encrypted data transfer
        - Possibility to verify the server's identity on the client side
        - Internet browsers and search engines like Google prefer HTTPS

        ## Node.js has native support for HTTPS
        - HTTPS module instead of HTTP
        - Much of the HTTP API is reused in HTTPS
        - Requires a Private Key and a Digital Certificate

        ### Creating Certificates
        - There are 2 possibilities
            - Self-signed Certificates
            - Certificates generated by official certifying authorities

        ### OpenSSL on Windows
        - Download: https://slproweb.com/products/Win32OpenSSL.html
        - How to Install: https://forum.casadodesenvolvedor.com.br/topic/44836-como-instalar-o-openssl-passo-a-passo-para-instalar-o-openssl-no-windows/

        - Environment Variables:
        set Path=C:\Program Files\OpenSSL-Win64\bin
        set OPENSSL_CONF=C:\Program Files\OpenSSL-Win64\bin\openssl.cfg

    ~~~
        # Generating Private Key
        $ openssl genrsa -out privatekey.pem 4096

        # Generating CSR (Certificate Signing Request)
        $ openssl req -new -key privatekey.pem -out csr.pem

        # Generating the certificate
        $ openssl x509 -in csr.pem -out certificate.pem -req -signkey privatekey.pem -days 365

        # Checking details of the generated certificate
        $ openssl x509 -in certificate.pem -text -noout
    ~~~

        - Generating Private Key and Certificate:
    ~~~
        $ openssl req -nodes -x509 -newkey rsa:2048  -keyout key.pem -out cert.pem -days 365
    ~~~

        ### Online SSL Generator
        - https://pt.rakko.tools/tools/46

        ## Chrome Event Log
        chrome://net-export/

        ## Http/2
        - https://en.wikipedia.org/wiki/SPDY?_gl=1*12wtoyt*_gcl_au*MTUwMzUyMDc0NC4xNzAxOTgwODgx
        - https://www.ssl.com/pt/artigo/uma-introdu%C3%A7%C3%A3o-ao-http2/
~~~

~~~
    ## server.js - https server

    import fs from "fs"
    import https from "https"
    import express from "express"

    const app = express()

    app.get("/", (req, res)=>{
        res.send("Olá, via Express")
    })

    //http server
    app.listen(3001, ()=>{
        console.log(`Servidor rodando em http://localhost:${3001}`);
    }) 

    const server = https.createServer({
        key: fs.readFileSync("privatekey.pem", "utf-8"),
        cert: fs.readFileSync("certificate.pem", "utf-8")
    }, app)

    //https server
    const PORT = process.env.PORT || 3002
    server.listen(PORT, ()=>{
        console.log(`Servidor rodando em https://localhost:${PORT}`);
    })
~~~

~~~
    ## server.js - http2 server

    import fs from "fs"
    import spdy from "spdy"
    import express from "express"

    const app = express()

    app.get("/", (req, res)=>{
        res.send("Olá, via Express")
    })

    //http server
    app.listen(3001, ()=>{
        console.log(`Servidor rodando em http://localhost:${3001}`);
    }) 

    const server = spdy.createServer({
        key: fs.readFileSync("privatekey.pem", "utf-8"),
        cert: fs.readFileSync("certificate.pem", "utf-8")
    }, app)

    //http2 server
    const PORT = process.env.PORT || 3002
    server.listen(PORT, ()=>{
        console.log(`Servidor rodando em https://localhost:${PORT}`);
    })
~~~

### Node.js - Testing with JEST <a id="jest"></a>

~~~
    # Automated Tests
    ## Unit Tests
    ## Integration Tests

    ## JEST

    - 1. Jest Installation 
        npm install --save-dev jest  


    - 2. Jest Configuration
    - jest.config.json: 
    ~~~JavaScript
    {
        "testEnvironment" : "node",
        "testMatch" : ["**/__tests__/**/*.js?(x)", "**/?(*.)+(spec|test).js?(x)"],
        "transform": {} 
    }
    ~~~

    ----OR-----

    - jest.config.js: 
    ~~~JavaScript
    module.exports = {
        testEnvironment: "node", 
        testMatch: ["**/__tests__/**/*.js?(x)", "**/?(*.)+(spec|test).js?(x)"]
    }
    ~~~

    - Test script in package.json:
    ~~~JSON
    "scripts": {
    "test": "node --experimental-vm-modules node_modules/jest/bin/jest.js --coverage"
    }
    ~~~

    - 3. Create the "test" folder and the mode.spec.js file

    - 4. Write the first test
    ~~~JavaScript

    /**
    *  Jest Functions:
    * - describe   : Test block (test Suites)
    * - it or test : Declare a single unit test (test cases)
    * - expect     : Validate results (result assertion) 
    */

        describe("Example Tests", () => {
            test("given 1 and 2, the expected result is 3", () => {
                expect(1 + 2).toEqual(3);
        });
        });
    ~~~

    - 5. Server Routes Testing 
        npm i --save-dev supertest

    - 6. Testing 
        npm test
~~~

~~~
    //server.js

    import app from "./src/app.js"

    const PORT = process.env.PORT || 3000
    app.listen(PORT, ()=>{
        console.log(`Server rodando em http://localhost:${PORT}`);
})
~~~

~~~
    //server.js

    import app from "./src/app.js"

    const PORT = process.env.PORT || 3000
    app.listen(PORT, ()=>{
        console.log(`Server rodando em http://localhost:${PORT}`);
})
~~~

~~~
    //jest.config.json

    {
    "testEnvironment" : "node",
    "testMatch" : ["**/__tests__/**/*.js?(x)", "**/?(*.)+(spec|test).js?(x)"], 
    "transform": {}
    }
~~~

~~~
    //src/Calculadora.js
    
    class Calculadora{

    soma(a, b){
        return a + b
    }

    sub(a, b){
        return a - b
    }

    div(a, b){
        if(b === 0){
            throw new Error("Divisao por zero")
        }
        return a / b
    }
    }

    export default Calculadora
~~~

~~~
    //src/Textos.js
    
    class Textos{

    concatenar(stringA, stringB){
        return stringA + stringB
    }

    }

    export default Textos
~~~

~~~
    //src/App.js
    
    import express from "express"

    const app = express()
    app.use(express.json())

    app.get("/user", (req, res)=>{
        res.status(200).json({msn:"Ola"})
    })

    app.post("/user", (req, res)=>{
        res.status(201).json({id: req.body.id, nome: req.body.nome})
    })

    app.delete("/user", (req, res)=>{
        res.status(200).json({msn:"User deletado com sucesso"})
    })

    app.put("/user", (req, res)=>{
        res.status(200).json({id: req.body.id, nome: req.body.nome})
    })

    export default app
~~~

~~~
    //test/Calculadora.spec.js
    
    import Calculadora from "../src/Calculadora.js"

    describe("Testes Calculadora.js", ()=>{
    it("Funcao soma(a, b) - dado a = 1, b = 2, o resultado esperado eh 3", ()=>{
        let calc = new Calculadora()
        let resul = calc.soma(1, 2)
        expect(resul).toEqual(3)
        expect(typeof(resul)).toEqual("number")
    })

    test("Funcao sub(a, b) - dado a = 1, b = 2, o resultado esperado eh -1", ()=>{
        let calc = new Calculadora()
        expect(calc.sub(1, 2)).toEqual(-1)
    })

    test("Funcao div(a, b) - dado a = 3 e b= 2, o resultado esperado eh 1.5", ()=>{
        let calc = new Calculadora()
        expect(calc.div(3, 2)).toBe(1.5)
    })

    test("Funcao div(a, b) - dado a = 3 e b= 0,  é esperado que lance o Erro 'Divisão por Zero'", ()=>{
        let calc = new Calculadora()
        expect(()=>{
            calc.div(3, 0)
        }).toThrow()
    })

    })  
~~~

~~~
   //test/Textos.spec.js
    
    import Textos from "../src/Textos.Js" 

    describe("Textos.js", ()=>{
    test("Funcao Concatenar(a, b), dado a='AB' e b= 'BC', o resultado esperado é 'ABBC'", ()=>{
        let text = new Textos()
        expect(text.concatenar("AB", "BC")).toBe("ABBC")
    })
    })
~~~

~~~
   //test/Textos.spec.js
    
    import supertest from "supertest"
    import app from "../src/app.js"

    const request = supertest(app)

    describe("app.js", ()=>{
    test("Deveria retornar Ola e Status 200", async ()=>{
        let res = await request.get("/user")

        
        expect(res.statusCode).toEqual(200)
        expect(res.body).toHaveProperty("msn")
        expect(res.body.msn).toEqual("Ola")
    })

    test("Deveria retornar os dados id e nome enviados na requisicao e Status 201", async ()=>{
        let res = await request.post("/user").send({"id": 23, "nome": "Steve Jobs"})
        expect(res.statusCode).toEqual(201)
        expect(res.body).toHaveProperty("id")
        expect(res.body).toHaveProperty("nome")
        expect(res.body.id).toEqual(23)
        expect(res.body.nome).toEqual("Steve Jobs")
    })

    test("Deveria retornar 'User deletado com sucesso' e Status 200", async ()=>{
        let res = await request.delete("/user")
        expect(res.statusCode).toEqual(200)
        expect(res.body).toHaveProperty("msn")
        expect(res.body.msn).toEqual("User deletado com sucesso")
    })

    test("Deveria retornar os dados id e nome enviados na requisicao e Status 201", async ()=>{
        let res = await request.put("/user").send({"id": 23, "nome": "Steve Jobs"})
        expect(res.statusCode).toEqual(200)
        expect(res.body).toHaveProperty("id")
        expect(res.body).toHaveProperty("nome")
        expect(res.body.id).toEqual(23)
        expect(res.body.nome).toEqual("Steve Jobs")
    })
    })
~~~

### Node.js - Connecting with DB PostgreSQL <a id="postgresql"></a>

~~~
const path = require("path")
const {Pool} = require("pg")
const env = require("dotenv")

// Configures environment variables using the .env file located at the specified path.
env.config({
    overide: true,
    path: path.join(__dirname, "conexao.env")
})

// Defines an object (dadosConexao) with PostgreSQL connection parameters taken from environment variables.
const dadosConexao = {
    user: process.env.USER,
    host: process.env.HOST,
    database: process.env.DATABASE,
    password: process.env.PASSWORD,
    port: process.env.PORT
}

// Creates a PostgreSQL client pool using the previously defined connection parameters.
const pool = new Pool(dadosConexao)

// Inserts a new row into the corretor table and returns the inserted data.
async function salvarCorretor(id, nome, licenca, telefone){
    const client =  await pool.connect()

    try {
        const text = `insert into corretor values($1, $2, $3, $4) returning *`
        const values = [id, nome, licenca, telefone]
        const rows = await client.query(text, values)

        console.log(rows.rows)
        
    } catch (error) {
       console.log(error)
    } finally {
        client.release()
    }
}

salvarCorretor(8, 'Ivan Borchardt', 'LHC334', '479977887')

// Deletes a row from the corretor table based on the provided ID and returns the deleted data.
async function deletarCorretor(id){
    const client =  await pool.connect()

    try {

        const text = `delete from corretor where codcorr = $1 returning *`
        const values = [id]
        const rows = await client.query(text, values)

        console.log(rows.rows)
        
    } catch (error) {
       console.log(error)
    } finally {
        client.release()
    }
}

deletarCorretor(6)

// Updates the data of an existing row in the corretor table and returns the updated data.
async function alterarCorretor(id, nome, licenca, telefone){
    const client =  await pool.connect()

    try {

        const text = `update corretor set nome = $2, licenca = $3, telefone = $4 where codcorr = $1 returning *`
        const values = [id, nome, licenca, telefone]
        const rows = await client.query(text, values)

        console.log(rows.rows)
        
    } catch (error) {
       console.log(error)
    } finally {
        client.release()
    }
}

alterarCorretor(8, 'Ivan J. Borchardt', 'LHC000', '47000000')

// Retrieves all rows from the corretor_sem_telefone view and logs the result.
async function buscarCorretores(){
    const client =  await pool.connect()

    try {

        const text = `select * from corretor_sem_telefone`
        const rows = await client.query(text)

        console.log(rows.rows)
        
    } catch (error) {
       console.log(error)
    } finally {
        client.release()
    }
}

buscarCorretores()

// Retrieves a specific row from the corretor table based on the provided ID and logs the result.
async function buscarCorretoresPorId(id){
    const client =  await pool.connect()

    try {

        const text = `select * from corretor where codcorr = $1`
        const values = [id]
        const rows = await client.query(text, values)

        console.log(rows.rows)
        
    } catch (error) {
       console.log(error)
    } finally {
        client.release()
    }
}

buscarCorretoresPorId(5)
~~~