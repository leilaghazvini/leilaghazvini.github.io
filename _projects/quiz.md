---
layout: page
title: New project...in the works
description: New Project 
img: assets/img/4.png
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
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
            flex-wrap: wrap;
            gap: 20px;
        }

        .quiz-container, .result-container {
            width: 500px;
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

        .next-btn, .restart-btn {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div id="quiz-container-1" class="quiz-container">
        <div id="question-container-1">
            <div id="question-1">KEY</div>
            <div id="answer-buttons-1" class="btn-container">
                <!-- Buttons will be generated here by JavaScript -->
            </div>
        </div>
        <button id="next-btn-1" class="btn next-btn hide">Next</button>
    </div>
    <div id="result-container-1" class="result-container hide">
        <div id="result-1">Your result is...</div>
        <button id="restart-btn-1" class="btn restart-btn">Restart</button>
    </div>

    <div id="quiz-container-2" class="quiz-container">
        <div id="question-container-2">
            <div id="question-2">KEY</div>
            <div id="answer-buttons-2" class="btn-container">
                <!-- Buttons will be generated here by JavaScript -->
            </div>
        </div>
        <button id="next-btn-2" class="btn next-btn hide">Next</button>
    </div>
    <div id="result-container-2" class="result-container hide">
        <div id="result-2">Your result is...</div>
        <button id="restart-btn-2" class="btn restart-btn">Restart</button>
    </div>

    <script>
        const questions = [
            {
                question: "When you travel do you?",
                answers: [
                    { text: "Stay in a 5 star hotel", category: "A" },
                    { text: "Stay in the cheapest hostel you can find", category: "C" },
                    { text: "Stay with friends/family", category: "B" },
                    { text: "YOLO, figure it out when you get there", category: "A" }
                ]
            },
            {
                question: "Fav type of straw",
                answers: [
                    { text: "Paper", category: "C" },
                    { text: "Plastic", category: "A" },
                    { text: "Silicone/glass reusable", category: "B" },
                    { text: "Raw dog: no straw", category: "B" }
                ]
            },
            {
                question: "Do you like the smell of gasoline?",
                answers: [
                    { text: "No", category: "A" },
                    { text: "Yes", category: "C" }
                ]
            },
            {
                question: "The most I’ve paid a month in rent is…",
                answers: [
                    { text: "$800 (I’m not real)", category: "A" },
                    { text: "$1000", category: "C" },
                    { text: "$1,500", category: "B" },
                    { text: "$3,000 (ok, money bags)", category: "A" }
                ]
            },
            {
                question: "Fav sex and the city character?",
                answers: [
                    { text: "Carrie", category: "A" },
                    { text: "Charlotte", category: "C" },
                    { text: "Miranda", category: "C" },
                    { text: "Samantha", category: "B" }
                ]
            },
            {
                question: "Did you drive a car in your college town?",
                answers: [
                    { text: "Yes", category: "C" },
                    { text: "No", category: "A" }
                ]
            },
            {
                question: "What brand is your reusable water bottle?",
                answers: [
                    { text: "Owala", category: "B" },
                    { text: "Hydroflask", category: "B" },
                    { text: "Stanley", category: "A" },
                    { text: "I use plastic…", category: "C" }
                ]
            },
            {
                question: "How many housemates did you have in college (not including yourself)?",
                answers: [
                    { text: "1-2", category: "C" },
                    { text: "3-5", category: "A" },
                    { text: "6-7", category: "B" },
                    { text: "8+", category: "C" }
                ]
            },
            {
                question: "Fav vehicle?",
                answers: [
                    { text: "Car", category: "C" },
                    { text: "Bus", category: "B" },
                    { text: "Train", category: "A" },
                    { text: "Plane", category: "C" }
                ]
            },
            {
                question: "Go-to pair of shoes?",
                answers: [
                    { text: "Sneakers", category: "A" },
                    { text: "Running shoe", category: "B" },
                    { text: "Boot", category: "C" },
                    { text: "Sandals", category: "B" }
                ]
            }
        ];

        function initializeQuiz(quizContainerId, questionContainerId, questionElementId, answerButtonsElementId, nextButtonId, resultContainerId, resultElementId, restartButtonId) {
            const quizContainer = document.getElementById(quizContainerId);
            const questionContainer = document.getElementById(questionContainerId);
            const questionElement = document.getElementById(questionElementId);
            const answerButtonsElement = document.getElementById(answerButtonsElementId);
            const nextButton = document.getElementById(nextButtonId);
            const resultContainer = document.getElementById(resultContainerId);
            const resultElement = document.getElementById(resultElementId);
            const restartButton = document.getElementById(restartButtonId);

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
        }

        initializeQuiz('quiz-container-1', 'question-container-1', 'question-1', 'answer-buttons-1', 'next-btn-1', 'result-container-1', 'result-1', 'restart-btn-1');
        initializeQuiz('quiz-container-2', 'question-container-2', 'question-2', '

