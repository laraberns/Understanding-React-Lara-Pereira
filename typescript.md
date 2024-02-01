![typescript badge](./assets/typescript.png)
 
# TypeScript

- [TS - First TS File](#firstts)

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

~~~
