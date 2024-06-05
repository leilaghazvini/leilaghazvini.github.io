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
        const questions1 = [
            {
                question: "When you travel do you?",
                answers: [
                    { text: "Stay in a 5 star hotel", category: "Transortation" },
                    { text: "Stay in the cheapest hostel you can find", category: "person who doesn't wear shoes" },
                    { text: "Stay with friends/family", category: "Environmental" },
                    { text: "YOLO, figure it out when you get there", category: "Transortation" }
                ]
            },
            {
                question: "Fav type of straw",
                answers: [
                    { text: "Paper", category: "Housing" },
                    { text: "Plastic", category: "Transortation" },
                    { text: "Silicone/glass reusable", category: "Environmental" },
                    { text: "Raw dog: no straw", category: "Environmental" }
                ]
            },
            {
                question: "Do you like the smell of gasoline?",
                answers: [
                    { text: "No", category: "Transortation" },
                    { text: "Yes", category: "Housing" }
                ]
            },
            {
                question: "The most I’ve paid a month in rent is…",
                answers: [
                    { text: "$800 (I’m not real)", category: "Transortation" },
                    { text: "$1000", category: "Housing" },
                    { text: "$1,500", category: "Environmental" },
                    { text: "$3,000 (ok, money bags)", category: "Transortation" }
                ]
            },
            {
                question: "Fav sex and the city character?",
                answers: [
                    { text: "Carrie", category: "Transortation" },
                    { text: "Charlotte", category: "Housing" },
                    { text: "Miranda", category: "Housing" },
                    { text: "Samantha", category: "Environmental" }
                ]
            },
            {
                question: "Did you drive a car in your college town?",
                answers: [
                    { text: "Yes", category: "Housing" },
                    { text: "No", category: "Transortation" }
                ]
            },
            {
                question: "What brand is your reusable water bottle?",
                answers: [
                    { text: "Owala", category: "Environmental" },
                    { text: "Hydroflask", category: "Environmental" },
                    { text: "Stanley", category: "Transortation" },
                    { text: "I use plastic…", category: "Housing" }
                ]
            },
            {
                question: "How many housemates did you have in college (not including yourself)?",
                answers: [
                    { text: "1-2", category: "Housing" },
                    { text: "3-5", category: "Transortation" },
                    { text: "6-7", category: "Environmental" },
                    { text: "8+", category: "Housing" }
                ]
            },
            {
                question: "Fav vehicle?",
                answers: [
                    { text: "Car", category: "Housing" },
                    { text: "Bus", category: "Environmental" },
                    { text: "Train", category: "Transortation" },
                    { text: "Plane", category: "Housing" }
                ]
            },
            {
                question: "Go-to pair of shoes?",
                answers: [
                    { text: "Sneakers", category: "Transortation" },
                    { text: "Running shoe", category: "Environmental" },
                    { text: "Boot", category: "Housing" },
                    { text: "Sandals", category: "Environmental" }
                ]
            }
        ];

        const questions2 = [
            {
                question: "Pick a college affiliation:",
                answers: [
                    { text: "Stevenson", category: "tall white guy with curly brown hair" },
                    { text: "Crown", category: "Research STEM Queen" },
                    { text: "Porter", category: "Alaina" },
                    { text: "Kresge", category: "person who doesn't wear shoes" }
                ]
            },
            {
                question: "Fav greenhouse gas?",
                answers: [
                    { text: "Carbon Dioxide", category: "person who doesn't wear shoes" },
                    { text: "Methane", category: "Alaina" },
                    { text: "Nitrous oxide ", category: "tall white guy with curly brown hair" },
                    { text: "Hydrofluorocarbons", category: "Research STEM Queen" }
                ]
            },
            {
                question: "How do you transport to class",
                answers: [
                    { text: "Combination of bus and walk", category: "Alaina" },
                    { text: "Drive and park in west remote", category: "tall white guy with curly brown hair" },
                    { text: "Bike with the dogs out (woof woof)", category: "person who doesn't wear shoes" },
                    { text: "Go to campus in the morning and bring lunch so you don’t have to go back and forth between campus and home (you live by the base) ", category: "Research STEM Queen" }
                ]
            },
            {
                question: "Your ideal night out in Santa Cruz?",
                answers: [
                    { text: "That one casino by subrosa", category: "person who doesn't wear shoes" },
                    { text: "Surf City", category: "tall white guy with curly brown hair" },
                    { text: "People’s disco then taco bell ", category: "Alaina" },
                    { text: "Intimate house party (you know 1 person there and get really drunk and confuse everyone there)", category: "Research STEM Queen" }
                ]
            },
            {
                question: "Fav sex and the city character?",
                answers: [
                    { text: "Carrie", category: "tall white guy with curly brown hair" },
                    { text: "Charlotte", category: "Alaina" },
                    { text: "Miranda", category: "Research STEM Queen" },
                    { text: "Samantha", category: "person who doesn't wear shoes" }
                ]
            },
            {
                question: "Happy Halloween! What is your costume?",
                answers: [
                    { text: "Mario", category: "Alaina" },
                    { text: "Luigi", category: "tall white guy with curly brown hair" },
                    { text: "T shirt that has a formal shirt with bow tie on it ", category: "person who doesn't wear shoes" },
                    { text: "Generic sexy animal", category: "Research STEM Queen" }
                ]
            },
            {
                question: "Pick an ENVS internship",
                answers: [
                    { text: "Cowell Coffee Shop", category: "Alaina" },
                    { text: "Work on the farm (bought new overalls just for the internship and they still look brand new)", category: "person who doesn't wear shoes" },
                    { text: "Research at Año nuevo reserve (long bus ride complains about it to all her friends)", category: "Research STEM Queen" },
                    { text: "Private renewable energy consulting (doesn’t actually do anything here)", category: "tall white guy with curly brown hair" }
                ]
            },
            {
                question: "Favorite type of going out",
                answers: [
                    { text: "Forest Party", category: "person who doesn't wear shoes" },
                    { text: "House Show", category: "tall white guy with curly brown hair" },
                    { text: "Bars", category: "Alaina" },
                    { text: "Staying in and seshing", category: "Research STEM Queen" }
                ]
            },
            {
                question: "Post grad dream job",
                answers: [
                    { text: "Low paying research position while getting masters", category: "Research STEM Queen" },
                    { text: "Somalie", category: "Alaina" },
                    { text: "Green peace", category: "person who doesn't wear shoes" },
                    { text: "Envs econ consulting", category: "tall white guy with curly brown hair" }
                ]
            },
            {
                question: "You’re stuck on campus cramming for finals and desperate for food… What are you doing?", 
                answers: [
                    { text: "Doordash chipotle, takes 2 hours to get there and costs you your first born child (the worst bowl you’ve ever had in your life)", category: "Alaina" },
                    { text: "Paying $8 for the dining hall- chance to reminisce", category: "tall white guy with curly brown hair"" },
                    { text: "On the prowl for a vending machine going ferrell when you find one, takes you about an hour to acomplish this mission", category: "Research STEM Queen" },
                    { text: "Paying $20 for overpriced mediocre fusion cuisine from a food truck ", category: "person who doesn't wear shoes" }
                ]
            }
        ];

        function initializeQuiz(quizContainerId, questionContainerId, questionElementId, answerButtonsElementId, nextButtonId, resultContainerId, resultElementId, restartButtonId, questions) {
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

        initializeQuiz('quiz-container-1', 'question-container-1', 'question-1', 'answer-buttons-1', 'next-btn-1', 'result-container-1', 'result-1', 'restart-btn-1', questions1);
        initializeQuiz('quiz-container-2', 'question-container-2', 'question-2', 'answer-buttons-2', 'next-btn-2', 'result-container-2', 'result-2', 'restart-btn-2', questions2);
    </script>
</body>
</html>
