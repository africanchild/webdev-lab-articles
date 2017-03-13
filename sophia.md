# 13/03/2017 Igbinedion Daniel 
# created the HTML script using text editor "Atom";
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Static-Bot</title>
    <link rel="stylesheet" href="css/javis.css">
  </head>
  <body>
    <header>
      <h1>Static-Bot</h1>
    </header>
    <div class="wrapper">
      <h2 id="default-msg"><span class="hello">SOPHIE:</span> Hello please type in your command, type in <i>help</i> to view my functions.</h2>
      <div id="chat-area"></div>
      <input type="text" id="userInput">
      <button type="button" id="response" name="button">Send</button>
    </div>
  </body>
  <script src="js/javis.js"></script>
</html>
```
## the color editing functionalities was done on an
  external css then linked to the above HTML script.
  This was done with with the link tag;

  ```css
  body {
    font-family: cursive;
    font-size: 16px;
    padding: 0;
    margin: 0;
    line-height: 1.4;
    background: grey;
  }
  header {
    background-color: #03A9F4;
    padding: 14px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  }

  h1, h2, {
    font-weight: 300;
  }
  header > h1 {
    font-weight: 300;
    font-size: 40px
    color: #FFFFFF;
    text-align: center;
  }

  .wrapper {
    max-width: 100%;
    width: 50%;
    margin: auto;
  }
  .hello {
    color: red;
    font: 35px;
    font-weight: bolder;
  }
  input[type=text] {
    width: 100%;
    font-size: 16pt;
    transition: all 0.4s ease-in-out;
    padding: 10px;
    -webkit-appearance: none;
    line-height: 1.4285713;
    color: #555;
    border: 1px solid #ccc;
    margin-top: 20px !important;
  }
  button {
    border: none;
    background: chocolate;
    padding: 12px 12px;
    font-size: 16pt;
    float: right;
    width: 100px;
    color: #fff;
    display: inline;
    align-self: center;
    margin-top: 3px;
    border-radius: 20px;
    cursor: pointer;
    transition: all 0.4s ease-in-out;
  }
  button:hover {
    background: #ee22ed;
  }

  input:focus, button:focus {
    outline: none;
  }
  #chat-area {
    font-size: 1.5em;
    font-style: italic;
  }
```
### obviously javascript is needed to input commands and functions and my designed bot has a few commands but you could add extra to make it look smarter;
Here is my javascript for my bot 'Sophie';
```javascript
var userInput = document.getElementById('userInput');
var btn = document.getElementById('response');
var chatArea = document.getElementById('chat-area');

function kill() {
  window.open("media/AUD-20170213-WA0016.mp3",
'_self');
};
var commands = [
  ['hi', ['hello!', 'hey']],
  ['hello', 'how are you?'],
  ['fine', 'pretty cool'],
  ["what's up", 'fine and you?'],
  ['who are you', 'I am Sophie: developed assistant for you'],
  ['who created you', 'confindential but i was made in NIGERIA.'],
  ['are you funny', 'not really but i could get jokes online for you'],
  ['self_destruct', 'lol' ],
  ['help'],
];
var defaultMsg = "Sorry! Didn't understand your request, could we try again."

btn.addEventListener("click", function() {
  chatArea.innerHTML += "<p class='user'><b>You: " + userInput.value + "</p><br>";

  for (i = 0; i < commands.length; i++) {
    if (userInput.value == commands[i][0]) {
      var match = true;
      for (ii = 0; ii < commands[0][0][1].length; ii++) {
        if (userInput.value == commands[i][0]) {
          var rand = Math.floor(Math.random() * commands[ii][1].length);
          var rep = commands[ii][1][rand];
          // var match = true;
          // var response = commands[i][1];
      }
    }
  }
    var response = commands[i][1];
    if (userInput.value == 'self_destruct' || userInput.value == 'destroy' ||
    userInput.value == 'selfdestruct' || userInput.value == 'kill') {
      kill();
    }
  }
  if (userInput.value == 'help') {
    chatArea.innerHTML += "Sophie: ";
    for (ii = 0; ii < commands.length; ii++) {
      chatArea.innerHTML += commands[ii][0] + "<br>";
  }
  return;
  }
  if (!match) {
    setTimeout(function() {
      chatArea.innerHTML += "<p class='jarvis'><b>Sophie: </b>" + defaultMsg + "</p><br>";
    }, 3000);
  } else {
    setTimeout(function() {
      chatArea.innerHTML += "<p class='jarvis'><b>Sophie: </b>" + response + "</p><br>";
    }, 2000);
  }
});
```

