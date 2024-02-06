![typescript badge](./assets/typescript.png)
 
# TypeScript

- [TS - First TS File](#firstts)
- [TS - POO - Class and Objects](#pooclass)
- [TS - POO - Encapsulation](#pooencapsulation)
- [TS - POO - Static Atributes and Methods](#poostatic)
- [TS - POO - Heritage](#pooheritage)
- [TS - POO - Polymorphism](#poopolymorphism)
- [TS - POO - Abstract Class](#pooabstract)
- [TS - POO - Interfaces](#poointerfaces)

## What is TypeScript 

- TypeScript is a **superset** for the JavaScript language.

- It adds features to JavaScript, such as **static typing**.
- It is the default language for Angular and can be used with various other frameworks like Express, React, and Vue.js.
- TypeScript needs to be compiled/transpiled into **JavaScript**, meaning we don't execute TypeScript directly.
- It is maintained by **Microsoft**.

## Advantages of using TypeScript 

- Adds **reliability** to the program (due to typing).
- Provides new features to JavaScript, such as **Interfaces**.
- With TS, we can **check errors before code execution**, i.e., during development.
- Makes JavaScript **more explicit**, reducing the number of bugs.
- Optimizes development time, as **less time is spent dealing with bugs**.

## Installing TypeScript 


- To install TypeScript, we will use **npm**.
- The package/dependency name is **typescript**.
- We will add it globally with the **-g** flag.
- After installation, we can **execute/compile** TypeScript using the **tsc** command.

        $ npm i typescript -g 
        
        $ tsc -v 

        $ tsc --init 

        $ tsc -w 


### TS - First TS File <a id="firstts"></a>
~~~
// index.ts
    console.log("Olá TypeScript!!!"); // Olá TypeScript!!!

    //Typing
    let idade: number 
    var nome: string = "Ada Lovelace"
    const isAluno: boolean = true 

    idade = 23
    //idade = "23" - ERROR

    console.log(nome.toUpperCase()); // ADA LOVELACE
    console.log(typeof(idade)); //number

    //Inference
    let idadeAluno = 10 
    console.log(typeof(idadeAluno)); //number

    //idadeAluno = "XYZ" - ERROR

    //Objects
    //Array 
    const idades: number[] = [10, 14, 20, 5, 20]

    console.log(idades); // [10, 14, 20, 5, 20]
    console.log(typeof(idades)); // object
    console.log(idades.length) // 5

    //Tuple
    let usuario: [number, string, boolean, string[], number]
    usuario = [1, "Jaoa Pessoa", false, ["a","b", "c"], 23]

    //usuario.push(true) <-- Be careful this will work
    console.log(usuario); // [1, "Jaoa Pessoa", false, ["a","b", "c"], 23]

    //Object Literals
    let user: {id: number, nome: string, isPermitido: boolean}

    user = {
        id: 1,
        nome: "Joana",
        isPermitido: true
    }

    user.nome = "Joana Dark"

    console.log(user); //{id: 1, nome: "Joana Dark", isPermitido: true}

    //Any type - Avoid using it
    let varA : any
    varA = "Oi"
    varA = 1
    varA = true 
    varA = [1, 3, true]

    //Union Type 
    var id: string | number
    id = 200
    id = "200"

    //Type Alias 
    type userIdType = string | number 
    var userId: userIdType
    userId = "200"
    userId = 100

    //Literal Types
    let estadoUser : "autenticado" | null | "deslogado" | boolean 
    estadoUser = "autenticado"
    estadoUser = null 
    estadoUser = "deslogado"
    estadoUser = false
    //estadoUser = "teste" <--- Error

    //Enum <-- Colection
    enum Tamanho {
        P = "Pequeno", 
        M = "Médio", 
        G = "Grande"
    }

    const camisa = {
        desc: "Camisa basica preta", 
        size: Tamanho.P
    }

    console.log(camisa.size); //Pequeno

    enum Operacao {
        debitoCC = 5038, 
        creditoCC = 5039,
        debitoP = 6038,
        creditoP = 6039 
    }

    let op = 5039 // <-- API Database data

    if (op == Operacao.debitoCC){

    }else if(op = Operacao.creditoCC){

    } else if(op == Operacao.debitoP){

    }else if (op == Operacao.creditoP) {
        
    }

    //Interfaces 
    interface ParametrosFuncoesMatematicas{
        n1: number;
        n2: number; 
    }

    let teste : ParametrosFuncoesMatematicas; 
    teste = {n1: 3, n2: 7} --> same
    let op1: {n1: number, n2: number} =  {n1: 3, n2: 4} --> same
    let op2: ParametrosFuncoesMatematicas =  {n1: 3, n2: 4} --> same

    function somaNum(nums:ParametrosFuncoesMatematicas):number {
        return nums.n1 + nums.n2
    }

    let res: number = somaNum(op1) --> same
    let res1: number = somaNum(op2) --> same
    let res2: number = somaNum({n1: 3, n2: 5}) --> same

    //Functions
    //Params types
    function soma(num1: number, num2: number) {
        return num1 + num2;
    }

    //Return types
    function digaOla(nome: string): string{
        return "olá " + nome;
    }

    function testeRet():ParametrosFuncoesMatematicas{
        return {n1:0, n2:0}
    }

    //No return = void
    function gravarLog(msn: string): void{
        console.log(msn);
    }

    //Optional params
    function saudar(nome: string, saudacao?: string):void{
        if (saudacao) {
            console.log(`Olá ${saudacao} ${nome}`);
        } else {
            console.log(`Olá ${nome}`); 
        }
    }

    saudar("Fulano", "Sr.") // Olá Sr. Fulano
    saudar("Joana") / Olá Joana

    //Narrowing 
    function facaAlgo(info: number | boolean): void{

        if (typeof info === "number") {
            console.log("O dado é numérico");
        } else {
            console.log("O dado é lógico");
        }
    }

    //Generics 
    function exibirItensArray<T>(vetor: T[]){

        vetor.forEach(element => {
            console.log(element);
        });

    }

    var x1 = [0, 2, 4, 6]; 
    var x2 = ["a", "b", "c"];
    var x3 = [true, false, true]
    var x4 = [{ax1: "saasd", ax2:3434}, {ax1: "saasd", ax2:3434}, {ax1: "saasd", ax2:3434} ]

    exibirItensArray(x2); // a, b, c
    exibirItensArray(x4); // {ax1: "saasd", ax2:3434}, {ax1: "saasd", ax2:3434}, {ax1: "saasd", ax2:3434}

~~~

### TS - POO - Class and Objects <a id="pooclass"></a>
~~~

// index.ts

    //Class
    class Pessoa {
        
        //Atributes
        nome: string;
        idade?: number; 
        cpf?: string; 

        //Methods - Functions
        //Construtor 
        constructor(nome: string, idade?: number, cpf?: string){
            this.nome = nome; 
            this.idade = idade;
            this.cpf = cpf; 
        }

        //Worker Method
        mostrarNomeUsuario(tipoUser: string):void{
            console.log(`O Nome do Usuário é ${this.nome} tipo: ${tipoUser}`);
        }
    }

    let pessoa = new Pessoa("Joao", 23, "0004.0009.333-23")
    let pessoa2 = new Pessoa("Evandro", 21)

    console.log(pessoa.nome); //Joao

    pessoa.nome = "Joana"

    console.log(pessoa.nome); //Joana

    console.log(pessoa); //Pessoa {nome: "Joana", idade: 23, cpf: "0004.0009.333-23"}

    console.log(pessoa2.mostrarNomeUsuario("DBA")); //O Nome do Usuário é Evandro tipo: DBA
~~~

### TS - POO - Encapsulation <a id="pooencapsulation"></a>
~~~
// app.ts

    import { Cliente } from "./Cliente"
    import {ContaCorrente} from "./ContaCorrente"

    let cliente = new Cliente("William", "009.008.007-23", new ContaCorrente("203-0", 500.00, 200))

    console.log("Operação Depósito:" + cliente.getConta().deposito(300)); //000 - Op. Depósito realizado com sucesso!
~~~

~~~
// Cliente.ts

    import { ContaCorrente } from "./ContaCorrente"

    export class Cliente{

            private nome: string 
            private cpf: string
            private conta: ContaCorrente

            constructor (nome: string, cpf: string, conta: ContaCorrente){
                this.nome = nome
                this.cpf = cpf
                this.conta = conta
            }

            public getNome():string{
                return this.nome
            }

            public getCpf():string{
                return this.cpf
            }

            public getConta():ContaCorrente{
                return this.conta
            } 

            public setNome(nome:string){
                this.nome = nome
            }

            public setCpf(cpf:string){
                this.cpf = cpf
            }

            public setConta(conta:ContaCorrente){
                this.conta = conta
            }
        }
~~~

~~~
// ContaCorrente.ts

    export class ContaCorrente{
        //Access modificators => public, private, protected, readonly 
        private  numCC: string
        private  saldo: number = 0 
        private limite: number = 0
        private senha: number

        constructor(numCC: string, senha: number, saldo?:number, limite?:number){
            this.numCC = numCC
            this.senha = senha
            if (saldo) {
                if (saldo > 0) {
                    this.saldo = saldo
                }
            }
            
            if (limite) {
                if (limite > 0) {
                    this.limite = limite
                }
            }
        }

        //Getter 
        public getSaldo():number{
            return this.saldo
        }

        public getLimite():number{
            return this.limite
        }

        public getSenha():number{
            return this.senha
        }

        //Setter 
        public setLimite(limite:number):string{
            if (limite > (this.limite * 1.2)) {
                return "Novo limite acima de 20%, operação negada"
            }else if(limite < 0){
                return "Novo limite inferior a ZERO, operação negada"
            }else{
                this.limite = limite
                return "Novo limite " + this.limite
            }
        }

        public setSenha(senha:number):string{
            this.senha = senha
            return "000 - Nova senha cadastrada com sucesso!"
        }

        //Métodos Worker 
        public deposito(valorDeposito:number):string{
            if (valorDeposito > 0 ){
                this.saldo = this.saldo + valorDeposito
                return "000 - Op. Depósito realizado com sucesso!"
            }
            return "005 - Valor de depósito inválido"
        }

        public saque(valorSaque:number):string{
            if ((this.saldo + this.limite) >= valorSaque){
                this.saldo = this.saldo - valorSaque
                return "000 - Saque Efetuado com sucesso!"
            } else {
                return "006 - Saldo Insuficiente!"
            }
        }
    } 
~~~

### TS - POO - Static Atributes and Methods <a id="poostatic"></a>
~~~
// Calculadora.ts

    export class Calculadora {

        //Class atributes - Static
        static contadorCalculadora = 0;
        static PI = 3.14;

        //Class atributes - Private
        private id: number

        constructor(id: number) {
            this.id = id
            Calculadora.contadorCalculadora++
        }

        static areaCirculo(raio: number): number {
            let areaCirculo:number = Math.PI * raio * raio
            return areaCirculo
        }

        static areaRetangulo(baseRet: number, alturaRet:number):number{
            let areaRetangulo:number = baseRet * alturaRet
            return areaRetangulo
        }

        static areaTrianguloRetangulo(baseTri: number, alturaTri: number):number{
            let areaTrianguloRetangulo:number = (baseTri * alturaTri)/2
            return areaTrianguloRetangulo
        }

        static areaTrianguloEquilatero(lado:number):number{
            let areaTrianguloEquilatero:number = ((lado ** 2) *  Math.sqrt(3) )/4
            return areaTrianguloEquilatero
        }
    }

        /* Static and private methods are distinct concepts in object-oriented programming. Static methods belong to the class as a whole and can be invoked without creating instances, accessible directly through the class. They are typically used for operations related to the class without relying on specific instance states. On the other hand, private methods, marked with the private keyword, are only accessible within the class, preventing direct external access and manipulation. This enhances encapsulation, protecting the internal implementation of the class, and restricting access to and manipulation of attributes to internal methods. In summary, static methods are shared among all class instances and can be called without creating objects, while private methods are confined to the class's internal scope, ensuring data integrity and security.
        */
~~~

### TS - POO - Heritage <a id="pooheritage"></a>
~~~
// index.ts

    export class Carro{
        protected marca: string
        protected motor: string // Members marked as public are accessible from anywhere, whether within the class itself, in derived classes (inheritance), or from any external code.
        
        public isLigado: boolean // Members marked as protected are accessible within the class itself and also in derived classes (inheritance). However, they are not accessible from external code or instances of the class.

        constructor(marca: string, motor: string){
            this.marca =  marca
            this.motor = motor
            this.isLigado = false
        }

        public ligarMotor(): boolean{
            if (this.checkupPreStart()){
                this.isLigado = true
            }else{
                this.isLigado = false
            }
            return this.isLigado
        }

        private checkupPreStart():boolean{
            return true 
        }
    }

    export class Suv extends Carro {

        private volumePortaMalas: number

        constructor(volumePortaMalas: number, marca: string, motor: string){
            super(marca, motor)
            this.volumePortaMalas = volumePortaMalas
        }

        //Getters e Setters 
        public getVolumePortaMalas(): number{
            return this.volumePortaMalas
        }

        public getMarca(): string{
            return this.marca; 
        }

        public setMarca(marca:string): void{
            this.marca = marca
        }
    }

    var ecoSport = new Suv(23, 'Ford', '2.0')

    console.log(`Carro Ligado: ${ecoSport.ligarMotor()}`); //Carro Ligado: true
    console.log(`Marca: ${ecoSport.getMarca()}`); //Marca: Ford
    // console.log(`Marca: ${ecoSport.marca}`); //Error - 'marca' property in the base class is protected, allowing its access in derived classes, such as 'Suv'."
~~~

### TS - POO - Polymorphism <a id="poopolymorphism"></a>
~~~
// index.ts

    export class Carro{
        protected marca: string
        protected motor: string
        public isLigado: boolean

        constructor(marca: string, motor: string){
            this.marca =  marca
            this.motor = motor
            this.isLigado = false
        }

        // Worker
        public ligarMotor(): boolean{
            if (this.checkupPreStart()){
                this.isLigado = true
            }else{
                this.isLigado = false
            }
            return this.isLigado
        }

        private checkupPreStart():boolean{
            return true 
        }
    }

    export class Suv extends Carro {

        private volumePortaMalas: number
        private modoLuzCarro: "auto" | "cidade" | "alta" | "neblina" 
        private isLuzLigada: boolean 

        constructor(volumePortaMalas: number, marca: string, motor: string){
            super(marca, motor)
            this.volumePortaMalas = volumePortaMalas
            this.modoLuzCarro = "auto"
            this.isLuzLigada = false
        }

        // Getters and Setters 
        public getVolumePortaMalas(): number{
            return this.volumePortaMalas
        }
        
        public getMarca(): string{
            return this.marca; 
        }

        public setMarca(marca:string): void{
            this.marca = marca
        }

        // Worker 
        public ligarMotor(): boolean{
            this.ligarLuzes()
            this.isLigado = true
            return this.isLigado
            /*
            Note that the method Suv.ligarMotor() is different from the method Carro.ligarMotor(), but its signature is the same. This is an example of Method Overriding Polymorphism!
            */
        }

        private ligarLuzes(): boolean{
            if (this.modoLuzCarro === "auto") {
                this.isLuzLigada = true 
            }else{
                this.isLuzLigada = false
            }
            return this.isLuzLigada
        }
    }
~~~


### TS - POO - Abstract Class <a id="pooabstract"></a>
~~~
// index.ts

    // Abstract Class
    export abstract class Veiculo{
        constructor(protected marca: string, protected modelo: string){}

        abstract ligarMotor(): boolean
        abstract desligarMotor(): boolean

        public acinarAssitenteEstacionamento():boolean{
            return true 
        }
    }

    // Regular Class
    export class Carro extends Veiculo{

        protected motor: string
        public isLigado: boolean

        constructor(marca: string, motor: string, modelo: string){
            super(marca, modelo)
            this.motor = motor
            this.isLigado = false
        }

        //Worker
        public ligarMotor(): boolean{
            if (this.checkupPreStart()){
                this.isLigado = true
            }else{
                this.isLigado = false
            }
            return this.isLigado
        }

        public desligarMotor(): boolean {
            throw new Error("Method not implemented.")
        }

        private checkupPreStart():boolean{
            return true 
        }

    }

    export class Suv extends Carro {

        private volumePortaMalas: number
        private modoLuzCarro: "auto" | "cidade" | "alta" | "neblina" 
        private isLuzLigada: boolean 

        constructor(volumePortaMalas: number, marca: string, motor: string, modelo:string){
            super(marca, motor, modelo)
            this.volumePortaMalas = volumePortaMalas
            this.modoLuzCarro = "auto"
            this.isLuzLigada = false
        }

        public getVolumePortaMalas(): number{
            return this.volumePortaMalas
        }
        
        public getMarca(): string{
            return this.marca; 
        }

        public setMarca(marca:string): void{
            this.marca = marca
        }

        //Worker 
        public ligarMotor(): boolean{
            this.ligarLuzes()
            this.isLigado = true
            return this.isLigado
        }

        private ligarLuzes(): boolean{
            if (this.modoLuzCarro === "auto") {
                this.isLuzLigada = true 
            }else{
                this.isLuzLigada = false
            }
            return this.isLuzLigada
        }
    }
~~~

### TS - POO - Interfaces <a id="poointerfaces"></a>
~~~
// index.ts

    //Interfaces with Classes
    interface IVeiculo {
        marca: string;
        motor: string; 
        isLigado: boolean; 

        ligarMotor(): void;   
    }

    class Car implements IVeiculo {
        marca: string;
        motor: string;
        isLigado: boolean;
    
        constructor(marca: string, motor: string){
            this.marca = marca;
            this.motor = motor; 
            this.isLigado = false; 
        } 

        ligarMotor(): void {
            this.isLigado = true; 
        }  
    }

    // Heritage
    class Suv extends Car {
        volumePortaMalas: number;

        constructor(vol: number, marca: string, motor: string){
            super(marca, motor);
            this.volumePortaMalas = vol; 
        }
    }
~~~