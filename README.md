# Ex04 Simple Calculator - React Project
## Date: 26-05-2026

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
### Calculater.jsx
```jsx
import React, { useState } from "react";
import "./Calculator.css";

const Calculator = () => {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput((prev) => prev + value);
  };

  const handleClear = () => {
    setInput("");
  };

  const handleDelete = () => {
    setInput(input.slice(0, -1));
  };

  const handleCalculate = () => {
    try {
      // eval is fine for simple demo, avoid in production
      const result = input;
      setInput(result.toString());
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator">
      <input type="text" value={input} readOnly className="display" />

      <div className="buttons">
        <button onClick={handleClear}>C</button>
        <button onClick={handleDelete}>DEL</button>
        <button onClick={() => handleClick("/")}>/</button>
        <button onClick={() => handleClick("*")}>*</button>

        <button onClick={() => handleClick("7")}>7</button>
        <button onClick={() => handleClick("8")}>8</button>
        <button onClick={() => handleClick("9")}>9</button>
        <button onClick={() => handleClick("-")}>-</button>

        <button onClick={() => handleClick("4")}>4</button>
        <button onClick={() => handleClick("5")}>5</button>
        <button onClick={() => handleClick("6")}>6</button>
        <button onClick={() => handleClick("+")}>+</button>

        <button onClick={() => handleClick("1")}>1</button>
        <button onClick={() => handleClick("2")}>2</button>
        <button onClick={() => handleClick("3")}>3</button>
        <button onClick={handleCalculate}>=</button>

        <button onClick={() => handleClick("0")} className="zero">
          0
        </button>
        <button onClick={() => handleClick(".")}>.</button>
      </div>
    </div>
  );
};

export default Calculator;
```

### App.jsx 
```
import React from "react";
import Calculator from "./Calculator.jsx";

function App() {
  return (
    <div>
      <Calculator />
    </div>
  );
}

export default App;

```

### Calculator.css 
```css
.calculator {
  width: 250px;
  margin: 50px auto;
  padding: 15px;
  border-radius: 10px;
}

.display {
  width: 100%;
  height: 50px;
  font-size: 20px;
  margin-bottom: 10px;
  text-align: right;
  padding: 5px;
  border: none;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 8px;
}

button {
  height: 50px;
  font-size: 18px;
  cursor: pointer;
}

.zero {
  grid-column: span 2;
}
```

## OUTPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/09c0579a-51cd-40ed-b319-e7244301038c" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
