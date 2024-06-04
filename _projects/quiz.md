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
          <script>
        const questions = [
            {
                question: "Pick a college affiliation:",
                answers: [
                    { text: "Stevenson", category: "B" },
                    { text: "Crown", category: "A" },
                    { text: "Porter", category: "B" },
                    { text: "Kresge", category: "C" }
                ]
            },
            {
                question: "Fav greenhouse gas?",
                answers: [
                    { text: "Carbon Dioxide", category: "C" },
                    { text: "Methane", category: "D" },
                    { text: "Nitrous oxide ", category: "B" },
                    { text: "Hydrofluorocarbons", category: "A" }
                ]
            },
            {
                question: "How do you transport to class",
                answers: [
                    { text: "Combination of bus and walk", category: "D" },
                    { text: "Drive and park in west remote", category: "B" },
                    { text: "Bike with the dogs out (woof woof)", category: "C" },
                    { text: "Go to campus in the morning and bring lunch so you don’t have to go back and forth between campus and home (you live by the base) ", category: "A" }
                ]
            },
            {
                question: "Your ideal night out in Santa Cruz?",
                answers: [
                    { text: "That one casino by subrosa", category: "C" },
                    { text: "Surf City", category: "B" },
                    { text: "People’s disco then taco bell ", category: "D" },
                    { text: "Intimate house party (you know 1 person there and get really drunk and confuse everyone there)", category: "A" }
                ]
            },
            {
                question: "Fav sex and the city character?",
                answers: [
                    { text: "Carrie", category: "B" },
                    { text: "Charlotte", category: "D" },
                    { text: "Miranda", category: "A" },
                    { text: "Samantha", category: "C" }
                ]
            },
            {
                question: "Happy Halloween! What is your costume?",
                answers: [
                    { text: "Mario", category: "D" },
                    { text: "Luigi", category: "B" },
                    { text: "T shirt that has a formal shirt with bow tie on it ", category: "C" },
                    { text: "Generic sexy animal", category: "A" }
                ]
            },
            {
                question: "Pick an ENVS internship",
                answers: [
                    { text: "Cowell Coffee Shop", category: "D" },
                    { text: "Work on the farm (bought new overalls just for the internship and they still look brand new)", category: "C" },
                    { text: "Research at Año nuevo reserve (long bus ride complains about it to all her friends)", category: "A" },
                    { text: "Private renewable energy consulting (doesn’t actually do anything here)", category: "B" }
                ]
            },
            {
                question: "Favorite type of going out",
                answers: [
                    { text: "Forest Party", category: "C" },
                    { text: "House Show", category: "B" },
                    { text: "Bars", category: "D" },
                    { text: "Staying in and seshing", category: "A" }
                ]
            },
            {
                question: "Post grad dream job",
                answers: [
                    { text: "Low paying research position while getting masters", category: "A" },
                    { text: "Somalie", category: "D" },
                    { text: "Green peace", category: "C" },
                    { text: "Envs econ consulting", category: "B" }
                ]
            },
            {
                question: "You’re stuck on campus cramming for finals and desperate for food… What are you doing?", 
                answers: [
                    { text: "Doordash chipotle, takes 2 hours to get there and costs you your first born child (the worst bowl you’ve ever had in your life)", category: "D" },
                    { text: "Paying $8 for the dining hall- chance to reminisce", category: "B" },
                    { text: "On the prowl for a vending machine going ferrell when you find one, takes you about an hour to acomplish this mission", category: "A" },
                    { text: "Paying $20 for overpriced mediocre fusion cuisine from a food truck ", category: "C" }
                ]
            }
        ];

        function initializeQuiz(quizContainerId, questionContainerId, questionElementId, answerButtonsElementId, nextButtonId, resultContainerId, resultElementId, restartButtonId) {
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
        initializeQuiz('quiz-container-2', 'question-container-2', 'question-2', 'answer-buttons-2', 'next-btn-2', 'result-container-2', 'result-
