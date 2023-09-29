## HTML

### HTML Structure
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

- Structure Explanation
~~~
- The <!DOCTYPE html> declaration defines that this document is an HTML5 document.
- The <html> element is the root element of an HTML page.
- The <head> element contains meta-information about the HTML page.
- The <title> element specifies a title for the HTML page (which is displayed in the browser's title bar or tab).
- The <body> element defines the body of the document and is a container for all visible content, such as headings, paragraphs, images, hyperlinks, tables, lists, etc.
- The <h1> element defines a top-level heading.
- The <p> element defines a paragraph.
~~~

### HTML Tags
- Headings:
~~~
        <h1>Heading 1</h1>
        <h2>Heading 2</h2>
        <h3>Heading 3</h3>
        <h4>Heading 4</h4>
        <h5>Heading 5</h5>
        <h6>Heading 6</h6>
~~~

- Paragraph:
~~~
        <p>This is a paragraph...</p>
~~~

- Text Formatting:
~~~
        <p><b>Bold</b></p>
        <p><strong>Strong</strong></p>
        <p><i>Italic</i></p>
        <p><em>Emphasized</em></p>
        <p><mark>Highlighted</mark></p>
        <p><small>Small Text</small></p>
        <p><big>Big Text</big></p>
        <p><s>Strikethrough Text</s></p>
        <p><del>Deleted Text</del></p>
        <p>H<sub>2</sub>O</p>
        <p>x<sup>2</sup></p>
~~~

- Quotation and Citation Elements:
~~~
        <p><q>Quoted Text</q></p>
        <p><blockquote>Text</blockquote></p>

        <p>Here is a quote from WWF's website:</p>
        <blockquote cite="http://www.worldwildlife.org/who/index.html">
        For 60 years, WWF has worked to help people and nature thrive. As the world's leading conservation organization, WWF works in nearly 100 countries. At every level, we collaborate with people around the world to develop and deliver innovative solutions that protect communities, wildlife, and the places in which they live.
        </blockquote>

        <p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>

        <p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>
~~~

- Unordered List:
~~~
        <ul> 
            <li>Item 1</li> 
            <li>Item 2</li>
            <li>Item 3</li>
        </ul>
~~~
- Ordered List:
~~~
        <ol> 
            <li>Item A</li>
            <li>Item B</li>
            <li>Item C</li>
        </ol>
~~~
- Definition List:
~~~
        <dl>
            <dt>Chrome</dt>
            <dd>
                Chrome was developed by Google...
            </dd>

            <dt>IE</dt>
            <dd>
                IE was developed by Microsoft...
            </dd>

            <dt>Safari</dt>
            <dd>
                Safari was developed by Apple...
            </dd>
        </dl>
~~~

- Details and Summary:
~~~
        <details>
            <summary>How can I access my course?</summary>
            <p>You can access your course through YouTube using the following link...</p>
        </details>
~~~

### HTML Links
- Link to Another Website:
~~~
        <p> <a href="https://www.entra21.com.br/" target="_blank">Entra21</a> is a program for employability and professional training.</p>
~~~

- Link to a Bookmark on the Same Page:
~~~
         <p><a href="#heading3">Link to the top of the page</a></p>
~~~

- Link to a Bookmark on Another Page:
~~~
         <p><a href="https://www.proway.de/#colophon" target="_blank">Footer on the proway website</a></p>
~~~

- Link to a Page on the Same Site:
~~~
         <p><a href="contact.html">Contact Page</a></p>
~~~

- Link on an Image/Figure/Tag:
~~~
        <a href="https://en.wikipedia.org/wiki/HTML" target="_blank">
        <img src="assets/brazil-flag.png" width="150" alt="JS background">
    </a>
~~~

- Email Link:
~~~
         <p>Like our offer? Get in <a href="mailto:ivan.borchardt.cobol@gmail.com?subject=Contact&body=I'm reaching out regarding the offer...">touch</a></p>
~~~

- Download Link:
~~~
         <p>Download the <a href="assets/brazil-flag.png" download>Brazilian flag</a></p>
~~~

### Tables
- Minimum Table Structure:
~~~
      <table border="1">
        <tr>
            <th>Column 1</th>
            <th>Column 2</th>
            <th>Column 3</th>
        </tr>
    </table>
~~~

- Complete Table Structure:
~~~
   <table border="1" cellpadding="10" width="100%" align="center">
        <thead>
            <tr>
                <th>Qty</th>
                <th>Description</th>
                <th>Value</th>
            </tr>
        </thead>
        <tbody>
            <tr align="center">
                <td>1</td>
                <td>Pencil</td>
                <td>1.00</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="2"><b>Total</b></td>
                <td>19.00</td>
            </tr>
        </tfoot>
    </table>
~~~

- Merging Rows and Columns in a Table:
~~~
    <table border="1" cellspacing="0" >
        <tr>
            <td rowspan="2">Row 1, Column 1</td>
            <td>Row 1, Column 2</td>
            <td>Row 1, Column 3</td>
        </tr>
        <tr>
            <td>Row 2, Column 1</td>
            <td>Row 2, Column 2</td>
        </tr>
        <tr>
            <td>Row 3, Column 2</td>
            <td colspan="2">Row 3, Column 3</td>
        </tr>
    </table>
~~~

### Audiovisual Tags
- Images: Image types jpeg, png, gif, svg, ico
~~~
    <figure>
        <img src="assets/brazil-flag.png" alt="" width="100" title="Brazilian Flag">
        <figcaption>Credits: Some Artist</figcaption>
    </figure>
~~~

- Videos mp4, ogg, WebM
~~~
    <video width="320" controls autoplay loop muted>
        <source src="assets/20230513_160933.mp4">
        <source src="assets/20230513_160933.ogg">
        Your browser does not support the video tag.
    </video>
~~~

- YouTube Videos
~~~
    <iframe width="420" height="315" src="https://www.youtube.com/embed/SsqXAP0EeEI">
    </iframe>
~~~

- Audio
~~~
     <audio controls autoplay loop muted>
        <source src="assets/bad_to_the_bone.mp3" type="audio/mpeg">
        <source src="assets/bad_to_the_bone.ogg" type="audio/ogg">
        Your browser does not support the audio tag.
    </audio>
    <p>Download</p>
~~~

### Structuring with Semantic Tags
- Example of an HTML file using semantic tags: header, main, footer, section, nav, aside...:
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
        <!---------------- Header Area ---------------------->

        <header>
                <h1>Title</h1>
                <nav>
                    <ul>
                        <li><a href="">Home</a></li>
                        <li><a href="">Store</a></li>
                        <li><a href="">Contact</a></li>
                    </ul>
                </nav>
            </div>
            <div>
                <p>Company Logo</p>
            </div>
        </header>
        <!---------------- Left Sidebar ---------------------->

        <aside>
            <p>Left Sidebar</p>
        </aside>
        <!---------------- Main Section ---------------------->

        <main>
            <section>
                <span><p>Single-line box</p></span>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                    Dolore aperiam, <span>facere modi animi</span> dignissimos maiores? 
                    Eaque enim laudantium libero illum debitis nisi ullam hic 
                    consequatur, quisquam quam aliquam alias mollitia.</p>
                <div>

            </section>

            <section>
                <h2>Title</h2>
                <article>
                    <h3>Article Title</h3>
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
        <!---------------- Right Sidebar ---------------------->

        <aside>
            <p>Right Sidebar</p>
        </aside>
        <!---------------- Footer Section ---------------------->

        <footer>

        </footer>
    </div>
</body>

</html>
~~~

### Form Example
- Example of a form using HTML:
~~~
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .label {
            display: block;
        }
    </style>
</head>

<body>
    <form action="" method="POST">

        <fieldset>
            <legend>Registration</legend>

            <label for="idAge" class="label">Age</label>
            <input type="text" name="" id="">

            <div>
                <div>
                    <label for="idCpf">CPF:</label>
                </div>
                <input type="text" name="" id="">
            </div>

            <label for="idName">Name:</label><br>
            <input type="text" id="idName" name="nmName" value="João">

        </fieldset>

        <br><br>
        <label for="idDesc">Description</label><br>
        <!-- Multi-line text field -->
        <textarea name="nmDesc" id="idDesc" cols="30" rows="10">innerText</textarea>
        <!-- The value of the textarea is the innerText property -->

        <!-- Selection box -->
        <label for="idCars">Choose your Car:</label><br>
        <select name="nmCars" id="idCars" size="3" multiple>
            <option value="volvo">Volvo</option>
            <option value="ford ka">Ford Ka</option>
            <option value="fiat">Fiat</option>
            <option value="lamborghini">Lamborghini</option>
        </select>

        <br><br>
        <select name="cars" id="cars" size="3" multiple>
            <optgroup label="Swedish Cars">
                <option value="volvo">Volvo</option>
                <option value="saab">Saab</option>
            </optgroup>
            <optgroup label="German Cars">
                <option value="mercedes">Mercedes</option>
                <option value="audi">Audi</option>
            </optgroup>
        </select>

        <br><br>
        <!-- Data list (item selection) -->
        <label for="idBrowsers">Browsers:</label><br>
        <input list="idBrowsers">
        <datalist id="idBrowsers">
            <option value="Internet Explorer">IE</option>
            <option value="Chrome">Chrome</option>
            <option value="Firefox">Firefox</option>
            <option value="Opera">Opera</option>
            <option value="Safari">Safari</option>
            <option value="Brave">Brave</option>
            <option value="Edge">Edge</option>
            <option value="Yahoo">Yahoo</option>
        </datalist>

        <br><br>
        <!-- Buttons -->
        <button type="reset">Clear</button>
        <button type="submit">Submit</button>
        <button type="button">Test</button>
    </form>
</body>

</html>
~~~

### Form Example - Inputs
- Example of form inputs types using HTML:
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .label {
            display: block;
        }
    </style>
</head>
<body>
    <form action="">
        <!-- Single-line text field -->
        <label for="idName" class="label">Name:</label>
        <input type="text" name="nmName" id="idName" value="" size="35" minlength="2" maxlength="5" placeholder="Name" autocomplete="off" required>

        <label for="idLastName" class="label">Last Name:</label>
        <input type="text" name="nmLastName" id="idLastName" value="" pattern="[A-Za-z]{3}">

        <!-- Phone Field -->
        <label for="idTel" class="label">Phone:</label>
        <input type="tel" name="nmTel" id="idTel" value="" pattern="\(\d{2}\) \d{4}-\d{4}">

        <!-- Numeric Field -->
        <label for="idTemp" class="label">Temperature</label>
        <input type="number" name="nmTemp" id="idTemp" min="-5" max="100" step="0.01" autofocus>

        <!-- Numeric Range -->
        <label for="idInter" class="label">Interval</label>
        <input type="range" name="nmInter" id="idInter" min="0" max="100" value="0" disabled>

        <!-- Password Boxes -->
        <label for="idPassword" class="label">Password</label>
        <input type="password" name="nmPassword" id="idPassword" pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}" title="Must contain at least one number and both uppercase and lowercase letters, and at least 8 or more characters">

        <!-- Email Boxes -->
        <label for="idEmail" class="label">Email</label>
        <input type="email" name="nmEmail" id="idEmail" value="Ivan.Borchardt@T-Systems.com" readonly>

        <!-- Date Boxes -->
        <label for="idDate" class="label">Date</label>
        <input type="date" name="nmDate" id="idDate" min="2022-04-01" max="2022-05-30">

        <!-- Local Date-Time Boxes -->
        <label for="idLocalDateTime" class="label">Date: </label>
        <input type="datetime-local" name="nmLocalDateTime" id="idLocalDateTime">

        <!-- Time Boxes -->
        <label for="idTime" class="label">Time</label>
        <input type="time" name="nmTime" id="idTime">

        <!-- Color Picker -->
        <label for="idColor" class="label">Color</label>
        <input type="color" name="nmColor" id="idColor">

        <!-- Radio Buttons -->
        <br><br>
        <input type="radio" name="nmGender" id="idFemale" checked>
        <label for="idFemale">Female</label>
        <br>
        <input type="radio" name="nmGender" id="idMale">
        <label for="idMale">Male</label>
        <br>
        <input type="radio" name="nmGender" id="idLGBT">
        <label for="idLGBT">LGBT</label>

        <!-- Checkboxes -->
        <br><br>
        <input type="checkbox" name="nmBrands" id="idFordKa">
        <label for="idFordKa">Ford Ka</label>
        <br>
        <input type="checkbox" name="nmBrands" id="idGol">
        <label for="idGol">Gol</label>
        <br>
        <input type="checkbox" name="nmBrands" id="idFerrari">
        <label for="idFerrari">Ferrari</label>

        <br><br>
        <input type="submit" name="" id="">
        <input type="reset" name="" id="" value="Clear">
        <input type="button" name="" id="" value="Test">
    </form>
</body>
</html>
~~~