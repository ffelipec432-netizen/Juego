<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Rompecabezas Educativo</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #1e1e2f, #2a2a4a);
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
    }

    #score-board {
      font-size: 1.5rem;
      font-weight: bold;
      margin: 10px;
      padding: 10px 20px;
      background: #00ffcc;
      color: #111;
      border-radius: 12px;
      box-shadow: 0 0 15px #00ffcc;
      animation: pulse 1.5s infinite;
    }

    @keyframes pulse {
      0% { box-shadow: 0 0 10px #00ffcc; }
      50% { box-shadow: 0 0 25px #00ffcc; }
      100% { box-shadow: 0 0 10px #00ffcc; }
    }

    #puzzle-board {
      position: relative;
      width: 600px;
      height: 600px;
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      grid-template-rows: repeat(4, 1fr);
      background: url('https://www.uautonoma.cl/content/uploads/2023/07/maltrato-infantil-1.jpg') no-repeat center;
      background-size: cover;
      border: 4px solid #00ffcc;
      border-radius: 16px;
      overflow: hidden;
    }

    .tile {
      background: rgba(0,0,0,0.85);
      border: 1px solid #333;
      cursor: pointer;
      transition: opacity 0.5s;
    }

    .tile.revealed {
      opacity: 0;
      pointer-events: none;
    }

    #quiz-container {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: linear-gradient(135deg, #4a00e0, #8e2de2);
      padding: 20px;
      border-radius: 16px;
      box-shadow: 0 0 25px #8e2de2;
      max-width: 400px;
      text-align: center;
      z-index: 1000;
    }

    #quiz-container h2 {
      font-size: 1.2rem;
      margin-bottom: 20px;
    }

    .option {
      display: block;
      margin: 10px auto;
      padding: 12px 20px;
      background: #00ffcc;
      color: #111;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      font-size: 1rem;
      font-weight: bold;
      transition: transform 0.2s, background 0.3s;
    }

    .option:hover {
      transform: scale(1.05);
      background: #00ffaa;
    }

    #final-panel {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.9);
      z-index: 2000;
      color: #fff;
      text-align: center;
      padding-top: 50px;
    }

    #final-panel h1 {
      font-size: 3rem;
      margin-bottom: 20px;
      color: #00ffcc;
      text-shadow: 0 0 15px #00ffcc;
      animation: zoomIn 1s ease;
    }

    @keyframes zoomIn {
      from { transform: scale(0.5); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    #final-panel img {
      width: 400px;
      border-radius: 16px;
      margin: 20px 0;
    }

    #download-btn {
      padding: 15px 25px;
      font-size: 1.2rem;
      font-weight: bold;
      background: #00ffcc;
      color: #111;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      box-shadow: 0 0 15px #00ffcc;
      transition: background 0.3s, transform 0.2s;
    }

    #download-btn:hover {
      background: #00ffaa;
      transform: scale(1.05);
    }
  </style>
</head>
<body>

<div id="score-board">Puntaje: 0 | Tiempo: 03:00</div>
<div id="puzzle-board"></div>

<div id="quiz-container">
  <h2 id="quiz-question"></h2>
  <div id="options"></div>
</div>

<div id="final-panel">
  <h1 id="final-score"></h1>
  <p id="final-message"></p>
  <img id="final-image" src="https://www.uautonoma.cl/content/uploads/2023/07/maltrato-infantil-1.jpg" alt="Imagen final">
  <br>
  <button id="download-btn">Descargar Certificado</button>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script>
  const board = document.getElementById('puzzle-board');
  const scoreBoard = document.getElementById('score-board');
  const quizContainer = document.getElementById('quiz-container');
  const quizQuestion = document.getElementById('quiz-question');
  const optionsDiv = document.getElementById('options');
  const finalPanel = document.getElementById('final-panel');
  const finalScore = document.getElementById('final-score');
  const finalMessage = document.getElementById('final-message');
  const downloadBtn = document.getElementById('download-btn');

  let score = 0;
  let timeLeft = 180;
  let gameTimer = null;

  function updateHUD() {
    const mm = String(Math.floor(timeLeft / 60)).padStart(2, '0');
    const ss = String(timeLeft % 60).padStart(2, '0');
    scoreBoard.textContent = `Puntaje: ${score} | Tiempo: ${mm}:${ss}`;
  }

  function startGameTimer() {
    updateHUD();
    gameTimer = setInterval(() => {
      timeLeft--;
      updateHUD();
      if (timeLeft <= 0) {
        clearInterval(gameTimer);
        endGame(true);
      }
    }, 1000);
  }

  let revealedTiles = 0;
  function createBoard() {
    for (let i = 0; i < 16; i++) {
      const tile = document.createElement('div');
      tile.classList.add('tile');
      tile.dataset.index = i;
      tile.addEventListener('click', () => startQuiz(tile));
      board.appendChild(tile);
    }
  }

  const questions = [
    {q: "¿Qué debes hacer si alguien te pide guardar un secreto que te incomoda?", a: "Contarlo a un adulto de confianza", o: ["Guardarlo", "Contarlo a un adulto de confianza", "Ignorarlo"]},
    {q: "Si un desconocido te ofrece regalos a cambio de favores, ¿qué haces?", a: "Rechazar y contarlo", o: ["Aceptarlo", "Rechazar y contarlo", "Guardarlo en secreto"]},
    {q: "¿Qué personas puedes buscar si necesitas ayuda?", a: "Familia, docentes, autoridades", o: ["Cualquier persona en la calle", "Familia, docentes, autoridades", "Nadie"]},
    {q: "¿Qué es el abuso sexual infantil?", a: "Contacto o acciones sexuales hacia un menor", o: ["Un juego entre amigos", "Contacto o acciones sexuales hacia un menor", "Un secreto"]},
    {q: "¿Qué número puedes marcar en Colombia para denunciar emergencias?", a: "141", o: ["321", "141", "911"]},
    {q: "Si un adulto toca tu cuerpo sin permiso, ¿qué debes hacer?", a: "Decir no y buscar ayuda", o: ["Quedarte callado", "Decir no y buscar ayuda", "Aceptar"]},
    {q: "¿El abuso sexual siempre implica violencia física?", a: "No, puede ser sin fuerza física", o: ["Sí, siempre", "No, puede ser sin fuerza física", "Nunca"]},
    {q: "¿Qué es el consentimiento?", a: "Aceptar libremente y sin presión", o: ["Aceptar por miedo", "Aceptar libremente y sin presión", "Obedecer"]},
    {q: "¿Qué debes hacer si un amigo te cuenta que fue víctima de abuso?", a: "Escuchar y buscar ayuda con un adulto", o: ["Ignorar", "Reírse", "Escuchar y buscar ayuda con un adulto"]},
    {q: "¿Qué lugar NO es seguro para conocer extraños en internet?", a: "Redes sociales", o: ["El colegio", "Redes sociales", "Biblioteca"]},
    {q: "¿Qué significa respetar los límites del cuerpo?", a: "No tocar sin permiso", o: ["Tocar cuando quieras", "No tocar sin permiso", "Obligar"]},
    {q: "¿Qué actitud es correcta frente al abuso?", a: "Denunciar y apoyar a la víctima", o: ["Culpar a la víctima", "Negar el problema", "Denunciar y apoyar a la víctima"]},
    {q: "¿Quiénes son responsables del abuso sexual?", a: "Los agresores", o: ["Los niños", "Los agresores", "Los amigos"]},
    {q: "¿Qué debes recordar sobre tu cuerpo?", a: "Tu cuerpo es tuyo y merece respeto", o: ["No importa", "Tu cuerpo es tuyo y merece respeto", "Otros deciden"]},
    {q: "¿Qué hacer si sientes miedo de denunciar?", a: "Hablar con alguien de confianza", o: ["Guardar silencio", "Hablar con alguien de confianza", "Huir"]},
    {q: "Si alguien te pide fotos íntimas por internet, ¿qué debes hacer?", a: "No enviar y avisar a un adulto", o: ["Enviar", "No enviar y avisar a un adulto", "Ignorar y seguir"]}
  ];

  let availableQuestions = [...questions];

  let startTime = null;
  function startQuiz(tile) {
    if (quizContainer.style.display === 'block' || tile.classList.contains('revealed')) return;
    if (availableQuestions.length === 0) return;

    const qIndex = Math.floor(Math.random() * availableQuestions.length);
    const q = availableQuestions.splice(qIndex, 1)[0];

    quizQuestion.textContent = q.q;
    optionsDiv.innerHTML = '';
    q.o.forEach(opt => {
      const btn = document.createElement('button');
      btn.textContent = opt;
      btn.classList.add('option');
      btn.onclick = () => checkAnswer(opt, q.a, tile);
      optionsDiv.appendChild(btn);
    });

    quizContainer.style.display = 'block';
    startTime = new Date();
  }

  function checkAnswer(selected, correct, tile) {
    const endTime = new Date();
    const timeTaken = (endTime - startTime) / 1000;

    if (selected === correct) {
      let points = 40;
      if (timeTaken < 5) points += 20;
      else if (timeTaken < 10) points += 15;
      else if (timeTaken < 20) points += 10;
      score += points;
      updateHUD();

      tile.classList.add('revealed');
      revealedTiles++;

      if (revealedTiles === 16) {
        score += 40;
        clearInterval(gameTimer);
        endGame(false);
      }
    }

    quizContainer.style.display = 'none';
  }

  function endGame(byTime = false) {
    let message = "";
    if (byTime) {
      message = "Se acabó el tiempo. ¡Buen intento!";
    } else {
      if (score >= 800) message = "¡Excelente compromiso!";
      else if (score >= 500) message = "¡Muy bien, sigues aprendiendo y apoyando!";
      else message = "¡Puedes mejorar, sigue intentándolo!";
    }

    finalScore.textContent = `Tu puntaje: ${score}/1000`;
    finalMessage.textContent = message;
    finalPanel.style.display = 'block';
  }

  downloadBtn.addEventListener('click', () => {
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF();
    doc.setFontSize(18);
    doc.text("Certificado de Compromiso", 60, 40);
    doc.setFontSize(14);
    doc.text("Me comprometo a no guardar silencio frente al abuso.", 20, 70);
    doc.text(`Puntaje obtenido: ${score}/1000`, 20, 90);
    doc.save("Compromiso.pdf");
  });

  createBoard();
  startGameTimer();
</script>
</body>
</html>
