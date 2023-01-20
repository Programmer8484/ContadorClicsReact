# ContadorClicsReact
Contador de clics, creado con React y responsive.

//App.js
import './App.css';
import Boton from './componentes/Boton';
import Contador from './componentes/contador';
import { useState } from 'react';


function App() {

  const [numClics, setNumClics] = useState(0);

  const manejarClic = () => {
    setNumClics(numClics + 1);
  };

  const reiniciarContador = () => {
    setNumClics(0);
  };

  return (
    <div className="App">
      <div className='Cont-contador'>
        <Contador numClics={numClics} />
        <Boton
        texto='Clic'
        esBotonDeClic={true}
        manejarClic={manejarClic} />
        <Boton
        texto='Reiniciar'
        esBotonDeClic={false}
        manejarClic={reiniciarContador} />
      </div>
    </div>
  );
}

export default App;

/*App.css*/
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box; /*Propiedades de ancho y alto*/
}

html, body{
  background-color: black;
}

.Cont-contador{
  height: 550px;
  min-width: 600px;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

@media(max-width: 700px) {
  body, html{
    background-color: brown;
  }
}

@media(max-width: 400px) {
  body,
  html{
    background-color: blue;
  }

  .Cont-contador{
    height: 300px;
    min-width: 300px;
    flex: none;
  }
}

//Boton.js
import './Hojas-de-estilo/Boton.css';

function Boton({texto, esBotonDeClic, manejarClic}) { /*Dos espacios para JS. Props sólo con texto (parámetro que recibe la función)*/ 
  return(
    <button
    className={ esBotonDeClic ? 'boton-clic':'boton-reiniciar' }
    onClick={manejarClic}>
      {texto} 
    </button>
  );
}

export default Boton;

/*Boton.css*/
button{
  width: 250px;
  height: 80px;
  font-family: 'Courier New', Courier, monospace;
  font-weight: bold;
  color: black;
  border: 2px solid aqua;
  border-radius: 15px;
  margin: 5px;
  font-size: 30px;
  cursor: pointer;
  align-content: center;
}

button:hover{
  background-color: green; 
}

.boton-clic{
  background-color: brown;
}

.boton-reiniciar{
  background-color: blue;
}


@media(max-width: 700px) {
  button{
    width: 250px;
    height: 80px;
    font-family: 'Courier New', Courier, monospace;
    font-weight: bold;
    color: black;
    border: 2px solid aqua;
    border-radius: 15px;
    margin: 5px;
    font-size: 30px;
    cursor: pointer;
    align-content: center;
  }
}

@media(max-width: 400px) {
  button{
    width: 150px;
    height: 50px;
    font-family: 'Courier New', Courier, monospace;
    font-weight: bold;
    color: black;
    border: 2px solid aqua;
    border-radius: 15px;
    margin: 5px;
    font-size: 25px;
    cursor: pointer;
    align-content: center;
    float: left;
  }
}

//Contador.js
import React from 'react';
import './Hojas-de-estilo/Contador.css';

function Contador ({ numClics }){
  return(
    <div className='contador'>
      {numClics}
    </div>
  );
}

export default Contador;

/*Contador.css*/
.contador{
  min-width: 300px; 
  height: 300px;
  font-size: 150px;
  padding: 25px;
  color: gold;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 10px solid white;
  margin-bottom: 20px;
}

@media(max-width: 700px) {
  .contador{
    min-width: 300px; 
    height: 300px;
    font-size: 150px;
    padding: 25px;
    color: gold;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 10px solid white;
    margin-bottom: 20px;
  }
}

@media(max-width: 400px) {
  .contador{
    min-width: 150px; 
    height: 150px;
    font-size: 90px;
    padding: 25px;
    color: gold;
    border: 10px solid white;
    margin-bottom: 20px;
  }
}

//Package.jeson.
{
  "name": "contador-clics",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.16.5",
    "@testing-library/react": "^13.4.0",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}
