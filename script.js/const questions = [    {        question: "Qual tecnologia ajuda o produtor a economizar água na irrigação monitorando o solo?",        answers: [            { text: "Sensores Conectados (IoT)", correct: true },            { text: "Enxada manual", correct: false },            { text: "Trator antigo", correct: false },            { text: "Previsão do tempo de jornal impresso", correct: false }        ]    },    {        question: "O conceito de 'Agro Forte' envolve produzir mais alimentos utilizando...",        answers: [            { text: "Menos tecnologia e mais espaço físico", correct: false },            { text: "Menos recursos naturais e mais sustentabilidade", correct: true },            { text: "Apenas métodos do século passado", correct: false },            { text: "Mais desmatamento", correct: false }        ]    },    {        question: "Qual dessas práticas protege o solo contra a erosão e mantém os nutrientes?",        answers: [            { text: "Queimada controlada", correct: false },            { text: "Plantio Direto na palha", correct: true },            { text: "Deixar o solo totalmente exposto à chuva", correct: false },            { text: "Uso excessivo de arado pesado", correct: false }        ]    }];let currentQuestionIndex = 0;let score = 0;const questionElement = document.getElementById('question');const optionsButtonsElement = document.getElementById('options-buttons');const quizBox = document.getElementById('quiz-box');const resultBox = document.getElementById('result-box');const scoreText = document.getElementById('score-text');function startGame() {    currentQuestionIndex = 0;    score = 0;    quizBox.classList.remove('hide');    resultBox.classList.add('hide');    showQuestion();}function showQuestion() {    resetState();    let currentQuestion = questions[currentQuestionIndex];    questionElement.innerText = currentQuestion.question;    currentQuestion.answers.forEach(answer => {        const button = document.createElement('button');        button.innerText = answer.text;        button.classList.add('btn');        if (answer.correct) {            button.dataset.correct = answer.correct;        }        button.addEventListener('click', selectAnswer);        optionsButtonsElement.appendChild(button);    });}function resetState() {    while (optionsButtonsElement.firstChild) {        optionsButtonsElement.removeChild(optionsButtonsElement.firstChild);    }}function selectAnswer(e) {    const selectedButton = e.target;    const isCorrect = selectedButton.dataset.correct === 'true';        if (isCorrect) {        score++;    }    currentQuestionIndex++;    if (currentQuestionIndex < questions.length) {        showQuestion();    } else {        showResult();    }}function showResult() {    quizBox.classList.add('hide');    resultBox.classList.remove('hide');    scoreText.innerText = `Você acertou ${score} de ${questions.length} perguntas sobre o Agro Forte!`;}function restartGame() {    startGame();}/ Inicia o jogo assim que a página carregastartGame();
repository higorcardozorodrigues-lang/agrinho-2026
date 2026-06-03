const questions = [
    {
        question: "Qual tecnologia ajuda o produtor a economizar água na irrigação monitorando o solo?",
        answers: [
            { text: "Sensores Conectados (IoT)", correct: true },
            { text: "Enxada manual", correct: false },
            { text: "Trator antigo", correct: false },
            { text: "Previsão do tempo de jornal impresso", correct: false }
        ]
    },
    {
        question: "O conceito de 'Agro Forte' envolve produzir mais alimentos utilizando...",
        answers: [
            { text: "Menos tecnologia e mais espaço físico", correct: false },
            { text: "Menos recursos naturais e mais sustentabilidade", correct: true },
            { text: "Apenas métodos do século passado", correct: false },
            { text: "Mais desmatamento", correct: false }
        ]
    },
    {
        question: "Qual dessas práticas protege o solo contra a erosão e mantém os nutrientes?",
        answers: [
            { text: "Queimada controlada", correct: false },
            { text: "Plantio Direto na palha", correct: true },
            { text: "Deixar o solo totalmente exposto à chuva", correct: false },
            { text: "Uso excessivo de arado pesado", correct: false }
        ]
    }
];

let currentQuestionIndex = 0;
let score = 0;

const questionElement = document.getElementById('question');
const optionsButtonsElement = document.getElementById('options-buttons');
const quizBox = document.getElementById('quiz-box');
const resultBox = document.getElementById('result-box');
const scoreText = document.getElementById('score-text');

function startGame() {
    currentQuestionIndex = 0;
    score = 0;
    quizBox.classList.remove('hide');
    resultBox.classList.add('hide');
    showQuestion();
}

function showQuestion() {
    resetState();
    let currentQuestion = questions[currentQuestionIndex];
    questionElement.innerText = currentQuestion.question;

    currentQuestion.answers.forEach(answer => {
        const button = document.createElement('button');
        button.innerText = answer.text;
        button.classList.add('btn');
        if (answer.correct) {
            button.dataset.correct = answer.correct;
        }
        button.addEventListener('click', selectAnswer);
        optionsButtonsElement.appendChild(button);
    });
}

function resetState() {
    while (optionsButtonsElement.firstChild) {
        optionsButtonsElement.removeChild(optionsButtonsElement.firstChild);
    }
}

function selectAnswer(e) {
    const selectedButton = e.target;
    const isCorrect = selectedButton.dataset.correct === 'true';
    
    if (isCorrect) {
        score++;
    }

    currentQuestionIndex++;
    if (currentQuestionIndex < questions.length) {
        showQuestion();
    } else {
        showResult();
    }
}

function showResult() {
    quizBox.classList.add('hide');
    resultBox.classList.remove('hide');
    scoreText.innerText = `Você acertou ${score} de ${questions.length} perguntas sobre o Agro Forte!`;
}

function restartGame() {
    startGame();
}

// Inicia o jogo assim que a página carrega
startGame();