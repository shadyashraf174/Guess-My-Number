# **Guess My Number Game**  
#### Inspired by [Jonas Schmedtmann](https://github.com/jonasschmedtmann) || See it live at [CodePen](https://codepen.io/shady-ashraf/pen/XJrbJKL)  
###### *Guess My Number* is a simple browser-based game where players attempt to guess a randomly generated number between 1 and 20. This project demonstrates the use of basic HTML, CSS, and JavaScript for building interactive web applications.

---

## **Table of Contents**  
- [Overview](#overview)  
- [Features](#features)  
- [File Structure](#file-structure)  
- [HTML Details](#html-details)  
- [CSS Styling](#css-styling)  
- [JavaScript Logic](#javascript-logic)  
- [Deployment](#deployment)  
- [Selectors Used in the Project](#selectors-used-in-the-project)  

---

## **Overview**  
The **Guess My Number Game** challenges users to guess a number while providing feedback like "Too high" or "Too low." The game tracks the score and high score for each session.  

**Technologies used:**  
- HTML5  
- CSS3  
- JavaScript (ES6)  

---

## **Features**  
- **Random Number Generation**: A secret number is generated for every game session.  
- **User Feedback**: Dynamic messages guide the player.  
- **Score Tracking**: Displays current score and high score.  
- **Reset Option**: Players can restart the game at any time.  
- **Interactive Visuals**: Background color changes on win or loss.  

---

## **File Structure**  
```plaintext
guess-my-number/
├── index.html  
├── style.css  
└── script.js  
```  

---

## **HTML Details**  
The HTML file (`index.html`) structures the user interface of the game.  

### Key Sections:  
- **Header**:  
  Contains the game title, range information, and "Again!" button for resetting.  
  ```html  
  <header>
    <h1>Guess My Number!</h1>
    <p class="between">(Between 1 and 20)</p>
    <button class="btn again">Again!</button>
    <div class="number">?</div>
  </header>  
  ```  

- **Main**:  
  Divided into two sections:
  - **Left**: Input field for the guess and "Check!" button.  
  - **Right**: Displays game messages, score, and high score.  

---

## **CSS Styling**  
The CSS file (`style.css`) provides the retro-inspired visual style and responsive design.

### Key Styles:  
- **Theme and Font**:  
  - Dark background (`#222`) with light text (`#eee`).  
  - Retro font (`Press Start 2P`) imported via Google Fonts.  

- **Dynamic Feedback**:  
  - Background changes to green on win (`#60b347`) and red on loss (`#e3877f`).  

- **Layout**:  
  - Flexbox for centering elements.  
  - Responsive input fields and buttons for usability.  

### Snippet:  
```css  
body {
  font-family: "Press Start 2P", sans-serif;
  background-color: #222;
  color: #eee;
}
.number {
  background: #eee;
  color: #333;
  font-size: 6rem;
  width: 15rem;
  padding: 3rem 0;
  text-align: center;
}
```  

---

## **JavaScript Logic**  
The JavaScript file (`script.js`) implements the interactive functionality.  

### Key Functions:  
1. **Random Number Generation**:  
   ```javascript  
   let secretNumber = Math.trunc(Math.random() * 20) + 1;
   ```  

2. **Guess Checking**:  
   Compares user input to the secret number and provides feedback:  
   - Correct guess changes background to green and reveals the number.  
   - Incorrect guesses decrement the score and provide hints.  
   ```javascript  
   document.querySelector(".check").addEventListener("click", function () {
     const guess = Number(document.querySelector(".guess").value);
     if (!guess) {
       displayMessage("⛔️ No number!");
     } else if (guess === secretNumber) {
       displayMessage("🎉 Correct Number!");
       document.querySelector("body").style.backgroundColor = "#60b347";
     }
   });
   ```  

3. **Game Reset**:  
   Resets the game state with a new random number and default styles.  
   ```javascript  
   document.querySelector(".again").addEventListener("click", function () {
     score = 20;
     secretNumber = Math.trunc(Math.random() * 20) + 1;
     document.querySelector(".number").textContent = "?";
   });
   ```  

---

## **Deployment**  
1. Clone the repository:  
   ```bash  
   git clone https://github.com/shadyashraf174/guess-my-number.git  
   ```  
2. Open `index.html` in a web browser to play the game.  

---

## **Selectors Used in the Project**  

### **HTML Selectors**  
- **Element Selectors**:  
  - `<header>`: Defines the top section of the game.  
  - `<main>`: Contains the primary game elements.  
  - `<input>`: Accepts the player's guess.  

- **Class Selectors**:  
  - `.message`: Displays hints and feedback.  
  - `.score`: Displays the current score.  
  - `.btn`: Styles interactive buttons.  

### **CSS Selectors**  
- **Pseudo-classes**:  
  - `button:hover`: Adds hover effect to buttons.  
- **Dynamic Styling**:  
  - `body` background color changes using `style.backgroundColor`.  

---


![Screenshot 2024-12-01 011352](https://github.com/user-attachments/assets/cb91b90e-1ecb-469b-a6b2-11f4026a26ce)

![Screenshot 2024-12-01 011427](https://github.com/user-attachments/assets/e2f8d335-a673-4a64-a9d1-1d78f292c18c)

![image](https://github.com/user-attachments/assets/f57e7860-2d71-4372-88f8-5a01eab89af9)
