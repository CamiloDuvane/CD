<html><head><base href="https://websimstorage.com/comics/"><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Biblioteca de Histórias em Quadrinhos</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Bangers&family=Comic+Neue:wght@400;700&display=swap');

  body {
    font-family: 'Comic Neue', cursive;
    background-color: #f0f0f0;
    margin: 0;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
  }

  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
  }

  .login-container {
    background-color: white;
    padding: 20px;
    border-radius: 10px;
    text-align: center;
  }

  .login-btn {
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    margin: 10px;
    background-color: #ff6b6b;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .login-btn:hover {
    background-color: #ff4757;
  }

  .container {
    flex: 1;
    max-width: none;
    width: 100%;
    margin: 0;
    border-radius: 0;
    box-shadow: none;
    overflow-y: auto;
  }

  h1 {
    font-family: 'Bangers', cursive;
    color: #ff6b6b;
    text-align: center;
    font-size: 2.5em;
    margin-bottom: 20px;
    text-shadow: 2px 2px 0px #feca57;
  }

  .menu {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
    margin-bottom: 30px;
  }

  .story-card {
    background-color: #f7f1e3;
    border: 2px solid #2d3436;
    border-radius: 10px;
    padding: 15px;
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
  }

  .story-card.read {
    opacity: 0.7;
    background-color: #e0e0e0;
  }

  .story-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
  }

  .story-title {
    font-family: 'Bangers', cursive;
    color: #4ecdc4;
    font-size: 1.3em;
    margin-bottom: 10px;
  }

  .story-info {
    font-size: 0.9em;
    color: #636e72;
  }

  .comic-container {
    display: none;
  }

  .scene {
    margin-bottom: 30px;
    border: 1px solid #ddd;
    padding: 15px;
    border-radius: 5px;
  }

  .scene-title {
    font-family: 'Bangers', cursive;
    color: #4ecdc4;
    font-size: 1.5em;
    margin-bottom: 10px;
  }

  .panel {
    background-color: #f7f1e3;
    border: 2px solid #2d3436;
    border-radius: 10px;
    padding: 15px;
    margin-bottom: 15px;
  }

  .panel-description {
    white-space: pre-wrap;
  }

  .dialogue {
    margin-left: 20px;
  }

  .character {
    font-weight: bold;
    color: #6c5ce7;
  }

  .moral {
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    text-align: center;
    color: #e17055;
    margin-top: 30px;
    padding: 10px;
    background-color: #ffeaa7;
    border-radius: 5px;
  }

  .nav-buttons {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
  }

  .nav-button {
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #ff6b6b;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .nav-button:hover {
    background-color: #ff4757;
  }

  .nav-button:disabled {
    background-color: #b2bec3;
    cursor: not-allowed;
  }

  .back-to-menu {
    display: block;
    margin: 20px auto;
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #4ecdc4;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .back-to-menu:hover {
    background-color: #45b7aa;
  }

  .exit-btn {
    display: block;
    margin: 20px auto;
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #ff6b6b;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .exit-btn:hover {
    background-color: #ff4757;
  }

  .edit-form {
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    padding: 20px;
    margin-top: 20px;
    border-radius: 5px;
  }

  .edit-form input {
    width: 100%;
    padding: 8px;
    margin: 5px 0 15px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }

  .edit-form button {
    background-color: #4CAF50;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }

  .edit-form button:hover {
    background-color: #45a049;
  }

  .edit-form textarea {
    width: 100%;
    height: 400px;
    margin-bottom: 10px;
    font-family: 'Comic Neue', cursive;
    font-size: 14px;
    line-height: 1.5;
  }

  .edit-form p {
    margin-bottom: 10px;
    font-style: italic;
    color: #666;
  }

  .quiz {
    background-color: #f0f8ff;
    border: 1px solid #add8e6;
    border-radius: 10px;
    padding: 20px;
    margin-top: 30px;
  }

  .quiz h3 {
    font-family: 'Bangers', cursive;
    color: #4ecdc4;
    font-size: 1.5em;
    margin-bottom: 20px;
  }

  .question {
    margin-bottom: 20px;
  }

  .question p {
    font-weight: bold;
    margin-bottom: 10px;
  }

  .question label {
    display: block;
    margin-bottom: 5px;
  }

  .quiz button {
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #ff6b6b;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
    margin-top: 20px;
  }

  .quiz button:hover {
    background-color: #ff4757;
  }

  .admin-panel {
    background-color: white;
    padding: 20px;
    border-radius: 10px;
    margin-top: 20px;
    display: none;
  }

  #story-select {
    width: 100%;
    padding: 10px;
    margin-bottom: 20px;
    font-size: 16px;
  }

  .quiz-question {
    margin-bottom: 20px;
  }

  .quiz-question input,
  .quiz-question textarea {
    width: 100%;
    padding: 5px;
    margin-bottom: 5px;
  }

  .admin-button {
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #4ecdc4;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
    margin-top: 20px;
    margin-right: 10px;
  }

  .admin-button:hover {
    background-color: #45b7aa;
  }

  .story-preview {
    display: none;
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 10px;
    padding: 30px;
    margin-top: 20px;
    max-height: 600px;
    overflow-y: auto;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  .story-preview h3 {
    font-family: 'Bangers', cursive;
    color: #4ecdc4;
    font-size: 2em;
    margin-bottom: 10px;
    text-align: center;
  }

  .story-preview .story-info {
    text-align: center;
    font-style: italic;
    margin-bottom: 20px;
    color: #666;
  }

  .story-preview .story-content {
    background-color: #f7f1e3;
    border: 2px solid #2d3436;
    border-radius: 10px;
    padding: 25px;
    margin-bottom: 20px;
    white-space: pre-wrap;
    font-family: 'Comic Neue', cursive;
    line-height: 1.8;
    text-align: justify;
  }

  .story-preview .quiz-section h4 {
    font-family: 'Bangers', cursive;
    color: #ff6b6b;
    font-size: 1.5em;
    margin-bottom: 15px;
  }

  .story-preview .quiz-section .question {
    background-color: #f0f8ff;
    border: 1px solid #add8e6;
    border-radius: 8px;
    padding: 15px;
    margin-bottom: 15px;
  }

  .story-preview .quiz-section .question p {
    font-weight: bold;
    margin-bottom: 10px;
  }

  .story-preview .quiz-section .question ul {
    list-style-type: none;
    padding-left: 0;
  }

  .story-preview .quiz-section .question li {
    margin-bottom: 5px;
  }

  .story-preview .quiz-section .question li.correct-answer {
    color: #4CAF50;
    font-weight: bold;
  }

  .quiz-result {
    background-color: #f0f8ff;
    border: 1px solid #add8e6;
    border-radius: 10px;
    padding: 20px;
    margin-top: 30px;
    text-align: center;
  }

  .quiz-result h3 {
    font-family: 'Bangers', cursive;
    color: #4ecdc4;
    font-size: 1.5em;
    margin-bottom: 20px;
  }

  .quiz-result p {
    font-size: 1.2em;
    margin-bottom: 20px;
  }

  .quiz-result button {
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #ff6b6b;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .quiz-result button:hover {
    background-color: #ff4757;
  }

  .fullscreen-btn {
    position: fixed;
    top: 20px;
    right: 20px;
    z-index: 1001;
    font-family: 'Bangers', cursive;
    font-size: 1.2em;
    padding: 10px 20px;
    background-color: #4ecdc4;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .fullscreen-btn:hover {
    background-color: #45b7aa;
  }
  
</style>
</head>
<body>
  <div id="login-overlay" class="overlay">
    <div class="login-container">
      <h2>Bem-vindo à Biblioteca de Histórias em Quadrinhos</h2>
      <button id="reading-room-btn" class="login-btn">Sala de Leitura</button>
      <button id="admin-btn" class="login-btn">Administrador</button>
    </div>
  </div>
  <div class="container">
    <h1>Biblioteca de Histórias em Quadrinhos</h1>
    <div id="story-menu" class="menu"></div>
    <div id="comic-container" class="comic-container">
      <h2 id="comic-title"></h2>
      <div id="comic-content"></div>
      <button class="back-to-menu" onclick="showMenu()">Voltar ao Menu</button>
    </div>
    <button id="exit-btn" class="exit-btn" onclick="showLoginOverlay()">Sair</button>
  </div>
  <div id="admin-panel" class="admin-panel">
    <h2>Painel de Administração</h2>
    <select id="story-select"></select>
    <div id="edit-form" class="edit-form">
      <input type="text" id="edit-title" placeholder="Título">
      <input type="number" id="edit-year" placeholder="Ano">
      <input type="text" id="edit-author" placeholder="Autor">
      <textarea id="edit-content" placeholder="Conteúdo"></textarea>
      <div id="quiz-editor"></div>
      <button onclick="saveStoryChanges()">Salvar Alterações</button>
      <button onclick="previewStory()" class="admin-button">Visualizar História</button>
    </div>
    <button onclick="showMenu()" class="admin-button">Voltar ao Menu</button>
    <div id="story-preview" class="story-preview"></div>
  </div>

  <script>
const stories = [
  {
    id: 1,
    title: "Os Ladrões e a Galinha dos Ovos de Ouro",
    year: 2023,
    author: "Camilo Duvane",
    content: `O fazendeiro está no galinheiro segurando um ovo de ouro, com um sorriso imenso no rosto. (pensando) Com esse ovo, vou comprar o maior trator do mundo!

Os ladrões armam um plano com um mapa desenhado à mão de como entrar no galinheiro.

Os ladrões finalmente chegam ao poleiro, mas a galinha começa a cacarejar alto.

Os ladrões fogem em pânico, deixando um rastro de penas para trás.

Os ladrões, escondidos atrás de arbustos, observam o fazendeiro voltar para casa.`,
    read: false,
    quiz: [
      {
        question: "O que o fazendeiro planeja comprar com o ovo de ouro?",
        options: ["Um carro novo", "O maior trator do mundo", "Uma nova fazenda", "Uma galinha robótica"],
        correctAnswer: 1
      },
      {
        question: "O que acontece quando os ladrões chegam ao poleiro?",
        options: ["A galinha dorme", "A galinha põe um ovo", "A galinha começa a cacarejar alto", "A galinha os ataca"],
        correctAnswer: 2
      },
      {
        question: "Como os ladrões fogem?",
        options: ["Calmamente", "Em pânico", "Voando", "Nadando"],
        correctAnswer: 1
      }
    ]
  },
  {
    id: 2,
    title: "As Aventuras do Gato de Botas",
    year: 2022,
    author: "Camilo Duvane",
    content: `O Gato de Botas caminha orgulhosamente pela cidade, exibindo suas elegantes botas.

O Gato de Botas se prepara para a jornada, enchendo sua bolsa com petiscos de atum.

O Gato de Botas e o Rato chegam à entrada da caverna do Ogro.

O Ogro, orgulhoso, se transforma em um leão rugindo.

O Gato de Botas captura facilmente o Ogro transformado em rato.`,
    read: false,
    quiz: [
      {
        question: "Qual era o objetivo do Gato de Botas?",
        options: ["Capturar um ogro", "Encontrar um amigo", "Resolver um mistério", "Ir para casa"],
        correctAnswer: 0
      },
      {
        question: "O que o Gato de Botas traz com ele para a jornada?",
        options: ["Uma espada", "Um mapa", "Um bom humor", "Petiscos de atum"],
        correctAnswer: 3
      },
      {
        question: "Como o Gato de Botas derrota o Ogro?",
        options: ["Lutando com força", "Usando truques", "Fazendo amizade", "Transformando-o em rato"],
        correctAnswer: 3
      }
    ]
  },
  {
    id: 3,
    title: "O Dia em que o Sol Tirou Férias",
    year: 2024,
    author: "Camilo Duvane",
    content: `O Sol acorda cansado e decide tirar um dia de folga.

As pessoas ficam surpresas ao ver que não amanhece.

Os animais noturnos ficam confusos e não sabem se devem dormir ou ficar acordados.

As crianças organizam uma festa do pijama gigante para toda a cidade.

O Sol volta de suas férias, descansado e brilhando mais forte que nunca.`,
    read: false,
    quiz: [
      {
        question: "Por que o Sol decidiu tirar um dia de folga?",
        options: ["Estava cansado", "Queria ir à praia", "Estava doente", "Queria pregar uma peça"],
        correctAnswer: 0
      },
      {
        question: "O que as crianças fizeram durante o dia sem Sol?",
        options: ["Dormiram o dia todo", "Organizaram uma festa do pijama", "Ficaram tristes", "Foram para a escola"],
        correctAnswer: 1
      },
      {
        question: "Como o Sol estava quando voltou de suas férias?",
        options: ["Cansado", "Triste", "Descansado e brilhante", "Com nuvens"],
        correctAnswer: 2
      }
    ]
  },
  {
    id: 4,
    title: "A Girafa que Tinha Medo de Alturas",
    year: 2024,
    author: "Camilo Duvane",
    content: `Gigi, a girafa, descobre que tem medo de alturas ao olhar para baixo.

Os outros animais tentam ajudar Gigi a superar seu medo.

Gigi pratica olhar para cima em vez de para baixo.

Um filhote de pássaro cai do ninho e Gigi é a única que pode alcançá-lo.

Gigi supera seu medo para salvar o filhote e descobre que alturas não são tão assustadoras.`,
    read: false,
    quiz: [
      {
        question: "Qual é o nome da girafa da história?",
        options: ["Gina", "Gigi", "Gina", "Gilda"],
        correctAnswer: 1
      },
      {
        question: "O que Gigi pratica para superar seu medo?",
        options: ["Pular", "Correr", "Olhar para cima", "Fechar os olhos"],
        correctAnswer: 2
      },
      {
        question: "O que faz Gigi superar seu medo no final?",
        options: ["Ver um arco-íris", "Ganhar um prêmio", "Salvar um filhote de pássaro", "Subir em uma árvore"],
        correctAnswer: 2
      }
    ]
  },
  {
    id: 5,
    title: "O Peixe que Queria Voar",
    year: 2024,
    author: "Camilo Duvane",
    content: `Finn, o peixinho, sonha em voar como os pássaros.

Finn tenta pular para fora da água, mas sempre cai de volta.

Uma gaivota amiga ensina Finn sobre a importância de ser quem você é.

Finn descobre que pode 'voar' debaixo d'água usando suas nadadeiras.

Finn mostra aos pássaros como é incrível 'voar' no oceano. `,
    read: false,
    quiz: [
      {
        question: "Qual é o sonho de Finn?",
        options: ["Nadar mais rápido", "Voar como os pássaros", "Viver em um aquário", "Encontrar um tesouro"],
        correctAnswer: 1
      },
      {
        question: "Quem ajuda Finn a entender a importância de ser quem ele é?",
        options: ["Um tubarão", "Uma tartaruga", "Uma gaivota", "Outro peixe"],
        correctAnswer: 2
      },
      {
        question: "O que Finn descobre que pode fazer no final da história?",
        options: ["Voar no ar", "Respirar fora d'água", "'Voar' debaixo d'água", "Falar com humanos"],
        correctAnswer: 2
      }
    ]
  }
];

function populateMenu() {
  const menu = document.getElementById('story-menu');
  menu.innerHTML = '';
  
  const sortedStories = stories.sort((a, b) => {
    if (a.read === b.read) return 0;
    return a.read ? 1 : -1;
  });

  sortedStories.forEach((story, index) => {
    const card = document.createElement('div');
    card.className = `story-card ${story.read ? 'read' : ''}`;
    card.innerHTML = `
      <div class="story-title">${index + 1}. ${story.title}</div>
      <div class="story-info">Ano: ${story.year} | Autor: ${story.author}</div>
    `;
    card.onclick = () => showStory(story);
    menu.appendChild(card);
  });
}

let currentStory = null;

function showLoginOverlay() {
  document.getElementById('login-overlay').style.display = 'flex';
  document.querySelector('.container').style.display = 'none';
  document.getElementById('admin-panel').style.display = 'none';
  document.getElementById('story-preview').style.display = 'none';
}

function hideLoginOverlay() {
  document.getElementById('login-overlay').style.display = 'none';
}

function showAdminPanel() {
  document.getElementById('admin-panel').style.display = 'block';
  document.querySelector('.container').style.display = 'none';
  document.getElementById('story-preview').style.display = 'none';
  populateStorySelect();
}

function populateStorySelect() {
  const select = document.getElementById('story-select');
  select.innerHTML = '<option value="">Selecione uma história</option>';
  stories.forEach(story => {
    const option = document.createElement('option');
    option.value = story.id;
    option.textContent = story.title;
    select.appendChild(option);
  });
  select.addEventListener('change', loadStoryForEditing);
}

function loadStoryForEditing() {
  const storyId = parseInt(document.getElementById('story-select').value);
  const story = stories.find(s => s.id === storyId);
  if (story) {
    document.getElementById('edit-title').value = story.title;
    document.getElementById('edit-year').value = story.year;
    document.getElementById('edit-author').value = story.author;
    document.getElementById('edit-content').value = story.content;
    
    const quizEditor = document.getElementById('quiz-editor');
    quizEditor.innerHTML = '';
    story.quiz.forEach((question, index) => {
      const questionDiv = document.createElement('div');
      questionDiv.className = 'quiz-question';
      questionDiv.innerHTML = `
        <textarea class="question-text">${question.question}</textarea>
        ${question.options.map((option, optIndex) => `
          <input type="text" class="option" value="${option}">
        `).join('')}
        <input type="number" class="correct-answer" value="${question.correctAnswer}" min="0" max="3">
      `;
      quizEditor.appendChild(questionDiv);
    });
  }
}

function saveStoryChanges() {
  const storyId = parseInt(document.getElementById('story-select').value);
  const story = stories.find(s => s.id === storyId);
  if (story) {
    story.title = document.getElementById('edit-title').value;
    story.year = parseInt(document.getElementById('edit-year').value);
    story.author = document.getElementById('edit-author').value;
    story.content = document.getElementById('edit-content').value;
    
    const quizQuestions = document.querySelectorAll('.quiz-question');
    story.quiz = Array.from(quizQuestions).map(questionDiv => {
      return {
        question: questionDiv.querySelector('.question-text').value,
        options: Array.from(questionDiv.querySelectorAll('.option')).map(option => option.value),
        correctAnswer: parseInt(questionDiv.querySelector('.correct-answer').value)
      };
    });
    
    alert('Alterações salvas com sucesso!');
    populateMenu();
  }
}

function previewStory() {
  const storyId = parseInt(document.getElementById('story-select').value);
  const story = stories.find(s => s.id === storyId);
  const previewDiv = document.getElementById('story-preview');
  
  if (story) {
    const modifiedTitle = document.getElementById('edit-title').value;
    const modifiedYear = document.getElementById('edit-year').value;
    const modifiedAuthor = document.getElementById('edit-author').value;
    const modifiedContent = document.getElementById('edit-content').value;
    
    previewDiv.innerHTML = `
      <h3>${modifiedTitle}</h3>
      <p class="story-info"><strong>Ano:</strong> ${modifiedYear} | <strong>Autor:</strong> ${modifiedAuthor}</p>
      <div class="story-content">${modifiedContent}</div>
      <div class="quiz-section">
        <h4>Quiz</h4>
        ${story.quiz.map((q, i) => `
          <div class="question">
            <p>${i + 1}. ${q.question}</p>
            <ul>
              ${q.options.map((option, j) => `
                <li class="${j === q.correctAnswer ? 'correct-answer' : ''}">${option}${j === q.correctAnswer ? ' (Resposta correta)' : ''}</li>
              `).join('')}
            </ul>
          </div>
        `).join('')}
      </div>
    `;
    previewDiv.style.display = 'block';
  } else {
    previewDiv.innerHTML = '<p>Selecione uma história para visualizar.</p>';
    previewDiv.style.display = 'block';
  }
}

function showMenu() {
  document.getElementById('story-menu').style.display = 'grid';
  document.getElementById('comic-container').style.display = 'none';
  document.getElementById('admin-panel').style.display = 'none';
  document.getElementById('story-preview').style.display = 'none';
  document.querySelector('.container').style.display = 'block';
  currentStory = null;
  populateMenu();
}

function showAdminError() {
  alert('Senha incorreta. Por favor, contacte Camilo Duvane pelos números 842479404 para obter a senha correta.');
}

document.getElementById('admin-btn').addEventListener('click', () => {
  const password = prompt('Digite a senha de administrador:');
  if (password === '6363') {
    hideLoginOverlay();
    showAdminPanel();
  } else {
    showAdminError();
  }
});

function showStory(story) {
  currentStory = story;
  document.getElementById('story-menu').style.display = 'none';
  const comicContainer = document.getElementById('comic-container');
  comicContainer.style.display = 'block';
  
  document.getElementById('comic-title').textContent = story.title;
  const comicContent = document.getElementById('comic-content');
  comicContent.innerHTML = '';

  const scenes = story.content.split('\n\n');
  scenes.forEach((scene, index) => {
    const sceneDiv = document.createElement('div');
    sceneDiv.className = 'scene';
    sceneDiv.innerHTML = `
      <h3 class="scene-title">Cena ${index + 1}</h3>
      <div class="panel">
        <p class="panel-description">${scene}</p>
      </div>
    `;
    comicContent.appendChild(sceneDiv);
  });

  const quizDiv = document.createElement('div');
  quizDiv.className = 'quiz';
  quizDiv.innerHTML = `
    <h3>Quiz</h3>
    ${story.quiz.map((q, i) => `
      <div class="question">
        <p>${i + 1}. ${q.question}</p>
        ${q.options.map((option, j) => `
          <label>
            <input type="radio" name="q${i}" value="${j}">
            ${option}
          </label>
        `).join('')}
      </div>
    `).join('')}
    <button onclick="submitQuiz()">Enviar Respostas</button>
  `;
  comicContent.appendChild(quizDiv);

  story.read = true;
}

function submitQuiz() {
  if (!currentStory) return;

  let correctAnswers = 0;
  const totalQuestions = currentStory.quiz.length;

  currentStory.quiz.forEach((q, i) => {
    const selectedAnswer = document.querySelector(`input[name="q${i}"]:checked`);
    if (selectedAnswer && parseInt(selectedAnswer.value) === q.correctAnswer) {
      correctAnswers++;
    }
  });

  const resultText = `Você acertou ${correctAnswers} de ${totalQuestions} perguntas!`;
  displayQuizResults(currentStory.title, resultText);
}

function displayQuizResults(title, resultText) {
  const comicContent = document.getElementById('comic-content');
  const resultDiv = document.createElement('div');
  resultDiv.className = 'quiz-result';
  resultDiv.innerHTML = `
    <h3>${title}</h3>
    <p>${resultText}</p>
    <button onclick="showMenu()">Voltar ao Menu</button>
  `;
  comicContent.innerHTML = '';
  comicContent.appendChild(resultDiv);
}

function toggleFullScreen() {
  if (!document.fullscreenElement) {
    document.documentElement.requestFullscreen();
  } else {
    if (document.exitFullscreen) {
      document.exitFullscreen();
    }
  }
}

// Add this to the existing window.addEventListener('load', ...) function
const fullscreenBtn = document.createElement('button');
fullscreenBtn.textContent = 'CWD';
fullscreenBtn.className = 'fullscreen-btn';
fullscreenBtn.onclick = toggleFullScreen;
document.body.appendChild(fullscreenBtn);

document.getElementById('reading-room-btn').addEventListener('click', () => {
  hideLoginOverlay();
  showMenu();
});

window.addEventListener('load', () => {
  showLoginOverlay();
  populateMenu();
});

stories.forEach(story => {
  story.author = "Camilo Duvane";
});
</script>
</body></html>
