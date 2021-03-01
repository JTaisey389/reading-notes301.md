# Code 301 Reading Notes

## Read 12 EJS Partials

### EJS Partials
- Partials come in handy when you want to reuse the same HTML accros multiple veiws. Partials are like functions, they make larger websites easier to maintain so you don't have to go and change a piece of text in every page it appears in. You define a resulable bundle of code in a file and include it wherever you need it.

- Our page will look something like this:

<img src="https://miro.medium.com/max/700/0*VngdKfkNNx5f2un0.png">
<img src="https://miro.medium.com/max/700/0*oUmdAzjcwkQZb_AR.png">

- As you can see from above the same navigation bar and footer appear in both veiws. This is a great way to show canidates for partials.

- Within our code lets create a views/partials directory file that is called ***navbar.js*** 

`<!-- views/partials/navbar.ejs -->`
    `<div class="header clearfix">`
        `<nav>`
            `<ul class="nav nav-pills pull-right">`
                `<li role="presentation"><a href="/">Home</a></li>`
            `</ul>`
            `<h3 class="text-muted">Node.js Blog</h3>`
        `</nav>`
    `</div>`

***Footer***
`<!-- views/partials/footer.ejs -->`
    `<footer class="footer">`
        `<p>© 90210 Lawyer Stuff.</p>`
    `</footer>`

- Now that we have that in place we can use them in our home.ejs and post.ejs templates. 

- Create the homepage template in the veiws/home.ejs

<!-- views/home.ejs -->
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>Node.js Blog</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
        <style>
            body {
                padding-top: 20px;
                padding-bottom: 20px;
            }
            .jumbotron {
              margin-top: 10px;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <%- include('partials/navbar') %>
            <div class="jumbotron">
                <h1>All about Node</h1>
                <p class="lead">Check out our articles below!</p>
            </div>
            <div class="row">
                <div class="col-lg-12">
                    <div class="list-group">
                      <!-- loop over blog posts and render them -->
                      LIST_OF_POSTS
                    </div>
                </div>
            </div>
            <%- include('partials/footer') %>
        </div>
    </body>
    </html>

<!-- views/post.ejs -->
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>POST_TITLE | Node.js Blog</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
        <style>
            body {
                padding-top: 20px;
                padding-bottom: 20px;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <%- include('partials/navbar') %>
            <div>
                <h2>POST_TITLE</h2>
                <p>by <a href="#">POST_AUTHOR</a></p>
                <p>POST_CONTENT</p>
                <hr>
            </div>
            <%- include('partials/footer') %>
        </div>
    </body>
    </html>

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)