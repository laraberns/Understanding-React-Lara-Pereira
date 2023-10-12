## CSS

- [CSS - Inline x External Style Sheet X Internal Style Sheet](#CSS-Inline)
- [CSS - Backgrounds Styles](#Backgrounds)
- [CSS - Text Styles](#Text)
- [CSS - Colors - Types](#Colors)
- [CSS - Fonts - Variants](#Fonts)
- [CSS - Box Model](#BoxModel)
- [CSS - Links](#Links)
- [CSS - Lists](#Lists)
- [CSS - Table](#Table)
- [CSS - Filter for img files](#Filter)
- [CSS - Flexbox](#Flexbox)
- [CSS - Declaring variables at the --root](#Declaring)
- [CSS - Form](#Form)
- [CSS - Grid](#Grid)
- [CSS - Media Queries](#Media)

### CSS - Inline x External Style Sheet X Internal Style Sheet <a id="CSS-Inline"></a>
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="assets/styles.css"> <!-- External Style Sheet -->
    
    <!-- Internal Style Sheet -->
    <style>  
        * {
            padding: 0;
        }
        h1 {
            padding: 0;
        }

        .class1 {
            background-color: aquamarine;
        }

        #id1 {
            padding: 0;
        }
    </style>
</head>
<body>
    <div id="id1" class="class1"> 
        <h1 style="color: beige;">Tests</h1> <!-- Inline Styles -->
    </div>   

    <div id="id2">
        <h1 class="class2">Test 2</h1>
    </div>

    <p>Lorem ipsum dolor sit amet.</p>
</body>
</html>

~~~

### CSS - Backgrounds Styles <a id="Backgrounds"></a>

~~~
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .bgPhoto {
            background-color: beige;
            background-image: url("assets/background.png");
            background-repeat: no-repeat;
            background-position: center top;
            background-attachment: fixed;
            background-size: 1000px;
            opacity: 30%;
        }

        .bgColor {
            background-color: beige;
            height: 100vh;
        }

        #title2 {
            background-color: aqua;
        }
    </style>

</head>

<body>
    <section class="bgPhoto">
        <h1>Test</h1>

        <h1>My Example Title</h1>

        <h1 id="title2">My Example Title</h1>

        <h1 id="title3">My Example Title</h1>

        <h1 id="title4">My Example Title</h1>

        <h1 id="title5">My Example Title</h1>

        <h1>The background-attachment Property</h1>

        <p id="idPgr">The background-attachment property specifies whether the background image should scroll or be
            fixed (will not scroll with the rest of the page).</p>

        <p><strong>Tip:</strong> If you do not see any scrollbars, try to resize the browser window.</p>

        <p>The background-image scrolls. Try to scroll down the page.</p>
        <p>The background-image scrolls. Try to scroll down the page.</p>
        <!-- Repeat these lines for the remaining paragraphs as needed. -->

    </section>
    <section class="bgColor">
        <h1>Title of Session 2</h1>
    </section>
</body>

</html>

~~~

### CSS - Text Styles <a id="Text"></a>

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
    <style>
        .height100 {
            height: 100px;
            background-color: bisque;
        }

        h1 {
            background-color: aquamarine;
            color: red;
            /* Alignment */
            text-align: center; /* left, right, center */

            /* Text Decoration */
            text-decoration-line: overline line-through;
            text-decoration-color: black;
            text-decoration-style: double;
            text-decoration-thickness: 1px;
            text-decoration: underline red wavy 1px;

            /* Text Transformations */
            text-transform: capitalize; /* uppercase; lowercase */
        }

        h2 {
            /* Text Shadow */
            text-shadow: 0 0 3px #ff0000, 0 0 5px #0000ff;
        }

        p {
            text-align: justify; /* left, right, center, justify */
            /* Direction: rtl; */

            /* Spacing */
            text-indent: 30%;
            letter-spacing: 3px;
            line-height: 20px;
            word-spacing: 15px;
            white-space: nowrap; /* Prevents line breaks, forcing horizontal scrolling */
        }

        a {
            text-decoration: none;
        }
    </style>
</head>
<body>
    <div class="height100" id="uniqueId">
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt, iusto?</p>
    </div>
    <h1>Test Title</h1>

    <h2>Test Title 2</h2>

    <p><a href="">Any Link</a></p>
    <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusamus quisquam ad expedita numquam! Officia, libero sint? Beatae assumenda quis aliquid maxime consequuntur quam aperiam minus odit incidunt, enim autem ipsam?</p>
</body>
</html>
~~~

### CSS - Colors - Types <a id="Colors"></a>

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .rgb_d {
            color: rgba(156, 192, 66, 0.708);
        }

        .rgb_h {
            color: #ff0000;
        }

        .hsl {
            color: hsl(0, 38.05%, 38%);
        }

        .hsla {
            color: hsla(0, 38.05%, 38%, 0.5);
        }
    </style>
</head>
<body>
    <p class="rgb_d">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam, veniam!</p>

    <p class="rgb_h">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat, harum.</p>

    <p class="hsl">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Similique provident autem impedit nostrum, expedita accusamus recusandae, cum cupiditate commodi soluta voluptate eligendi harum consequuntur neque incidunt asperiores voluptates! Iste, at.</p>
    <p class="hsla">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Similique provident autem impedit nostrum, expedita accusamus recusandae, cum cupiditate commodi soluta voluptate eligendi harum consequuntur neque incidunt asperiores voluptates! Iste, at.</p>
</body>
</html>
~~~

### CSS - Fonts - Variants <a id="Fonts"></a>

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Qwitcher+Grypen:wght@700&display=swap" rel="stylesheet">

    
    <style>
        div {
            font-size: 25px;
        }

        .font01 {
            font-style: italic;
            font-variant: normal;
            font-weight: 800;
            font-size: 0.5em;
            font-family: 'Courier New', Courier, 'lucida console', monospace;
        }
        
        .font02 {
            font-family: 'Roboto', sans-serif;
            font-weight: lighter;
        }

        .font03 {
            font-family: 'Qwitcher Grypen', cursive;
        }

        .font04 {
            font: italic small-caps lighter 25px/30px 'Shadows Into Light', cursive;
        }
    </style>
</head>
<body>
    <div>
        <p class="font01">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus, alias.</p>
    </div>
    <p class="font02">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus, alias.</p>
    <p class="font03">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus, alias.</p>
    <p class="font04">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus, alias.</p>
</body>
</html>
~~~

### CSS - Box Model <a id="BoxModel"></a>

~~~
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            border: 0;
            margin: 0;
            padding: 0;
        }

        p {
            border-style: dashed;
            border-color: blue;
            border-width: 10px;


            border-top-style: solid;
            border-bottom-style: dotted;

            border-left-color: blueviolet;
            border-right-width: 2px;

            padding: 15px;
            padding-left: 30px;
            padding-top: 50px;
            padding-bottom: 60px;
            padding-right: 40px;

            margin: 30px;


            outline-style: solid;
            outline-color: red;
            outline-width: thin;
            outline-offset: 10px;

        }


        h1 {
            margin: 5px;
            margin: 19px 18px 20px 21px;
            margin-left: 45px;
            border-style: solid;
            border-width: 9px;
            padding: 10px;
            padding: 11px 12px 21px 24px;

            outline-style: solid;
            outline-color: red;
            outline-width: thin;
            outline-offset: 10px;

        }





        div {
            height: 100px;
            width: 100px;

            border-color: brown;
            border-style: solid;
            border-width: 5px;
            border-radius: 50%;

            border-top-style: dotted;

            margin: 30px;

        }

        section {
            height: 100px;
            width: 100px;
            border: 5px solid red;
            border-radius: 15px;

            margin: 50px;


        }

        .box {
            width: 200px;
            height: 200px;
            border: 2px solid black;
            border-radius: 0px;
            padding: 10px;
            box-sizing: border-box;
        }
    </style>
</head>

<body>
    <p>lorem ipsum et</p>

    <div></div>

    <section></section>

    <div class="box"></div>
</body>

</html>
~~~

### CSS - Links <a id="Links"></a>
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <style>
        .menu {
            display: flex;
        }

        .menu li {
            margin: 5px;
            list-style: none;
        }

        a:link, a:visited {
            background-color: white;
            color: black;
            border: 2px solid green;
            padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
        }

        a:hover, a:active {
            background-color: green;
            color: white;
        }
    </style>
</head>
<body>

    <header>
        <nav>
            <ul class="menu">
                <li><a href="#1">Home</a></li>
                <li><a href="#2">Contact</a></li>
                <li><a href="#3">About</a></li>
            </ul>
        </nav>
    </header>
    
</body>
</html>
~~~

### CSS - Lists <a id="Lists"></a>
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>

        .menu{
            display: flex;
            list-style-type: none;
        }
        
        .menu li{
            margin: 5px;  
        }

        .list{
            list-style-type: lower-greek;
            list-style-image: url("assets/index.gif");
            list-style-position: inside;

            padding: 25px;
            margin: 10px;
            background-color: violet;

        }

        .list li{
            background-color: thistle;
            padding: 3px;
            margin: 5px;
        }

    </style>

</head>
<body>

    <header>
        <nav>
            <ul class="menu">
                <li>menu-1</li>
                <li>menu-2</li>
                <li>menu-3</li>
            </ul>
        </nav>
    </header>


    <ul class="list">
        <li>item-1</li>
        <li>item-2</li>
        <li>item-3</li>
        <li>item-4</li>
        <li>item-5</li>
    </ul>
    
</body>
</html>
~~~

### CSS - Table <a id="Table"></a>
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>

        table {
            empty-cells: hide;
        }

        table, th, td{
            border-style: solid;
            border-top-style: dotted;
        }

        th{
            padding-left: 25px;
            padding-right: 25px;
            line-height: 25px;
            background-color: black;
            color: antiquewhite;
            border-color: brown;
        }

        tr{
            background-color: chartreuse;
        }

        td:hover{
            background-color: thistle;
        }

        tr:nth-child(odd){ /*even, odd, 3n, 4, 2n + 1...*/
            background-color: bisque;
        }

        td{
            height: 50px;
            width: 200px;
            text-align: center;
            vertical-align: top;
        }

        .tabs{
            width: 100vw;
            height: 30vh;
            overflow-y: auto;
            overflow-x: auto;
        }

    </style>

</head>
<body>
    <h1>Heading 1</h1>

    <div class="tabs">
        <table>
            <tr>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td>Peter</td>
                <td>Griffin</td>
                <td>Peter</td>
                <td>Griffin</td>
                <td>Peter</td>
                <td>Griffin</td>
                <td>Peter</td>
                <td>Griffin</td>
                <td>Peter</td>
                <td>Griffin</td>
                <td>Peter</td>
                <td>Griffin</td>
                <td>Peter</td>
                <td>Griffin</td>
            </tr>
            <!-- Additional rows go here -->
        </table>
    </div>

    <div class="tabs">
        <table cellspacing="15px">
            <tr>
                <th>Firstname</th>
                <th>Lastname</th>
                <th>Firstname</th>
                <th>Lastname</th>
            </tr>
            <tr>
                <td>Peter</td>
                <td>Griffin</td>
                <td>Peter</td>
                <td>Griffin</td>
            </tr>
            <!-- Additional rows go here -->
        </table>
    </div>

    <h2>Heading 2</h2>
</body>
</html>
~~~

### CSS - Filter for img files <a id="Filter"></a>
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        img{
            width: 400px;
        }

        label{
            display: block;
        }

        .clOpacity{
            opacity: 0.3;
        }

        .clBlur{
            filter: blur(5px);
        }

        .clBrightness{
            filter: brightness(2);
        }

        .clContrast{
            filter: contrast(1.2);
        }

        .clGrascale{
            filter:grayscale(0.2);
        }

        .clInvert{
            filter:invert();
        }

        .clSaturate{
            filter:saturate(2);
        }

        .clSepia{
            filter:sepia(0.5);
        }

        .clDropShadow{
            filter: drop-shadow(15px 25px 25px rgb(127, 125, 127))
        }

        .clHueRotate{
            filter: hue-rotate(240deg);
        }

        .clCombo{
            filter: blur(5px) opacity(0.5) grayscale(0.8);
        }



    </style>

</head>
<body>
    <div>
        <label for="">Opacity...</label>
        <img src="assets/Foto1.JPG" alt="Voando de Parapente" class="clOpacity">
    </div>
    <div>
        <label for="">Blur...</label>
        <img src="assets/Foto2.JPG" alt="Caiaque" class="clBlur">
    </div>
    <div>
        <label for="">Brightness...</label>
        <img src="assets/Foto1.JPG" alt="Voando de Parapente" class="clBrightness">
    </div>
    <div>
        <label for="">Contrast...</label>
        <img src="assets/Foto2.JPG" alt="Caiaque" class="clContrast">
    </div>
    <div>
        <label for="">Grascale...</label>
        <img src="assets/Foto1.JPG" alt="Voando de Parapente" class="clGrascale">
    </div>
    <div>
        <label for="">Invert...</label>
        <img src="assets/Foto2.JPG" alt="Caiaque" class="clInvert">
    </div>
    <div>
        <label for="">Saturate...</label>
        <img src="assets/Foto1.JPG" alt="Voando de Parapente" class="clSaturate">
    </div>
    <div>
        <label for="">Sepia...</label>
        <img src="assets/Foto2.JPG" alt="Caiaque" class="clSepia">
    </div>
    <div>
        <label for="">DropShadow...</label>
        <img src="assets/Foto1.JPG" alt="Voando de Parapente" class="clDropShadow">
    </div>
    <div>
        <label for="">HueRotate...</label>
        <img src="assets/Foto2.JPG" alt="Caiaque" class="clHueRotate">
    </div>   
    <div>
        <label for="">Combo...</label>
        <img src="assets/Foto1.JPG" alt="Voando de Parapente" class="clCombo">
    </div>   
</body>
</html>
~~~

### CSS - Flexbox <a id="Flexbox"></a>

~~~
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Documento</title>
    <style>
        .row {
            border: 1px solid red;
            margin: 15px;
            display: flex;
            height: 300px;
            flex-direction: row;  /*column; column-reverse; row; row-reverse;*/
            
            /*Horizontal Alignment*/
            justify-content: flex-end; /*center; space-around; space-between; space-evenly;*/
            
            /*Vertical Alignment without wrap enabled*/
            /*align-items: center;*//*center; flex-start; flex-end; stretch; baseline;*/
            
            /*Vertical Alignment with wrap enabled*/
            align-content: space-evenly; /*center; space-between; space-around; stretch; flex-start; flex-end;*/
            
            /*Item Wrapping Mode (line break...)*/
            flex-wrap: wrap; /*wrap; wrap-reverse; nowrap;*/
           
            /*Shorthand property to set flex-direction and flex-wrap properties.*/
            /* flex-flow: row wrap; */
        }

        .column {
            border: 1px solid blue;
            margin: 5px;
            padding: 15px;
        }

        /*Example 2*/
        .row1 {
            border: 1px solid red;
            margin: 15px;
            display: flex;
        }

        .column1 {
            border: 1px solid blue;
            margin: 5px;
            padding: 15px;
        }

        #item-1 {
            order: 3;
            flex-grow: 1;
            flex-shrink: 2;
        }

        #item-2 {
            order: 2;
            flex-grow: 1;
            flex-shrink: 1;
            flex-basis: 200px;
        }
    </style>
</head>
<body>
    <div class="row">
        <div class="column">1</div>
        <div class="column">2</div>
        <div class="column">3</div>
        <div class="column">4</div>
        <div class="column">5</div>
        <div class="column">6</div>
        <div class="column">7</div>
        <div class="column">8</div>
        <div class="column">9</div>
        <div class="column">10</div>
    </div>

    <div class="row1">
        <div class="column1" id="item-1">Estático 1</div>
        <div class="column1" id="item-2">Estático 2</div>
        <div class="column1" id="item-3">Estático 3</div>
    </div>
</body>
</html>
~~~

### CSS - Declaring variables at the --root <a id="Declaring"></a>

~~~
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* Color Palette */
        :root {
            --main-color: #04C4D9;
            --complementary-color: #2E3159;
            --complementary-color2: #2e31597d;
            --contrast-color1: #D94A64;
            --contrast-color2: #A62F03;
            --neutral-color1: white;
            --neutral-color2: black;
            --background-color1: #26262b;
            --background-color2: azure;
        }

        h1 {
            color: var(--main-color);
        }

        div {
            background-color: var(--background-color1);
        }

    </style>
</head>
<body>

    <div>
        <h1>Test CSS</h1>
    </div>
    
</body>
</html>
~~~

### CSS - Form <a id="Form"></a>

~~~
<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        input {
            margin-bottom: 5px;
            padding: 5px;
        }

        input:focus {
            color: blue;
            outline-color: aqua;
        }

        .borderless-field {
            border: 0;
            border-bottom: 1px solid black;
        }

        .search-field {
            padding-left: 25px;
            background-image: url("assets/searchicon.png");
            background-repeat: no-repeat;
            background-size: 7%;
        }

        .numeric[type=number] {
            padding: 15px;
        }
    </style>
</head>

<body>

    <form action="">

        <input class="search-field" type="text" placeholder="Pesquisar...">
        <input class="borderless-field" type="text" placeholder="Nome">
        <input class="borderless-field" type="text" placeholder="Sobrenome">

        <input class="numeric borderless-field" type="number" placeholder="Altura">

    </form>

</body>

</html>

~~~

### CSS - Grid <a id="Grid"></a>

~~~
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Documento</title>
    <style>
        /* Example 1 */
        .grid-container {
            border: 1px solid red;
            display: grid;
            grid-template-columns: 45px auto 30%;
            column-gap: 5px;
            row-gap: 8px;
            padding: 5px;
        }

        .grid-item {
            border: 1px solid black;
            height: 30px;
        }

        /* Example 2 */
        .grid-container2 {
            margin-top: 30px;
            border: 1px solid red;
            display: grid;
            grid-template-columns: auto auto auto auto;
            column-gap: 5px;
            row-gap: 8px;
            padding: 5px;
        }

        .grid-item2 {
            border: 1px solid black;
            height: 30px;
        }

        #item-1 {
            grid-column-start: 1;
            grid-column-end: 3;
        }

        #item-2 {
            grid-row-start: 2;
            grid-row-end: 4;
            align-self: end;
        }

        #item-3 {
            justify-self: center;
        }

        /* Example 3 */
        .grid-container3 {
            margin-top: 30px;
            border: 1px solid red;
            display: grid;
            grid-template-areas:
                'header header header'
                'sidebar main main'
                'footer footer footer';
            column-gap: 5px;
            row-gap: 8px;
            padding: 5px;
        }

        .grid-item3 {
            border: 1px solid black;
        }

        #idHeader {
            grid-area: header;
        }

        #idMain {
            grid-area: main;
        }

        #idAside {
            grid-area: sidebar;
        }

        #idFooter {
            grid-area: footer;
        }
    </style>
</head>
<body>
    <div class="grid-container">
        <div class="grid-item">item 1</div>
        <div class="grid-item">item 2</div>
        <div class="grid-item">item 3</div>
        <div class="grid-item">item 4</div>
        <div class="grid-item">item 5</div>
        <div class="grid-item">item 6</div>
        <div class="grid-item">item 7</div>
        <div class="grid-item">item 8</div>
        <div class="grid-item">item 9</div>
        <div class="grid-item">item 10</div>
        <div class="grid-item">item 11</div>
        <div class="grid-item">item 12</div>
    </div>

    <div class="grid-container2">
        <div id="item-1" class="grid-item2">item 1</div>
        <div id="item-2" class="grid-item2">item 2</div>
        <div id="item-3" class="grid-item2">item 3</div>
        <div id="item-4" class="grid-item2">item 4</div>
        <div id="item-5" class="grid-item2">item 5</div>
        <div id="item-6" class="grid-item2">item 6</div>
        <div id="item-7" class="grid-item2">item 7</div>
        <div id="item-8" class="grid-item2">item 8</div>
        <div id="item-9" class="grid-item2">item 9</div>
        <div id="item-10" class="grid-item2">item 10</div>
        <div id="item-11" class="grid-item2">item 11</div>
        <div id="item-12" class="grid-item2">item 12</div>
    </div>

    <div class="grid-container3">
        <header id="idHeader" class="grid-item3">Cabeçalho</header>
        <main id="idMain" class="grid-item3">Principal</main>
        <aside id="idAside" class="grid-item3">Lado</aside>
        <footer id="idFooter" class="grid-item3">Rodapé</footer>
    </div>
</body>
</html>
~~~

### CSS - Media Queries <a id="Media"></a>

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>

        h1{
            color: aqua;
        }


        @media screen and (min-width: 600px) and (orientation: portrait) {
            h1{
                color: red; 
            }
        }

        @media screen and (min-width: 600px) and (orientation: landscape) {
            h1{
                color: red; 
            }
        }

        @media screen and (min-width: 900px) {
            h1{
                color: green; 
            }
        }

        @media screen and (min-width: 1200px) {
            h1{
                color: purple; 
            }
        }

        @media  print {
            h1{
                color:blue;
            }
        }

    </style>

</head>
<body>

    <h1>Titulo 1</h1>

</body>
</html>
~~~