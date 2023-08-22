# Anotações das Aulas - Entra 21

<a href="#bookmark"> Git e Github </a>

<a href="#bookmark2"> HTML </a>

<h2 id="bookmark"> 1. Git e GitHub </h2>

~~~
- Software para controle de versionamento de código;
- Existem dois tipos de Software de Controle de Versão (VCS): 
   - Centralizado
   - Distribuído (Ex: Git)
- Algumas das vantagens de utilizar VCS são: segurança e facilita no trabalho em equipe.
~~~

### Comandos do Git
- Verificar a versão do Git e se está instalado:
~~~
   - git --version
~~~

- Configurar usuário e e-mail cadastrado (para máquina toda):
~~~
   - git config --global user.email you@example.com
   - git config --global user.name "Your Name"
~~~
- Verificar as configurações:
~~~
   - git config user.name
   - git config user.email
~~~
- Iniciar repositório:
~~~
   - git init
~~~
- Verificar status:
~~~
   - git status 
~~~
- Adicionar arquivos na área de staged:
~~~
   - git add nome_arquivo
   - git add . 
~~~
- Commitar arquivos:
~~~
   - git commit -m "comentário"
~~~
- Mapear repositório remoto:
~~~
   - git remote add origin "http://...url do rep remoto..." 
~~~
- Enviar alterações para o rep. remoto:
~~~
   - git push -u origin master
   - git push 
~~~
- Atualizar rep. local de acordo com rep. remoto:
~~~
   - git pull
~~~
- Renomear branch:
~~~
   - git branch -M main 
~~~
- Clonar rep. remoto:
~~~
   - git clone "http://...url do rep remoto...
~~~
- Removendo arquivos:
~~~
   - git rm --> remove do repositório (<mark>DELETA</mark> arquivo)
   - git rm --cached <file> --> arquivo deixa de ser monitorado (untracked)
~~~
- Utilizar Add junto com Commit (stage e commita):
~~~
   - git commit -am "criando commit"
~~~
- Verificar alterações:
~~~
   - git log
   - git log --oneline --> forma mais resumida
~~~
- Para ignorar arquivos:
~~~
   - Crie o arquivo ".gitignore"
   - Arquivos dentro do ".gitignore" o Git ignora e não rastreia
~~~
- Verificar diferenças entre commits:
~~~
   - git diff <cod. do commit> <cod. do commit2>
~~~
- Descatar alterações antes de add:
~~~
   - git checkout <file>
~~~
   

<h2 id="bookmark2"> 2. HTML </h2>

~~~
- HTML é a linguagem de marcação padrão para criar páginas da Web.
- HTML significa Hyper Text Markup Language
- HTML é a linguagem de marcação padrão para criar páginas da Web
- HTML descreve a estrutura de uma página da Web
~~~

### Estrutura HTML
~~~
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
~~~

- Explicação da estrutura
~~~
- A <!DOCTYPE html>declaração define que este documento é um documento HTML5
- O <html> elemento é o elemento raiz de uma página HTML
- O <head> elemento contém metainformações sobre a página HTML
- O <title> elemento especifica um título para a página HTML (que é mostrado na barra de título - do navegador ou na guia da página)
- O <body> elemento define o corpo do documento e é um recipiente para todos os conteúdos - visíveis, como cabeçalhos, parágrafos, imagens, hiperlinks, tabelas, listas, etc.
- O <h1> elemento define um título grande
- O <p> elemento define um parágrafo
~~~

### Tags do HTML
- Títulos:
~~~
        <h1>Titulo h1</h1>
        <h2>Titulo h2</h2>
        <h3>Titulo h3</h3>
        <h4>Titulo h4</h4>
        <h5>Titulo h5</h5>
        <h6>Titulo h6</h6>
~~~

- Parágrafo:
~~~
        <p>isso é um parágrafo ....</p>
~~~

- Formatação de palavras:
~~~
        <p><b>Negrito</b></p>  
        <p><strong>Enfase</strong></p>
        <p><i>Italico</i></p>
        <p><em>Enfatizado</em></p>
        <p><mark>Grifado</mark> </p>
        <p><small>Texto pequeno</small></p>
        <p><big>Texto Grande</big></p>
        <p><s>texto taxado</s></p>
        <p><del>Taxado</del></p>
        <p>H<sub>2</sub>O</p>
        <p>x<sup>2</sup></p>
~~~

- Cotação e elementos de Citação:
~~~
        <p><q>Texto cotado</q></p>
        <p><blockquote>Texto</blockquote></p>


        <p>Here is a quote from WWF's website:</p>
        <blockquote cite="http://www.worldwildlife.org/who/index.html">
        For 60 years, WWF has worked to help people and nature thrive. As the world's leading conservation organization, WWF works in nearly 100 countries. At every level, we collaborate with people around the world to develop and deliver innovative solutions that protect communities, wildlife, and the places in which they live.
        </blockquote>

        <p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>

        <p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>
~~~

- Lista não ordenada:
~~~
        <ul> 
            <li>item 1</li> 
            <li>item 2</li>
            <li>item 3</li>
        </ul>
~~~
- Lista ordenada:
~~~
        <ol> 
            <li>item A</li>
            <li>item B</li>
            <li>item C</li>
        </ol>
~~~
- Lista descritiva:
~~~
        <dl>
            <dt>Chrome</dt>
            <dd>
                o chrome foi desenvolvido pelo google...
            </dd>

            <dt>IE</dt>
            <dd>
                o ie foi desenvolvido pela Microsoft...
            </dd>

            <dt>Safari</dt>
            <dd>
                o safari foi desenvolvido pela Apple...
            </dd>
        </dl>
~~~

- Imagens:
~~~
        <img src="../000-Exercícios/assets/States_of_Brazil.png" 
             alt="Mapa do Brasil" title="Mapa dos estados do brasil" width="150" height="150">
~~~

### Links no HTML
- Link para outro site:
~~~
        <p> O <a href="https://www.entra21.com.br/" target="_blank">Entra21</a> é um programa de empregabilidade e formação profissional</p>
~~~

- Link para Bookmark da própria página:
~~~
         <p><a href="#titulo3">Link para o topo da página</a></p>
~~~

- Link para Bookmark de outra página:
~~~
         <p><a href="https://www.proway.de/#colophon" target="_blank">rodapá no site da proway</a></p>
~~~

- Link para uma página do próprio site:
~~~
         <p><a href="contato.html">Página de contato</a></p>
~~~

- Link em uma imagem/figura/tag:
~~~
        <a href="https://pt.wikipedia.org/wiki/HTML" target="_black">
        <img src="assets/brazil-flag.png" width="150" alt="fundo js">
    </a>
~~~

- Link para E-mail:
~~~
         <p>Gostou de nossa oferta? entre em <a href="mailto:ivan.borchardt.cobol@gmail.com?subject=Contato&body=estou entrando em contato referente a oferta...">contato</a></p>
~~~

- Link de Download:
~~~
         <p>baixe a <a href="assets/brazil-flag.png" download>bandeira do brasil</a></p>
~~~

### Estrturação com tags semânticas
- Exemplo de arquivo HTML utilizando tags semânticas: header, main, footer, section, nav, aside...:
~~~
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <div>
        <!---------------- Area de Cabeçalho ---------------------->
        <header>
                <h1>titulo</h1>
                <nav>
                    <ul>
                        <li><a href="">Home</a></li>
                        <li><a href="">Loja</a></li>
                        <li><a href="">Contato</a></li>
                    </ul>
                </nav>
            </div>
            <div>
                <p>logo da empresa</p>
            </div>
        </header>
        <!---------------- Barra Lateral Esquerda ---------------------->
        <aside>
            <p>aside esquerda</p>
        </aside>
        <!---------------- Sessao Principal ---------------------->
        <main>
            <section>
                <span><p>caixa de uma unica linha</p></span>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                    Dolore aperiam, <span>facere modi animi</span> dignissimos maiores? 
                    Eaque enim laudantium libero illum debitis nisi ullam hic 
                    consequatur, quisquam quam aliquam alias mollitia.</p>
                <div>

            </section>

            <section>
                <h2>Titulo</h2>
                <article>
                    <h3>titulo do artigo </h3>
                    <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Illum, ratione repellat praesentium
                        explicabo reiciendis laborum! Quidem quisquam voluptatem, dolor facere, esse debitis harum quod,
                        laboriosam tenetur reiciendis unde sunt praesentium.</p>
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Voluptatem in corrupti obcaecati
                        voluptatibus, reprehenderit laboriosam, veritatis minima, saepe vel fuga similique? Ullam,
                        consectetur sunt eum eligendi doloremque velit nemo rerum.</p>
                </article>

            </section>
            <section>
                <figure>
                    <img src="" alt="">
                </figure>
            </section>
        </main>
        <!---------------- Bara Lateral Direita ---------------------->
        <aside>
            <p>aside direita</p>
        </aside>
        <!---------------- Sessão de Rodapé  ---------------------->
        <footer>

        </footer>
    </div>
</body>

</html>
~~~



 <p align="center">
<a href="https://www.entra21.com.br/"> 
<img src= "https://cdn.sonicadigital.com.br/entra21/storage/header/257/original-61f8610472d4f.png">
</a>
</p>