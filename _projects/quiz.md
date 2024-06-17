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

        .quiz-container, .result-container, .cover-container {
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

        .next-btn, .restart-btn, .start-btn {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <!-- Cover Page for Quiz 1 -->
    <div id="cover-container-1" class="cover-container">
        <h2>Which type of Urban Planner are you?</h2>
        <p>Urban planners work to develop and enhance various aspects of our communities. Different types of urban planners specialize in specific areas, including transportation, the environment, and housing. This quiz helps determine which type of urban planner you would be.</p>
        <button id="start-btn-1" class="btn start-btn">Start Quiz</button>
    </div>

    <!-- Quiz 1 -->
    <div id="quiz-container-1" class="quiz-container hide">
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

    <!-- Cover Page for Quiz 2 -->
    <div id="cover-container-2" class="cover-container">
        <h2>Which type of Environmental Studies Major are you?</h2>
        <p>Being an Environmental Studies major at UCSC is a very specific experience that I wish every human could experience. Hopefully this quiz can help give you a glimpse.</p>
        <button id="start-btn-2" class="btn start-btn">Start Quiz</button>
    </div>

    <!-- Quiz 2 -->
    <div id="quiz-container-2" class="quiz-container hide">
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
        function initializeQuiz(coverContainerId, startButtonId, quizContainerId, questionContainerId, questionElementId, answerButtonsElementId, nextButtonId, resultContainerId, resultElementId, restartButtonId, questions) {
            const coverContainer = document.getElementById(coverContainerId);
            const startButton = document.getElementById(startButtonId);
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

            startButton.addEventListener('click', () => {
                coverContainer.classList.add('hide');
                quizContainer.classList.remove('hide');
                startGame();
            });

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

            restartButton.addEventListener('click', () => {
                coverContainer.classList.remove('hide');
                quizContainer.classList.add('hide');
                startGame();
            });

            startGame();
        }

        initializeQuiz('cover-container-1', 'start-btn-1', 'quiz-container-1', 'question-container-1', 'question-1', 'answer-buttons-1', 'next-btn-1', 'result-container-1', 'result-1', 'restart-btn-1', questions1);
        initializeQuiz('cover-container-2', 'start-btn-2', 'quiz-container-2', 'question-container-2', 'question-2', 'answer-buttons-2', 'next-btn-2', 'result-container-2', 'result-2', 'restart-btn-2', questions2);
    </script>
</body>
</html>
