# Ex04 Simple Calculator - React Project
## Name: POOJASRI L
## Reg.no: 212223220076
## Date:21/09/2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM

### APP.js
```
import React, { useState } from 'react'; 
import './App.css';
import { evaluate } from 'mathjs';

function App() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === 'AC') {
      setInput('');
    } else if (value === '⌫') {
      setInput(input.slice(0, -1));
    } else if (value === '=') {
      try {
        setInput(evaluate(input).toString());
      } catch {
        setInput('Error');
      }
    } else {
      setInput((prev) => prev + value);
    }
  };

  const buttons = [
    'AC', '⌫', '%', '/',
    '7', '8', '9', '*',
    '4', '5', '6', '-',
    '1', '2', '3', '+',
    '00', '0', '.', '='
  ];

  return (
    <div className="calculator">
      <div className="display">{input || '0'}</div>
      <div className="buttons">
        {buttons.map((btn, i) => (
          <button
            key={i}
            className={`button 
              ${btn === '=' ? 'equal' : ''} 
              ${btn === 'AC' || btn === '⌫' ? 'special' : ''}`}
            onClick={() => handleClick(btn)}
          >
            {btn}
          </button>
        ))}
      </div>
    </div>
  );
}

export default App;
```
### APP.css
```
.calculator {
  max-width: 320px;
  margin: 50px auto;
  border-radius: 20px;
  box-shadow: 0px 10px 25px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  background-color: #1c1c1c;
  color: white;
  font-family: 'Arial', sans-serif;
}

.display {
  background-color: #1c1c1c;
  padding: 20px;
  font-size: 2.5em;
  text-align: right;
  color: white;
  min-height: 80px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

.button {
  padding: 25px;
  font-size: 1.5em;
  border: 1px solid #333;
  background-color: #505050;
  color: white;
  cursor: pointer;
}

.button:nth-child(4n) {
  background-color: #ff9500;
  color: white;
}

.button.equal {
  background-color: #28a745;
  color: white;
}

.button:nth-child(-n+3) {
  background-color: #d4d4d2;
  color: black;
}

.button:active {
  opacity: 0.8;
}

```

## OUTPUT
<img width="1919" height="1079" alt="Screenshot 2025-09-21 144049" src="https://github.com/user-attachments/assets/3efd512a-a786-4e89-afdb-67da3a17e073" />

<img width="1918" height="1079" alt="Screenshot 2025-09-21 144101" src="https://github.com/user-attachments/assets/984786c3-a8fd-41c6-92f5-3073e2497b5a" />

<img width="1919" height="1079" alt="Screenshot 2025-09-21 144109" src="https://github.com/user-attachments/assets/449d5c4b-ee55-4ada-be3c-3bf238639a19" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
