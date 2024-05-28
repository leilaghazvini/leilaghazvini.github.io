---
layout: page
title: Quiz
description: New Project 
img: assets/img/fig_2.png
importance: 3
category: fun
related_publications: false
---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BuzzFeed Style Quiz</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="quiz-container">
        <div id="question-container">
            <div id="question">SQUIRT</div>
            <div id="answer-buttons" class="btn-container">
                <!-- Buttons will be generated here by JavaScript -->
            </div>
        </div>
        <button id="next-btn" class="btn hide">Next</button>
    </div>
    <div id="result-container" class="hide">
        <div id="result">Your result is...</div>
        <button id="restart-btn" class="btn">Restart</button>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f4f4f4;
}

#quiz-container, #result-container {
    width: 300px;
    padding: 20px;
    background-color: white;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.btn-container {
    display: flex;
    flex-direction: column;
}

.btn {
    margin: 5px 0;
    padding: 10px;
    border: none;
    border-radius: 5px;
    background-color: #007BFF;
    color: white;
    cursor: pointer;
}

.btn:hover {
    background-color: #0056b3;
}

.hide {
    display: none;
}

#next-btn, #restart-btn {
    margin-top: 20px;
}
const questions = [
    {
        question: "What is your favorite color?",
        answers: [
            { text: "Red", category: "A" },
            { text: "Blue", category: "B" },
            { text: "Green", category: "C" },
            { text: "Yellow", category: "D" }
        ]
    },
    {
        question: "What is your favorite animal?",
        answers: [
            { text: "Cat", category: "B" },
            { text: "Dog", category: "A" },
            { text: "Bird", category: "D" },
            { text: "Fish", category: "C" }
        ]
    },
    // Add more questions as needed
];

const questionContainer = document.getElementById('question-container');
const questionElement = document.getElementById('question');
const answerButtonsElement = document.getElementById('answer-buttons');
const nextButton = document.getElementById('next-btn');
const resultContainer = document.getElementById('result-container');
const resultElement = document.getElementById('result');
const restartButton = document.getElementById('restart-btn');

let currentQuestionIndex = 0;
let selectedCategories = [];

function startGame() {
    currentQuestionIndex = 0;
    selectedCategories = [];
    nextButton.classList.add('hide');
    resultContainer.classList.add('hide');
    questionContainer.classList.remove('hide');
    showQuestion(questions[currentQuestionIndex]);
}

function showQuestion(question) {
    questionElement.innerText = question.question;
    answerButtonsElement.innerHTML = '';
    question.answers.forEach(answer => {
        const button = document.createElement('button');
        button.innerText = answer.text;
        button.classList.add('btn');
        button.addEventListener('click', () => selectAnswer(answer));
        answerButtonsElement.appendChild(button);
    });
}

function selectAnswer(answer) {
    selectedCategories.push(answer.category);
    if (currentQuestionIndex < questions.length - 1) {
        currentQuestionIndex++;
        showQuestion(questions[currentQuestionIndex]);
    } else {
        showResults();
    }
}

function showResults() {
    questionContainer.classList.add('hide');
    resultContainer.classList.remove('hide');

    const result = calculateResult();
    resultElement.innerText = `Your result is: ${result}`;
}

function calculateResult() {
    const categoryCounts = selectedCategories.reduce((counts, category) => {
        counts[category] = (counts[category] || 0) + 1;
        return counts;
    }, {});

    return Object.keys(categoryCounts).reduce((a, b) => categoryCounts[a] > categoryCounts[b] ? a : b);
}

nextButton.addEventListener('click', () => {
    currentQuestionIndex++;
    nextButton.classList.add('hide');
    showQuestion(questions[currentQuestionIndex]);
});

restartButton.addEventListener('click', startGame);

startGame();
