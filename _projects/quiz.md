---
layout: page
title: New project...in the works
description: Personality Quiz 
img: assets/img/4.png
importance: 3
category: fun
related_publications: false
---
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
            gap: 20px;
            flex-wrap: wrap; /* Ensure containers wrap on smaller screens */
        }

        .quiz-container, .result-container, .cover-container {
            width: 500px;
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            flex: 1; /* Distribute available space equally */
            margin-right: 20px; /* Spacing between containers */
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
        const questions1 = [
            {
                question: "When you travel do you?",
                answers: [
                    { text: "Stay in a 5 star hotel", category: "Transportation" },
                    { text: "Stay in the cheapest hostel you can find", category: "person who doesn't wear shoes" },
                    { text: "Stay with friends/family", category: "Environmental" },
                    { text: "YOLO, figure it out when you get there", category: "Transportation" }
                ]
            },
            {
                question: "Fav type of straw",
                answers: [
                    { text: "Paper", category: "Housing" },
                    { text: "Plastic", category: "Transportation" },
                    { text: "Silicone/glass reusable", category: "Environmental" },
                    { text: "Raw dog: no straw", category: "Environmental" }
                ]
            },
            {
                question: "Do you like the smell of gasoline?",
                answers: [
                    { text: "No", category: "Transportation" },
                    { text: "Yes", category: "Housing" }
                ]
            },
            {
                question: "The most I’ve paid a month in rent is…",
                answers: [
                    { text: "$800 (I’m not real)", category: "Transportation" },
                    { text: "$1000", category: "Housing" },
                    { text: "$1,500", category: "Environmental" },
                    { text: "$3,000 (ok, money bags)", category: "Transportation" }
                ]
            },
            {
                question: "Fav sex and the city character?",
                answers: [
                    { text: "Carrie", category: "Transportation" },
                    { text: "Charlotte", category: "Housing" },
                    { text: "Miranda", category: "Housing" },
                    { text: "Samantha", category: "Environmental" }
                ]
            },
            {
                question: "Did you drive a car in your college town?",
                answers: [
                    { text: "Yes", category: "Housing" },
                    { text: "No", category: "Transportation" }
                ]
            },
            {
                question: "What brand is your reusable water bottle?",
                answers: [
                    { text: "Owala", category: "Environmental" },
                    { text: "Hydroflask", category: "Environmental" },
                    { text: "Stanley", category: "Transportation" },
                    { text: "I use plastic…", category: "Housing" }
                ]
            },
            {
                question: "How many housemates did you have in college (not including yourself)?",
                answers: [
                    { text: "1-2", category: "Housing" },
                    { text: "3-5", category: "Transportation" },
                    { text: "6-7", category: "Environmental" },
                    { text: "8+", category: "Housing" }
                ]
            },
            {
                question: "Fav vehicle?",
                answers: [
                    { text: "Car", category: "Housing" },
                    { text: "Bus", category: "Environmental" },
                    { text: "Train", category: "Transportation" },
                    { text: "Plane", category: "Housing" }
                ]
            },
            {
                question: "Go-to pair of shoes?",
                answers: [
                    { text: "Sneakers", category: "Transportation" },
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
                    { text: "Go to campus in the morning and bring lunch so you don’t have to go back and forth between campus and home (you live by the base)
