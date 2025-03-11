# Hi there! 👋 I'm [Your Name]

Welcome to my GitHub profile! I'm a passionate developer working on exciting projects. Instead of a regular README, let's make it fun! 🎮 Play a quick game of **Tic-Tac-Toe** below:

## 🎲 Play Tic-Tac-Toe

<details>
<summary>Click to play!</summary>

⚡ **Game Rules:**
- You play as "X", the computer plays as "O".
- Click on a cell to make your move.
- First to get three in a row wins!

</details>

### 🛠 My Tech Stack:
- 🔹 Python | Django | FastAPI
- 🔹 JavaScript | React | Vue
- 🔹 MongoDB | PostgreSQL
- 🔹 Blockchain | AI/ML

---

## 🎯 Fun Quiz About Me
**Q1: What is my favorite programming language?**
- [ ] Java
- [ ] C++
- [x] Python
- [ ] JavaScript

**Q2: What project am I currently working on?**
- [ ] AI Chatbot
- [ ] Weather App
- [x] Career Mentor (AI-Based Career Guidance System)
- [ ] Blogging Platform

_(Hover over the options for the correct answers!)_

---

### 🎮 Playable Tic-Tac-Toe (For GitHub Pages)

To make the game playable, add this HTML, CSS, and JavaScript in a GitHub Pages repository:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tic-Tac-Toe</title>
    <style>
        body { text-align: center; font-family: Arial, sans-serif; }
        .board { display: grid; grid-template-columns: repeat(3, 100px); gap: 5px; justify-content: center; margin-top: 20px; }
        .cell { width: 100px; height: 100px; display: flex; align-items: center; justify-content: center; font-size: 24px; background-color: #eee; cursor: pointer; }
        .cell.taken { cursor: not-allowed; }
    </style>
</head>
<body>
    <h2>Play Tic-Tac-Toe!</h2>
    <div class="board" id="board">
        <div class="cell" onclick="makeMove(0)"></div>
        <div class="cell" onclick="makeMove(1)"></div>
        <div class="cell" onclick="makeMove(2)"></div>
        <div class="cell" onclick="makeMove(3)"></div>
        <div class="cell" onclick="makeMove(4)"></div>
        <div class="cell" onclick="makeMove(5)"></div>
        <div class="cell" onclick="makeMove(6)"></div>
        <div class="cell" onclick="makeMove(7)"></div>
        <div class="cell" onclick="makeMove(8)"></div>
    </div>
    <p id="status"></p>
    <script>
        let board = ["", "", "", "", "", "", "", "", ""];
        let currentPlayer = "X";
        function makeMove(index) {
            if (!board[index]) {
                board[index] = currentPlayer;
                document.getElementsByClassName("cell")[index].innerText = currentPlayer;
                document.getElementsByClassName("cell")[index].classList.add("taken");
                checkWinner();
                currentPlayer = currentPlayer === "X" ? "O" : "X";
            }
        }
        function checkWinner() {
            let wins = [[0,1,2], [3,4,5], [6,7,8], [0,3,6], [1,4,7], [2,5,8], [0,4,8], [2,4,6]];
            wins.forEach(pattern => {
                let [a, b, c] = pattern;
                if (board[a] && board[a] === board[b] && board[a] === board[c]) {
                    document.getElementById("status").innerText = board[a] + " Wins!";
                }
            });
        }
    </script>
</body>
</html>
