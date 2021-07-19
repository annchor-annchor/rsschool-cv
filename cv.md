# Anna Fomina
###### City: *St.Petersburg, Russia*
###### Pnone: *+7-953-175-15-54*
###### Email: *fomina2.ad@gmail.com*
###### Telegram: *@annchor_annchor*
###### Portfolio: *https://gist.github.com/annchor-annchor*

### Front End Developer Intern
Front End Developer intern with basic knowledge and working experience with **JavaScript**, **HTML/CSS** to deliver the best results in Internship Programm. Adept at finding independent and creative solutions, contributing to a highly-collaborative work environment and determening project goals.  

## Education
* #### Peter the Great St.Petersburg Polytechnic University (*2019 - 2023*) - Bachelor's Business Analytics
* #### Google Ads Certification (2021) - Search, Display, Video and Shopping Ads
* #### The Complete Web-Development Bootcamp Certificate (2021) - JavaSCript, HTML/CSS Courses
* #### The Complete Python Bootcamp CErtificate (2020) - Python Basics Courses

## Experience
**2016 - 2018** - Copywriting, rewriting and translating multi-tematic texts on freelance platform for text-editors;  
**2021 - Present** - Linkbuilding and WordPress blog's posting in a Digital Agency;  
**2021 - Present** - Teaching English lesson for kids in a local English club;  

## Code Examples
1. Simple Weather Forecast Web-Interface using *API data*:
```javascript
// Requring Necessary Frameworks
const express = require("express");
const https = require("https");
const bodyParser = require("body-parser");
const app = express();

// Getting The Main Page
app.use('*/css',express.static('public/css'));
app.use(bodyParser.urlencoded({extended:true}));
app.get("/", function(req,res){
	res.sendFile(__dirname+"/index.html");
});

// Getting Info From User
app.post("/",function(req,res){
	const query = req.body.cityName;
	const apiKey = "c832e40bf02b89a3ee87a27f8a923a25";
	const units = "metric";
	const url = "https://api.openweathermap.org/data/2.5/weather?q="+query+"&appid="+apiKey+"&units="+units+"";
	https.get(url, function(response){
		console.log(response);

// Preparing Response
	response.on("data", function(data){
		const weatherData = JSON.parse(data);
		const temp = weatherData.main.temp;
		const description = weatherData.weather[0].description;
		const icon = weatherData.weather[0].icon;
		const imgURL = "https://openweathermap.org/img/wn/"+icon+"@2x.png";	

// Sending Response
		if (response.statusCode === 200) {
			res.write("<style>@import url('https://fonts.googleapis.com/css2?family=Caveat:wght@700&family=Inconsolata:wght@300&family=Montserrat:wght@200&display=swap');body{background-color: #1a508b;text-align: center;margin: 15% 20% 0% 20%;font-family: 'Montserrat';font-size: 1rem;color: #fff3e6;} img {border-radius: 50%;background-color: #fff3e6;} h1 {font-size: 3.5rem;font-family: 'Caveat';text-shadow: 3px 1px 0 #0d335d;margin-bottom: 10px;} h3:hover{color:#c0e218;} h1:hover{color:#c0e218;}</style><h1>The temperature in "+query+" is "+temp+" C</h1>");
			res.write("<h3>The weather is currently "+description+".</h3>");
			res.write("<img src="+imgURL+">");
			res.send();
		}});
	});
});

app.listen(3000, function() {
	console.log("Server is running on port 3000");
});
```
2. Daily Activities Keeper - To Do Web-Interface using *React and EJS*
```javascript
import React, { useState } from "react";
import Header from "./components/Header.jsx";
import Footer from "./components/Footer.jsx";
import Note from "./components/Note.jsx";
import CreateArea from "./components/CreateArea.jsx";

function App() {
  const [notes, setNotes] = useState([]);

  function addNote(note) {
    setNotes((prevNotes) => {
      return [...prevNotes, note];
    });
  }

  function deleteNote(id) {
    setNotes((prevNotes) => {
      return prevNotes.filter((note, index) => {
        return index !== id;
      });
    });
  }

  return (
    <div>
      <Header />
      <CreateArea onAdd={addNote} />
      {notes.map((note, index) => {
        return (
          <Note
            key={index}
            id={index}
            title={note.title}
            content={note.content}
            onDelete={deleteNote}
          />
        );
      })}
      <Footer />
    </div>
  );
}

export default App;
```
```javascript
import React from "react";
import ReactDOM from "react-dom";
import App from "./App.jsx";

ReactDOM.render(<App />, document.getElementById("root"));
```javascript
import React, { useState } from "react";

function CreateArea(props) {
  const [note, setNote] = useState({
    title: "",
    content: ""
  });

  function handleChange(event) {
    const { name, value } = event.target;

    setNote((prevNote) => {
      return {
        ...prevNote,
        [name]: value
      };
    });
  }

  function handleClick(event) {
    props.onAdd(note);
    setNote({
      title: "",
      content: ""
    });
    event.preventDefault();
  }

  return (
    <div>
      <form className="note-area">
        <input
          name="title"
          onChange={handleChange}
          placeholder="Title"
          value={note.title}
        ></input>
        <textarea
          name="content"
          onChange={handleChange}
          placeholder="Take a note..."
          rows="3"
          value={note.content}
        ></textarea>
        <button onClick={handleClick}>+</button>
      </form>
    </div>
  );
}

export default CreateArea;
```
```javascript
import React from "react";

const year = new Date().getFullYear();

function Footer() {
  return (
    <footer>
      <p>Copyright {year}</p>
    </footer>
  );
}

export default Footer;
```
```javascript
import React from "react";

function Header() {
  return (
    <div className="header">
      <img
        src="https://www.flaticon.com/svg/vstatic/svg/2645/2645883.svg?token=exp=1612208813~hmac=3522641b05b4d0e5ef8cfdbbee9ffd16"
        alt="bell-img"
      />
      <h1>Keeper App</h1>
    </div>
  );
}

export default Header;
```
```javascript
import React from "react";

function Note(props) {
  function handleClick() {
    props.onDelete(props.id);
  }

  return (
    <div className="note">
      <h1>{props.title}</h1>
      <p>{props.content}</p>
      <button onClick={handleClick}>🗑</button>
    </div>
  );
}

export default Note;
```
### Foreign Languages
English - C1 (*Uncertified*)

### Personal Traits
* *Organised, accurate and detail-oriented*
* *Flexible and adaptable to changes*
* *Quick learner*
* *Determined*


