# Ex04 Simple Calculator - React Project
## Date: 14-02-2026

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

### Calculator.jsx
```

import { useState } from "react";

const buttons = [
  "C", "←", "/", "*",
  "7", "8", "9", "-",
  "6", "5", "4", "+",
  "1", "2", "3", "=",
  "0", ".", 
];

export default function Calculator() {

  const [value, setValue] = useState("");

  const handleClick = (btn) => {
    if (btn === "C") return setValue("");

    if (btn === "←") return setValue(value.slice(0, -1));

    if (btn === "=") {
      try {
        // Evaluate safely using Function (avoid eval for security best practice)
        setValue(String(Function("return " + value)()));
      } catch {
        setValue("Error");
      }
      return;
    }

    setValue(value + btn);
  };

  return (
    <div className="calculator">
      <input
        type="text"
        className="display"
        value={value}
        readOnly
      />

      <div className="buttons">
        {buttons.map((btn, index) => (
          <button
            key={index}
            onClick={() => handleClick(btn)}
            className={btn === "=" ? "equal" : ""}
          >
            {btn}
          </button>
        ))}
      </div>
    </div>
  );
}

```

### index.css

```

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
}

body {
  background: #f2f3f7;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.app {
  display: flex;
  justify-content: center;
  align-items: center;
}

.calculator {
  width: 300px;
  background: white;
  padding: 20px;
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

.display {
  width: 100%;
  height: 60px;
  font-size: 24px;
  padding: 10px;
  text-align: right;
  border: none;
  outline: none;
  margin-bottom: 15px;
  border-radius: 8px;
  background: #f5f5f5;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  height: 55px;
  background: #e3e7eb;
  border: none;
  font-size: 20px;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.2s;
}

button:hover {
  background: #cbd3dd;
}

button.equal {
  background: #4caf50;
  color: white;
  grid-column: span 2;
}

button.equal:hover {
  background: #398e3a;
}

@media (max-width: 400px) {
  .calculator {
    width: 90vw;
  }

  button {
    height: 50px;
    font-size: 18px;
  }
}

```

### App.jsx

```
import Calculator from "./Calculator.jsx";

function App() {
  return(
    <div className="app">
      <Calculator />
    </div>
  );
}

export default App
```


## OUTPUT
<img width="1041" height="594" alt="image" src="https://github.com/user-attachments/assets/5397dd13-2837-46a4-8c19-2e7dd6197e65" />
<img width="1047" height="595" alt="image" src="https://github.com/user-attachments/assets/92a74235-0610-4b80-ad1d-6b8a7f812ec2" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
