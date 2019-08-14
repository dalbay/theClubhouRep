``` javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link href="https://fonts.googleapis.com/css?family=Roboto+Slab|VT323&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="bootstrap.min.css">
    <title>Document</title>
    <style>
    article#firstArticle{ color:rgb(124, 100, 99);
        width: 650px;
        height: 100px;
        background-color: aliceblue;
    }
    a{
        font-family: 'Roboto Slab', serif;
font-family: 'VT323', monospace;
    }
    article:first-child {
        width: 90%;
        height: 90%;
    }
    aside{
        display: block;
        float: left;
        width: 90%;
        background-color: gray;
    }
    span.a {
        display: inline-block;
  width: 50%;
  height: 100px;
  padding: 5px;
  border: 1px solid blue;
  float: left;
    }
    span.b {
        display: inline-block;
  width: 50%;
  height: 100px;
  padding: 5px;
  border: 1px solid blue; 
    }
    </style>
</head>

<body>
    <section>
        <nav class="navbar navbar-dark bg-primary mb-3">
            <div class="container">
                <a href="https://www.w3schools.com/default.asp" class="navbar-brand">w3schools</a>
            </div>
        </nav>

        <div class="container searchContainer">
            <div class="search card card-body">
                <h1>Login Page</h1>

                <label for="email2" class="mb-2 mr-sm-2">Email:</label>
                <input type="text" class="form-control mb-2 mr-sm-2" id="email2" placeholder="Enter email" name="email">
                <label for="pwd2" class="mb-2 mr-sm-2">Password:</label>
                <input type="text" class="form-control mb-2 mr-sm-2" id="pwd2" placeholder="Enter password" name="pswd">
                <div class="form-check mb-2 mr-sm-2">
                    <label class="form-check-label">
                        <input type="checkbox" class="form-check-input" name="remember"> Remember me
                    </label>
                </div>
                <button type="submit" class="btn btn-primary mb-2">Submit</button>
            </div>
            <br>
            <div id="profile"></div>
        </div>

    </section>
    <aside>

    </aside>
    <section>
        <div class="container">
            <h2>Inline form - Bootstrap</h2>
            <article id="firstArticle">
                <p><span class="a">For the interface we will be using Bootstrap 4 – Bootstrap Swatch (will give you a customized look in
                    colors and fonts). </span><span class="b"> you need to do is to include the CDN (external link)</span>
                </p>
            </article>
                <article>
                <p>Add Bootswatch to our project https://bootswatch.com/ This will give you different variations of a
                    Bootstrap template; we will be using the <b>“Litera Template”</b>. Click on it and copy the URL and add it
                    with a link tag to your project.</p>
                    <div class="container">
                            <table style="width:100%">
                                <header>My Table</header>
                                <footer>This is the table footer section</footer>
                                    <tr>
                                      <th>An Unordered HTML List</th>
                                      <th>An Ordered HTML List</th> 
                                      <th>pragraph tags</th>
                                    </tr>
                                    <tr>
                                      <td><ul>
                                            <li>Coffee</li>
                                            <li>Tea</li>
                                            <li>Milk</li>
                                          </ul></td>
                                      <td><ol>
                                            <li>Coke</li>
                                            <li>Fanta</li>
                                            <li>Sprite</li>
                                          </ol></td> 
                                      <td><p>Beer</p>
                                        <p>Wine</p>
                                        <p>Water</p></td>
                                    </tr>                                      
                                  </table>
                                  <div>
                                        <figure>
                                                <img src="images/pic_trulli.jpg" alt="Trulli" style="width:100%">
                                                <figcaption>Fig.1 - Trulli, Puglia, Italy.</figcaption>
                                              </figure>
                                  </div>
                    </div>
                <p>Go to Bootstrap (https://getbootstrap.com/) and copy the BootstrapCSN files (JS, Popper.js, and
                    jQuery) and paste them to the bottom of your body tags.</p>
            </article>
        </div>
    </section>
    <footer class="bg-primary mb-3">
        <div class="container">
            <p>Posted by: Hege Refsnes</p>
            <p>Contact information: <a href="mailto:someone@example.com">someone@example.com</a>.</p>
        </div>
    </footer>
</body>

</html>

```
