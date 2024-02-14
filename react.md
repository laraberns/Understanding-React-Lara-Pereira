![react badge](./assets/react.png)

- [React - Introduction](#intro)
- [React - First Project](#firstproject)
- [React - Router](#router)

# React - Introduction <a id="intro"></a>

- It is a JavaScript library for creating interfaces.
- Used to build Single Page Applications (SPAs).
- Based on components.
- Uses JSX to render HTML.
- Virtual DOM concept.

## Angular vs. React

| **Angular** | **React** |
|:-----------:|:---------:|
| Google      | Facebook  |
| Structural Framework | Library |
| MVC         | ---       |
| Strict Structure | No Structure |
| Larger components | More focused on Components |
| More specific code | More focus on reusability |
| Steeper Learning Curve | Short Learning Curve |
| More robust applications | Recommended for intense dynamic content |
| TypeScript  | JavaScript |
| Uses Dependency Injection | Does not use dependency injection |
| Two-Way Data Binding | One-Way Data Binding |

### Companies

| **Angular** | **React**  |
|:-----------:|:----------:|
| Gmail       | Instagram  |
| Microsoft   | Netflix    |
| Upwork      | Dropbox    |
| Sony        | Uber       |
| Forbes      | Airbnb     |
| PayPal      | Yahoo      |
| GoPro       | Asana      |
| AWS         | Intercom   |

### Glossary
- [React Glossary](https://pt-br.legacy.reactjs.org/docs/glossary.html)

## React Installation

React can be installed in various ways, but currently, the preferred choice is create-react-app.

It's a script that can be executed through npm, creating the basic structure for a React project.

**You can use the following commands:**

```bash
npx create-react-app helloworld
cd helloworld
npm start
```

## JSX

JSX is the primary way to write HTML with React.

JSX is like HTML but within JavaScript code. It allows various actions, such as printing data from variables in our templates. It's also possible to execute JavaScript code, like an "if" statement.

You can write JSX in the App.js file of React or in any component. Here's an example of JSX.

![JSX Example](./assets/jsx.png)

Note that it's very similar to HTML, but we need to avoid some words like `class`, which belongs to JavaScript, so we use `className`.

We can interpolate variables by enclosing them between curly braces `{}`. It's also possible to insert values into tag attributes, just like in HTML.

Find more at: [Introducing JSX](https://legacy.reactjs.org/docs/introducing-jsx.html)

## Components

Components are part of the React architecture. In an application, there can be various components, representing smaller parts of the site in smaller proportions, for example: a navigation bar, product card, or page title. All these cases can be divided into components.

One of the great advantages of components is that they can be reused in various places within the application.

**Example of a Component**

![Component Example](./assets/componente.png)

Usually, components are stored in the **components** folder. We need to create a function and export it.

Note that here we also use JSX, which is returned within parentheses since it has more than one line of code.

To use this component, we need to import it into a file. See the example of importation.

**Example of Importation:**

![Import Example](./assets/importacao.png)

We use the component like a tag, with the syntax `<Frase />`. Note that there is also the closing tag.

The name of the component is reflected by what it was imported as, as seen in the first line of the code.

## PROPS

Props are the data that we pass from the parent component to the child component.

Most of the time, we don't modify this data, meaning we only use it.

It is an extremely used feature in React.

![Props Example](./assets/props.png)

Here, the `SayMyName` component accepts the props, and within it, we use the prop called `nome`. Note that we need to declare it in the function's creation.

Now, see how to pass props to the component that accepts them.

![Passing Props](./assets/passandoProps.png)

Here, we reuse the `SayMyName` component three times, passing a different name each time.

We saw two features being used:
- Passing props;
- Reusing components;

## Adding CSS

To add CSS to our application, we have access to a feature called CSS Modules.

Simply create a file with the same name as the component where you want to add styles, ending with **module.css**. So if we have a component called `Frase.js`, let's create the file `Frase.module.css`.

![Adding CSS](./assets/css.png)

In the component, we import our CSS file and access the classes that were defined in it by inserting them into the elements of our component. This is the final implementation.

![Importing CSS in Component](./assets/importandoCSS.png)

We import the CSS with the name `styles` (which is a commonly used convention).

We access the classes defined in the CSS as properties of an object.

Now our component has CSS!

## Fragments

Whenever we define a component, we need to return only one element.

Fragments solve this problem, simplifying our HTML.

We can then return a kind of special tag, which allows a component to return two or more elements.

**See the implementation:**

![Fragments Example](./assets/fragments.png)

Here, we return only one `<li>` with a fragment that has the following syntax: `<> ... </>`. In other words, we open a fragment tag and then need to close it.

## Prop Types

We can define the type of a prop and also provide default values for it.

This makes our program much more solid, limiting what it accepts for better functioning.

**See the example:**

![Prop Types](./assets/tipoDeProps.png)

To define the type, we need to import `prop-types`.

And then apply the types to the properties we want to define.

To set a default value, it is not necessary to import anything, but we need to create the `defaultProps` property and insert the default value for the props we need. This ensures that if no value is passed, the default values are displayed instead of an empty value, which can be interesting in various cases.

## Events

React events are fundamental features for handling user data submissions, such as form submissions.

So, for each action, we have an event (clicks, keystrokes, forms, etc.).

**See an example:**

![Events Example](./assets/eventos.png)

The submit event triggers a method, i.e., a function, where we can execute code based on the logic of our application.

## Events with Props 

- You can pass a reference to a method through Props so that it is possible for a child component to activate its ancestor's method;
- These methods are accessed through an Event;
- The syntax is the same as a data prop: props.meuEvento.

## Router 

~~~
>> npm install react-router-dom
~~~

## React Icons

https://react-icons.github.io/react-icons/

~~~
>> npm install react-icons --save
~~~

## Bootstrap with React

1. Install
~~~
>> npm install bootstrap
~~~

2. Import on index.js

import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle';

# React - First Project <a id="firstproject"></a>

```bash
npx create-react-app helloworld
cd helloworld
npm start
```

## Creating components and props

App.js
~~~
    import './App.css';
    import Card from './components/001ComponentesBasicosProps/Card';
    import Pessoa from './components/002PropsCSS/Pessoa';
    import ListaCarros from './components/003FragmentsPropTypes/ListaCarros';
    import FormUsuario from './components/004EventosUseState/FormUsuario';
    import FormCliente from './components/004EventosUseState/FormCliente';
    import FormClienteUseState from './components/004EventosUseState/FormClienteUseState';
    import Botao from './components/004EventosUseState/Botao';
    import RenderCond from './components/005RenderizacaoCondicional/RenderCond';
    import IfInline from './components/005RenderizacaoCondicional/IfInline';
    import IfInlineTernario from './components/005RenderizacaoCondicional/IfInlineTernario';
    import RenderNull from './components/005RenderizacaoCondicional/RenderNull';
    import RenderListas from './components/006RenderizacaoListas/RenderListas';
    import RenderListas2 from './components/006RenderizacaoListas/RenderListas2';
    import RenderListas3 from './components/006RenderizacaoListas/RenderListas3';
    import ComponentePai from './components/007ElevandoState/ComponentePai';
    import Icons from './components/008Icons/Icons';


    function App() {

    function soma(a, b){
        return a + b
    }

    function deletarUsuario(){
        console.log("Usuario deletado com sucesso!!!");
    }

    const nome = "Ivan"
    return (
        <div className="App">
            <p className="vermelho">Olá {nome}, Este é seu primeiro REACT!</p>
            <p>A soma de A e B é: {soma(2, 5)}</p>
            <p>Teste</p>
            <FormClienteUseState/>
            <FormCliente/>

            <FormUsuario/>
            <Botao event={deletarUsuario} text="Deletar"/>
            <Card/>
            <Pessoa nome="Joselito" 
                    idade="34"
                    cpf="004.005.009-23" 
                    foto="https://github.com/Ivan-J-Borchardt/imagens/blob/master/joinha.jpg?raw=true"       
            />
            <Pessoa nome="Joana" 
                    idade="23"
                    cpf="004.005.222.98" 
                    foto="https://github.com/Ivan-J-Borchardt/imagens/blob/master/toquinho.jpg?raw=true"       
            />

            <ListaCarros/>

            <RenderCond isLogado={true} nome={"João"}/>
            <IfInline isLogado={false} nome={"João"}/>
            <IfInlineTernario isLogado={true} nome={"João"}/>
            <RenderNull err={false} msn={"Deu Erro!!!"}/>

            <RenderListas/>
            <RenderListas2/>
            <RenderListas3/>

            <ComponentePai/>

            <Icons/>

        </div>
    );
    }

    export default App;
~~~

Folder components -> Card.js
~~~
import Mensagem from "./Mensagem"

function Card() {

    const fnUser = "Analista"
    
    return(
        <div>
            <img src="https://github.com/Ivan-J-Borchardt/imagens/blob/master/porfavor.jpg?raw=true" alt="img"/>    
            <p>Sr. Fulando de Tal</p>
            <Mensagem funcao={fnUser}/>    
        </div>
    )

}

export default Card
~~~

Folder components -> Mensagem.js
~~~
function Mensagem(props){

    return(
        <> {/* fragment */} 
            <p>Função do Usuário: {props.funcao}</p>
        </>
    )
}

export default Mensagem
~~~

CSS styles module -> Pessoa.module.css
~~~
.azul{
    color: blue; 
}
~~~

Folder components -> Pessoa.js
~~~
import styles from './Pessoa.module.css'

function Pessoa({nome, idade, cpf, foto}) {

    return(
        <div className={styles.azul}>
            <img src={foto} alt={nome}/>
            <h2>Nome: {nome}</h2>
            <p>Idade: {idade}</p>
            <p>CPF: {cpf}</p>        
        </div>
    )
}

export default Pessoa
~~~

Folder components -> ListaCarros.js
~~~
import ItemLista from "./ItemLista"

function ListaCarros() {
    return(
        <>
            <h1>Lista de Carros</h1>
            <ul>
                <ItemLista modelo="Ford Ka"  ano={2015} />
                <ItemLista modelo="EcoSport" marca="Ford" ano={2020} />
                <ItemLista modelo="Tiguan" marca="Volkswagen" ano={2020} />
                <ItemLista modelo="Fusca" marca="Volkswagen"  />
            </ul>
        </>
    )
}

export default ListaCarros
~~~

Folder components -> ItemLista.js
~~~
import PropTypes from 'prop-types'

    function ItemLista({marca, modelo, ano}) {
        return(
            <li>{marca} - {modelo} - {ano}</li>
        )
    }

    ItemLista.propTypes = {
        marca : PropTypes.string.isRequired, 
        modelo: PropTypes.string,
        ano: PropTypes.number
    }

    ItemLista.defaultProps = {
        marca: 'Inserir Marca', 
        ano: 0
    }

export default ItemLista
~~~

Folder components -> FormUsuario.js
~~~
function FormUsuario() {

    function salvar() {
        console.log("Salvando...:", document.getElementById("idNome").value);
    }

    return (
        <>
            <div className="mb-3">
                <label htmlFor="idNome" className="form-label">Nome:</label>
                <input type="text" id="idNome" className="form-control" />
            </div>
            <button onClick={salvar} >Salvar</button>
        </>
    )
}

export default FormUsuario
~~~

Folder components -> FormCliente.js
~~~
function FormCliente() {

    function salvarCliente(event) {
        event.preventDefault()
        console.log("Salvando Cliente...", document.getElementById("idNomeCli").value);
    }

    return(
        <div>
            <h1>Cadastro de Cliente</h1>
            <form onSubmit={salvarCliente}>
                <div>
                    <input type="text" id="idNomeCli" placeholder="Nome do Cliente"/>
                </div>
                <div>
                    <input type="submit" value="Salvar"/>
                </div>

            </form>
        </div>
    )
}

export default FormCliente
~~~

Folder components -> FormClienteUseState.js
~~~
import {useState} from 'react'
import Botao from './Botao';

function FormClienteUseState() {

    function salvarCliente(event) {
        event.preventDefault()
        console.log("Nome do Cliente capturado pelo Hook useState:..", nomeCli);

    }

    const [nomeCli, setNomeCli] = useState("Tim Berners-Lee")


    return(
        <div>
            <h1>Cadastro de Cliente usando UseState</h1>
            <form>
                <div>
                    <input 
                        type="text" 
                        id="idNomeCli" 
                        placeholder="Nome do Cliente"
                        value={nomeCli}
                        onChange={function(event){ setNomeCli(event.target.value)}}
                    />
                </div>
                <div>
                    <Botao event={salvarCliente} text="Enviar"/>
                </div>

            </form>
        </div>
    )
    }

export default FormClienteUseState
~~~

Folder components -> Botao.js
~~~
function Botao(props) {
    return(<button onClick={props.event}>{props.text}</button>)
}

export default Botao
~~~

Folder components --> RenderCond.js
~~~
    import Login from "./Login"

    function RenderCond(props) {

        const isLogado = props.isLogado

        if (isLogado) {
            return (
                <div>
                    <h2>Renderização Condicional 1</h2>
                    <h2>Bem vindo {props.nome}</h2>
                </div>
            )
        } else {
            return (
                <div>
                    <h2>Exemplo 1 Renderização Condicional</h2>
                    <Login />
                </div>
            )
        }
    }

    export default RenderCond
~~~

Folder components ---> Login.js
~~~
    import {useState} from "react"
    import Botao from "../004EventosUseState/Botao"

    function Login(params) {

        function logar() {
            console.log(`Loggin ${userName} - ${password}`);
        }

        const [userName, setUserName] = useState()
        const [password, setPassword] = useState()


        return(
            <form>
                <label htmlFor="idUser">User</label><br/>
                <input type="Text" 
                    id="idUser"
                    onChange={event=>setUserName(event.target.value)}
                />
                <br/><br/>
                <label htmlFor="idPass">Senha</label><br/>
                <input type="password" 
                    id="idPass"
                    onChange={event=>setPassword(event.target.value)}
                />
                <br/><br/>
                <Botao event={logar} text="Login"/>

            </form>
        )
    }

    export default Login
~~~

Folder components --> IfInline.js
~~~
    import Login from "./Login"

    function IfInline(props) {

        const isLogado = props.isLogado

        return (
            <div>
                <h2>Exemplo 2 Renderização Condicional</h2>
                {isLogado && (
                    <div>
                        <h2>Bem vindo {props.nome}</h2>
                    </div>)
                }
                {!isLogado && (
                    <div>
                        <Login />
                    </div>)
                }
            </div>

        )
    }

    export default IfInline
~~~

Folder components --> IfInlineTernario.js
~~~
    import Login from "./Login"

    function IfInlineTernario(props) {

        const isLogado = props.isLogado

        return (
            <div>
                <h2>Exemplo 3 Renderização Condicional</h2>
                {isLogado ? (
                    <div>
                        <h2>Bem vindo {props.nome}</h2>
                    </div>
                ):(
                    <div>
                        <Login />
                    </div>
                )}
            </div>

        )
    }

    export default IfInlineTernario
~~~

Folder components --> RenderNull.js
~~~
    function RenderNull(props) {

        if (!props.err) {
            return null
        }

        return(
            <div>
                <p>Erro: {props.msn} </p>
            </div>
        )
    }

    export default RenderNull
~~~

Folder components --> RenderListas.js
~~~
    function RenderListas() {

        const navegadores = ['IE', 'Chrome', 'Firefox', 'Opera', 'Edge', 'Safari']

        return(
            <div>
                <h2>Exemplo Render Lista 1 - UL</h2>
                <ul>
                    {navegadores.map((navegador, index)=>{return(
                        <li key={index}>{navegador}</li>
                    )})}
                </ul>
            </div>
        )
    }

    export default RenderListas
~~~

Folder components --> RenderListas2.js
~~~
    import { useState } from "react"
    import Botao from "../004EventosUseState/Botao"

    function RenderListas2(params) {

        const navegadores = ['IE', 'Chrome', 'Firefox', 'Opera', 'Netscape']
        //const navegadores = []

        const [navegador, setNavegador] = useState(navegadores[0])

        function imprimirNavegador() {
            console.log(`Navegador: ${navegador}`);
        }

        return(
            <div>
                <h1>Renderização Lista - Select</h1>
                <select name="nmSelect" id="idSelect" onChange={(event) => setNavegador(event.target.value)}>
                    {navegadores.map((navegador,index)=> {return(
                        <option key={index}>{navegador}</option>
                    )})}
                </select>
                <Botao event={imprimirNavegador} text="Capturar"/>
            </div>
        )
    }

    export default RenderListas2
~~~

Folder components --> RenderListas3.js
~~~
    import { useState } from "react"
    import Botao from "../004EventosUseState/Botao"

    function RenderListas3(params) {

        //const navegadores = ['IE', 'Chrome', 'Firefox', 'Opera', 'Netscape']
        const navegadores = []

        const [navegador, setNavegador] = useState(navegadores[0])

        function imprimirNavegador() {
            console.log(`Navegador: ${navegador}`);
        }


        return (
            <div>
                <h1>Renderização Lista - Select</h1>
                <select name="nmSelect" id="idSelect" onChange={(event) => setNavegador(event.target.value)}>
                    {navegadores.length > 0 ? (
                        navegadores.map((navegador, index) => {
                            return (
                                <option key={index}>{navegador}</option>
                            )
                        })
                    ) : (
                        <option key={0}>Falha ao Carregar Navegadores</option>
                    )}


                </select>
                <Botao event={imprimirNavegador} text="Capturar" />
            </div>
        )

    }

    export default RenderListas3
~~~

Folder components --> ComponentePai.js
~~~
    import {useState} from "react" 
    import ComponenteFilho1 from "./ComponenteFilho1"
    import ComponenteFilho2 from "./ComponenteFilho2"

    function ComponentePai(params) {

        const [nome, setNome] = useState()
        return(
            <>
                <h1>Elevando o State</h1>
                <ComponenteFilho1 setNome={setNome} nome={nome} />
                <ComponenteFilho2 nome={nome}/>
                <p>{nome}</p>
            </>
        )
    }

    export default ComponentePai
~~~

Folder components --> ComponenteFilho1.js
~~~
 function ComponenteFilho1({setNome, nome}) {

    return(
        <div>
            <label htmlFor="idNomeP">Nome:</label>
            <input type="text"
                   id="idNomeP"
                   value={nome}
                   onChange={event=>setNome(event.target.value)}
            />
        </div>
    )
}

export default ComponenteFilho1
~~~

Folder components --> ComponenteFilho2.js
~~~
    function ComponenteFilho2(props) {
        return <p>Olá {props.nome}, tudo bem com vc? </p>
    }

    export default ComponenteFilho2
~~~

Folder components --> Icons.js
~~~
    import { BsAirplaneEnginesFill } from "react-icons/bs";
    import { DiApple } from "react-icons/di";
    import styles from "./Icons.module.css"

    function Icons() {
        return (

            <ul className={styles.socialMedia}>
                <li><BsAirplaneEnginesFill /></li>
                <li><DiApple /></li>
            </ul>
        )
    }

    export default Icons
~~~

Folder components --> Icons.module.css
~~~
    .socialMedia {
        display: flex;
        justify-content: center;
        align-items: center;
        list-style: none;
    }

    .socialMedia li{
        margin: 0 1em;
    }

    .socialMedia svg{
        font-size: 2em;
        color:blue;
        cursor: pointer;
    }
~~~

# React - Router <a id="router"></a>

App.js
~~~
    import {BrowserRouter as Router, Routes, Route, Link, Navigate} from 'react-router-dom'
    import './App.css';
    import Home from './pages/Home';
    import Empresa from './pages/Empresa';
    import Contato from './pages/Contato';
    import Info from './pages/Info';
    import Navebar from './components/Navebar';

    function App() {
    return (
        <Router>
        <Navebar/>
        <Routes>
            <Route path='/' element={<Home/>}/>
            <Route path='/empresa' element={<Empresa/>}/>
            <Route path='/contato' element={<Contato/>}/>
            <Route path='/info' element={<Navigate to="/"/>}/>
        </Routes>
        </Router>
    );
    }

    export default App;
~~~

Pages/Contato.js
~~~
    import { useNavigate } from "react-router-dom";

    function Contato() {

        const navigate = useNavigate()
        function voltarHome(){
            navigate("/")
        }

        return(
            <div>
                <h1>Contato</h1>
                <p>Formulário de Contato</p>
                <button onClick={voltarHome}>Home</button>
            </div>
        )
    }

    export default Contato
~~~

Pages/Empresa.js
~~~
    import { Link } from "react-router-dom"
    function Empresa() {
        return(
            <div>
                <h1>Empresa</h1>
                <p>Encontre aqui todas as informações <Link to="/info">sobre</Link> nossa empresa</p>
            </div>
        )
    }

    export default Empresa
~~~

Pages/Home.js
~~~
    function Home() {
        return(
            <div>
                <h1>Home</h1>
                <p>Página Principal</p>
            </div>
        )
    }

    export default Home
~~~

Pages/Info.js
~~~
    function Info() {
        return(
            <div>
                <h1>Infos</h1>
                <p>Conteúdo da Página</p>
            </div>
        )
    }

    export default Info
~~~

Components/Navebar.js
~~~
    import { Link } from "react-router-dom"
    function Navebar() {
        return (
            <ul>
                <li><Link to="/">Home</Link></li>
                <li><Link to="/empresa">Empresa</Link></li>
                <li><Link to="/contato">Contato</Link></li>
            </ul>
        )
    }

    export default Navebar
~~~