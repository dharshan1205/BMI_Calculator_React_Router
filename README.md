# Ex06 BMI Calculator
## Date: 23/03/2026

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
App.jsx
~~~
import React, { useState } from 'react';
import './App.css';

export default function BMI() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [result, setResult] = useState(null); // holds {bmi, message}

  const calculateBMI = (e) => {
    e.preventDefault();
    if (!weight || !height) return alert('Enter weight and height');

    const bmi = (weight / Math.pow(height / 100, 2)).toFixed(2);
    let message =
      bmi < 18.5
        ? 'Underweight'
        : bmi < 24.9
        ? 'Normal weight'
        : bmi < 29.9
        ? 'Overweight'
        : 'Obese';

    setResult({ bmi, message });
  };

  return (
    <div className="bmi-container">
      <h1>BMI Calculator</h1>
      <form onSubmit={calculateBMI}>
        <input
          type="number"
          placeholder="Weight (kg)"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
        <input
          type="number"
          placeholder="Height (cm)"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
        <button type="submit">Calculate</button>
      </form>

      {result && (
        <div className="result">
          <h2>Your BMI: {result.bmi}</h2>
          <p>Status: {result.message}</p>
        </div>
      )}
    </div>
  );
}

~~~
App.css
~~~
.bmi-container {
  text-align: center;
  margin-top: 50px;
  font-family: Arial, sans-serif;
}

form {
  margin: 20px;
}

input {
  margin: 10px;
  padding: 8px;
  width: 200px;
  font-size: 16px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

.result {
  margin-top: 20px;
  font-size: 20px;
}

~~~

## OUTPUT

<img width="1918" height="1128" alt="image" src="https://github.com/user-attachments/assets/6b997b14-b51c-4e02-9128-e23fe3fa8550" />

## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
