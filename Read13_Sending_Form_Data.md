# Code 301 Reading Notes

## Read 13 Sending form Data

- Once you have data that has been validated on the client-side, it is okay to submit a from. This article covers when a user submits a form, where the data goes and how do we handle it when it gets there. 

### Client/Server Architecture
- At it's most basic, the web uses a client/server archituecture that can be summarized as follows. 

1. A web browser sends a reqest to a server
2. The server responds and sends the data back

- HTML form on a web page is nothing more than a way to configure HTTP requests to send data to a server.

### How to send the data
- A `<form>` element defines how the data will be sent. All of it'ts attributes are designed to let you configure a request to be sent when the user hits a submit button. Two important attributes are **action** and **method**.

- The **action** attribute defines where the data will be sent. The value must be a valid relative or absolute URL. If this is not provided, data will not be sent to the URL of the page containing the form

- Example HTML:

`<form action="https://example.com">`

- The **method** attribute defines how data is sent. A HTTP protocol provides several ways to perform requests, HTML form data can be transmitted via a number of different methods, the most common being **Get** and **Post**.

### The **GET** Method

- The **get** method is used by the browser to ask the server to send back a given resource. In this instance the browser would send an empty body and because the body is empty, a form will be sent using this method and append the information to the URL. 

- Example HTML:

`<form action="http://www.foo.com" method="GET">`
  `<div>`
    `<label for="say">What greeting do you want to say?</label>`
    `<input name="say" id="say" value="Hi">`
  `</div>`
  `<div>`
    `<label for="to">Who do you want to say it to?</label>`
    `<input name="to" id="to" value="Mom">`
  `</div>`
  `<div>`
    `<button>Send my greetings</button>`
  `</div>`
`</form>`

### The **POST** method
- The **post** method is a little different and is a method the browser uses to talk to the server when asking for a response. **Post** takes into account the data provided in the body of the HTTP request and has the server look at the data. The server in response will send back an appropriate result. 

- Example HTML:

`<form action="http://www.foo.com" method="POST">`
  `<div>`
    `<label for="say">What greeting do you want to say?</label>`
    `<input name="say" id="say" value="Hi">`
  `</div>`
  `<div>`
    `<label for="to">Who do you want to say it to?</label>`
    `<input name="to" id="to" value="Mom">`
  `</div>`
  `<div>`
    `<button>Send my greetings</button>`
  `</div>`
`</form>`

### Viewing HTTP Requests
- HTTP Requests are never displayed to the user, if you want to see them you need to used Developer tools. After submitting a form open up the following. 

1. Developer tools
2. Select "Network"
3. Select "All"
4. Select "foo.com" in the same table
5. Select headers

- You will be able to view the form data as shown in the image below.

<img src="https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data/network-monitor.png">

### On the server side: retrieving data
- Whichever HTTP method you choose, the server receives a string that will be parsed in order to get a list of key value pairs. 

- Example: Raw PHP

- PHP offers some global object to access the data. Presuming you have used the **Post** method, the following example just takes the data and displays it to the user. 

`<?php
  // The global $_POST variable allows you to access the data sent with the POST method by name
  // To access the data sent with the GET method, you can use $_GET
  $say = htmlspecialchars($_POST['say']);
  $to  = htmlspecialchars($_POST['to']);

  echo  $say, ' ', $to;
?>`

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)