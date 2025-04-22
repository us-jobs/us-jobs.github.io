---
title: "Should I Quit My Job? Quiz"
layout: page
permalink: "/Quit-Job-Quiz"
---


<div class="quiz-container">
        <div class="progress-bar">
            <div class="progress" id="progress"></div>
        </div>
        <div id="quiz-content">
            <p class="question" id="question">Loading...</p>
            <div class="options" id="options"></div>
        </div>
    </div>

<script>
    const questions = [
        "💼 Do you feel valued at work?",
        "🧠 Is your job negatively impacting your mental health?",
        "📈 Do you see opportunities for growth in your company?",
        "💰 Are you fairly compensated for your work?",
        "😃 Do you feel excited about your daily tasks?",
        "⌛ Do you frequently feel overworked and exhausted?",
        "🚀 Are you learning new skills that enhance your career?",
        "⚖️ Is your work-life balance acceptable?",
        "❌ Have you considered quitting multiple times recently?",
        "💡 Do you feel inspired and motivated by your job?",
        "🏆 Do you feel recognized for your achievements?",
        "🔄 Are you stuck in repetitive tasks with no growth?",
        "📅 Do you look forward to going to work each day?",
        "🛑 Do you feel disrespected by your manager or colleagues?",
        "🌍 Do you believe your job aligns with your personal values?"
    ];

    const responses = [
        "Strongly Agree", "Agree", "Neutral", "Disagree", "Strongly Disagree", "Not Sure", "Prefer Not to Say"
    ];

    const results = {
        positive: "✅ It looks like you should consider staying! Your job still offers value and satisfaction.",
        negative: "🚨 You may want to consider quitting! Your responses indicate dissatisfaction and possible burnout.",
        neutral: "⚖️ It’s a mixed bag! Consider making a pros and cons list before deciding.",
        slightly_negative: "🤔 You seem to have some concerns. It might be worth addressing them before making a decision.",
        slightly_positive: "😊 Your job has some positive aspects, but there are areas for improvement. Consider talking to your manager.",
        extreme_negative: "🔥 Your responses indicate severe dissatisfaction. It may be time for a career change!"
    };

    let step = 0;
    let scores = [];

    function loadQuestion() {
        document.getElementById("quiz-content").innerHTML = `
            <p class="question">${questions[step]}</p>
            <div class="options">${responses.map(response => `<button onclick="handleResponse('${response}')">${response}</button>`).join('')}</div>
        `;
        updateProgress();
    }

    function handleResponse(response) {
        scores.push(responses.indexOf(response));
        if (step < questions.length - 1) {
            step++;
            loadQuestion();
        } else {
            calculateResult();
        }
    }

    function calculateResult() {
        let totalScore = scores.reduce((acc, score) => acc + score, 0);
        let finalMessage;
        
        if (totalScore < 10) {
            finalMessage = results.positive;
        } else if (totalScore < 25) {
            finalMessage = results.slightly_positive;
        } else if (totalScore < 40) {
            finalMessage = results.neutral;
        } else if (totalScore < 55) {
            finalMessage = results.slightly_negative;
        } else if (totalScore < 70) {
            finalMessage = results.negative;
        } else {
            finalMessage = results.extreme_negative;
        }
        
        document.getElementById("quiz-content").innerHTML = `
            <h2>${finalMessage}</h2>
            <button onclick='restartQuiz()'>🔄 Retake Quiz</button>
        `;
    }

    function updateProgress() {
        let progressPercent = ((step + 1) / questions.length) * 100;
        document.getElementById("progress").style.width = progressPercent + "%";
    }

    function restartQuiz() {
        step = 0;
        scores = [];
        loadQuestion();
        updateProgress();
    }

    loadQuestion();
</script>


📌 **Looking for a job?** Browse the latest listings at **[us-jobs.github.io](https://us-jobs.github.io/)**  

---