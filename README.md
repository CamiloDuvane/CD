<html><head><base href="https://camiloduvane.github.io/CD/"><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Biblioteca de Histórias em Quadrinhos</title>
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
      <h2>Seja bem-vindo à Biblioteca de Histórias em Quadrinhos! Onde cada história é uma nova aventura esperando para ser descoberta</h2>
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
    title: "A Galinha dos Ovos de Ouro",
    year: 2000,
    author: "Camilo Duvane",
    content: `No silêncio da manhã, o fazendeiro entrou no galinheiro como fazia todos os dias. Mas, para sua surpresa, encontrou algo brilhando no meio das palhas: um ovo de ouro. Ele o pegou cuidadosamente, admirando o brilho metálico com um sorriso imenso no rosto.
"Com esse ovo, vou comprar o maior trator do mundo!"
Ele não conseguia conter a alegria, imaginando as novas possibilidades que esse ovo traria para sua fazenda. Com o ovo seguro em suas mãos, ele saiu do galinheiro, sem perceber que estava sendo vigiado.

<p>O Plano dos Ladrões</p>
Do outro lado da fazenda, escondidos entre árvores, dois ladrões observavam atentamente o fazendeiro. Eles tinham ouvido rumores sobre o ovo de ouro e estavam determinados a roubá-lo.
"Precisamos desse ovo. Com ele, seremos ricos!"
Os dois abriram um mapa desenhado à mão no chão, traçando os passos de como invadir o galinheiro. Estavam confiantes de que o plano era perfeito.
"Entramos pelo portão lateral, depois escalamos a cerca e pegamos a galinha. Fácil."

<p>O Roubo</p>
Na calada da noite, os ladrões finalmente executaram seu plano. Chegaram ao poleiro, mal iluminado pela luz da lua, e começaram a se aproximar da galinha que, supostamente, botava os ovos de ouro. Quando estavam prestes a pegá-la, um som alto os fez congelar.

<p>"CÓCÓRÓCÓCÓÓÓÓÓ!"</p>
O cacarejar ecoou por toda a fazenda, acordando os outros animais. Desesperados, os ladrões se entreolharam, o medo crescendo.

<p>A Fuga<p/>
"Corre! Corre!"
Os dois fugiram em pânico, tropeçando nas cercas e deixando um rastro de penas para trás, enquanto o cacarejar continuava alto. O plano perfeito tinha virado um desastre. Eles correram sem parar até encontrarem abrigo.

<p>O Fazendeiro Retorna</p>
Na manhã seguinte, os ladrões, ainda tremendo e escondidos atrás de arbustos, observaram o fazendeiro retornando ao galinheiro. Ele parecia alheio ao ocorrido, acariciando a galinha e levando outro ovo para casa, com um sorriso no rosto.
"Que noite tranquila. Agora é hora de vender outro ovo de ouro."
Enquanto o fazendeiro caminhava para sua casa, os ladrões sabiam que, por ora, seus planos de roubar a galinha dos ovos de ouro estavam arruinados.
E assim termina a história dos ladrões, que, mesmo com todo o planejamento, acabaram fugindo com as mãos vazias!`,
    read: false,
    quiz: [
      {
        question: "O que o fazendeiro encontrou no galinheiro?",
        options: ["Uma galinha nova", "Um ovo de prata", "Um ovo de ouro", "Um saco de dinheiro"],
        correctAnswer: 2
      },
      {
        question: "O que o fazendeiro planejava fazer com o ovo de ouro?",
        options: ["Construir uma casa", "Comprar o maior trator do mundo", "Vender a fazenda", "Guardar o ovo como lembrança"],
        correctAnswer: 1
      },
      {
        question: "Como os ladrões planejavam roubar o ovo?",
        options: ["Elaborando um plano com um mapa desenhado à mão", "Pedindo o ovo ao fazendeiro", "Comprando a galinha do fazendeiro", "Esperando a galinha botar outro ovo"],
        correctAnswer: 0
      },
      {
        question: "Quando os ladrões decidiram executar o plano?",
        options: ["De manhã cedo", "À tarde", "Durante a noite", "No horário de almoço"],
        correctAnswer: 2
      },
      {
        question: "O que aconteceu quando os ladrões chegaram ao galinheiro?",
        options: ["A galinha os atacou", "O fazendeiro os pegou", "Eles roubaram o ovo", "A galinha começou a cacarejar alto"],
        correctAnswer: 3
      },
      {
        question: "O que os ladrões fizeram quando ouviram a galinha cacarejar?",
        options: ["Pegaram a galinha e correram", "Fugiram em pânico", "Se esconderam no galinheiro", "Gritaram por ajuda"],
        correctAnswer: 1
      },
      {
        question: "Onde os ladrões se esconderam após fugirem do galinheiro?",
        options: ["No celeiro", "Dentro do galinheiro", "Atrás de arbustos", "Na casa do fazendeiro"],
        correctAnswer: 2
      },   
      {
        question: "O fazendeiro percebeu o plano dos ladrões?",
        options: ["Não", "Sim, ele os pegou", "Sim, mas não fez nada", "Sim, e correu atrás deles"],
        correctAnswer: 0
      },
      {
        question: "O que o fazendeiro fez na manhã seguinte?",
        options: ["Ele voltou ao galinheiro, acariciou a galinha e levou outro ovo para casa", "Ele descobriu o plano dos ladrões", "Ele vendeu a galinha", "Ele trancou o galinheiro"],
        correctAnswer: 0
      },
     {
        question: "Como a história termina para os ladrões?",
        options: ["Conseguem roubar o ovo", "São presos pelo fazendeiro", "Se tornam amigos do fazendeiro", "Fugiram sem o ovo e com o plano fracassado"],
        correctAnswer: 3
      }
    ]
  },
  {
    id: 2,
    title: "As Aventuras do Gato de Botas",
    year: 1995,
    author: "Camilo Duvane",
    content: `<p>O Desfile do Gato de Botas</p>
Era uma vez, em uma cidade distante, um gato muito especial que usava botas de couro reluzente. Ele era conhecido por sua astúcia e coragem. Enquanto caminhava pelas ruas, os moradores admiravam sua confiança e elegância. Com sua espada presa ao cinto e seu chapéu inclinado para o lado, o Gato de Botas se preparava para uma missão perigosa: derrotar o terrível Ogro da montanha. Ele sorriu de canto, sabendo que nada poderia impedi-lo.

<p>Preparativos para a Jornada</p>
Em seu esconderijo secreto, o Gato de Botas organizava tudo com cuidado. Ele encheu sua bolsa com petiscos de atum, colocou sua capa e ajustou bem as botas. "Vamos, Rato", disse ele ao seu pequeno companheiro. "Hoje é o dia em que enfrentaremos o Ogro e sairemos vitoriosos!" O Rato, que sempre o acompanhava, tremia de medo, mas confiava plenamente no Gato de Botas.

<p>A Caminho da Caverna</p>
Eles caminharam por florestas densas e cruzaram rios gelados até que, finalmente, chegaram à entrada da caverna do Ogro. O lugar era sombrio, com musgos escorrendo pelas paredes de pedra e uma neblina que parecia esconder perigos à espreita. O Gato de Botas sacou sua espada e deu um passo à frente. "Agora começa a verdadeira aventura", ele disse, com um brilho nos olhos.

<p>O Primeiro Desafio – Os Guardiões de Pedra</p>
Ao entrarem na caverna, dois enormes guardiões de pedra surgiram das sombras, bloqueando o caminho. Suas vozes ressoavam como trovões: "Ninguém entra sem provar sua força!" O Gato de Botas não hesitou. Ele pulou com agilidade, desviando dos socos pesados das estátuas e usando sua espada para desferir golpes rápidos. Com suas botas mágicas, ele saltava pelas paredes, confundindo os guardiões, até que, com um movimento preciso, derrubou as criaturas de pedra com um golpe final.

<p>O Labirinto do Ogro</p>
Após vencer os guardiões, o Gato e o Rato se viram diante de um labirinto escuro e traiçoeiro. O Ogro tinha enchido o lugar de armadilhas mortais. Flechas voavam de todos os lados, e o chão se abria em buracos profundos. Mas o Gato de Botas, com sua incrível habilidade e agilidade, desviava de cada obstáculo, enquanto o Rato seguia em sua cauda, torcendo para que não errassem o caminho. A cada passo, o labirinto parecia mais difícil, mas o Gato de Botas não desistia.

<p>O Encontro com o Ogro</p>
Finalmente, depois de vencer o labirinto, eles chegaram à câmara central, onde o Ogro estava sentado em seu trono de ossos. Ele era gigantesco, com músculos que pareciam montanhas e olhos que brilhavam como brasas. "Quem ousa invadir minha caverna?", rugiu o Ogro. O Gato de Botas se aproximou, sem mostrar medo, e disse: "Eu sou o Gato de Botas, e vim acabar com o seu reinado de terror!" O Ogro deu uma gargalhada, mas o Gato estava preparado.

<p>A Grande Batalha</p>
O Ogro levantou seu pesado porrete e atacou, fazendo o chão tremer. O Gato de Botas, com sua agilidade, saltava para fora do alcance dos golpes, desferindo ataques rápidos com sua espada. Cada vez que o Ogro tentava esmagá-lo, o Gato usava suas botas mágicas para saltar mais alto e mais rápido, cortando o monstro em pontos estratégicos. Mas o Ogro era poderoso, e cada erro poderia ser fatal.
<p>A luta foi intensa. O Gato escalava as paredes e usava cada centímetro de sua inteligência e agilidade para vencer. Em um momento de descuido, o Ogro o encurralou, mas o Rato, com sua pequena bravura, mordeu o tornozelo do gigante, distraindo-o por tempo suficiente para o Gato de Botas desferir o golpe final — um corte certeiro que fez o Ogro cair, derrotado.</p>

<p>O Tesouro e o Retorno Triunfante</p>
Com o Ogro derrotado, o Gato de Botas e o Rato descobriram o tesouro escondido nas profundezas da caverna. Riquezas além da imaginação estavam à sua disposição, mas, mais importante que o ouro, era a sensação de vitória e dever cumprido. O Gato de Botas olhou para o Rato e sorriu. "Conseguimos, meu amigo. Agora, vamos para casa."

<p>E assim, o Gato de Botas voltou para a cidade, mais uma vez aclamado como herói. As pessoas o saudaram enquanto ele caminhava pelas ruas com suas botas brilhando e sua cabeça erguida, sabendo que sua coragem e astúcia haviam salvado o dia mais uma vez.</p>`,
    read: false,
    quiz: [
      {
        question: "Qual era o objetivo do Gato de Botas ao entrar na caverna do Ogro?",
        options: ["Encontrar um tesouro perdido.", "Libertar prisioneiros do Ogro.", "Derrotar o Ogro e acabar com seu reinado de terror.", "Procurar um antigo artefato mágico."],
        correctAnswer: 2
      },
      {
        question: "Quem acompanhava o Gato de Botas em sua jornada?",
        options: ["Um pequeno rato.", "Um cavalo valente.", "Um corvo sábio.", "Um leão corajoso."],
        correctAnswer: 0
      },
      {
        question: "Qual foi o primeiro desafio que o Gato de Botas enfrentou dentro da caverna?",
        options: ["Um rio de lava.", "Guardiões de pedra gigantes.", "Uma armadilha de flechas.", "Um dragão adormecido."],
        correctAnswer: 1
      },
      {
        question: "Como o Rato ajudou o Gato de Botas na batalha contra o Ogro?",
        options: ["Distraiu o Ogro mordendo seu tornozelo.", "Trouxe uma espada mágica ao Gato de Botas.", " Fez uma armadilha para o Ogro cair.", "Falou com o Ogro para negociar a paz."],
        correctAnswer: 0
      }
    ]
  },
  {
    id: 3,
    title: "O Dia em que o Sol Tirou Férias",
    year: 2022,
    author: "Camilo Duvane",
    content: `<p>O Sol Decide Descansar</p>
Era uma vez, em um reino distante, onde todos os dias o Sol nascia pontualmente, brilhante e caloroso, iluminando o mundo com sua luz dourada. No entanto, naquela manhã, algo inesperado aconteceu. O Sol, ao despertar no horizonte, se sentiu cansado. "Todos os dias eu ilumino a Terra sem descanso", pensou ele. "Hoje, vou tirar um dia de folga!" E assim, sem pensar duas vezes, o Sol se escondeu atrás de uma nuvem enorme, bocejou, e adormeceu novamente.

<p>O Mundo sem Amanhecer</p>
As horas passaram e, estranhamente, não amanhecia. As pessoas saíram de suas casas, mas a escuridão continuava. O relógio marcava 8 da manhã, depois 9, 10… e ainda estava tudo escuro. "O que está acontecendo?", perguntavam-se, intrigadas. Os agricultores esperavam a luz do Sol para começar o trabalho, as crianças estavam confusas, e até os relógios de sol ficaram inúteis. As ruas estavam cheias de murmúrios: "Onde está o Sol? Será que ele nos abandonou?"

<p>A Confusão dos Animais</p>
Enquanto as pessoas tentavam entender o que estava acontecendo, os animais noturnos ficaram completamente confusos. Os morcegos voavam em círculos, sem saber se deveriam caçar ou voltar para suas cavernas. As corujas, que normalmente dormiam durante o dia, estavam acordadas, mas estranhavam que a noite parecia não ter fim. "Deveríamos continuar acordados?", perguntava-se um lobo a outro. "Ou será que estamos presos em uma noite eterna?" Os animais diurnos, por sua vez, se recusavam a sair de seus abrigos, achando que era noite.

<p>Os Planos da Lua</p>
Enquanto o Sol descansava, a Lua, que normalmente só aparecia à noite, olhava a Terra com preocupação. Ela sabia que não estava pronta para iluminar o mundo durante o dia. "Eu sou a guardiã da noite", pensava a Lua, "mas com o Sol dormindo, alguém precisa cuidar de tudo!" Assim, a Lua decidiu aparecer no céu, mas sua luz fraca não era suficiente para trazer a mesma energia que o Sol. "Preciso acordar o Sol", concluiu.

<p>A Conversa da Lua com o Sol</p>
A Lua, então, subiu até o esconderijo do Sol e o encontrou profundamente adormecido. "Sol!", chamou a Lua suavemente. "Todos na Terra estão confusos. Os humanos estão inquietos, os animais não sabem o que fazer, e a natureza precisa de você." O Sol abriu um olho, ainda preguiçoso. "Só mais cinco minutos...", ele murmurou. Mas a Lua insistiu: "Você pode descansar depois. O mundo precisa da sua luz!" Relutante, o Sol finalmente se espreguiçou e saiu de trás da nuvem.

<p>O Sol Retorna ao Céu</p>
De repente, um feixe de luz dourada cortou o céu, e as pessoas começaram a aplaudir. "O Sol voltou!", gritaram. Os animais diurnos saíram de seus abrigos, animados para um novo dia, enquanto os noturnos voltaram para suas cavernas e tocas, aliviados por poderem finalmente descansar. A Lua sorriu ao ver a Terra retornar ao seu equilíbrio natural. O Sol, mesmo ainda um pouco cansado, sentiu-se feliz por voltar a iluminar o mundo, sabendo que era insubstituível.

<p>Uma Lição Importante</p>
Antes de desaparecer no horizonte ao final do dia, o Sol refletiu: "Talvez eu realmente precise de uma folga de vez em quando, mas o mundo depende de mim. Da próxima vez, vou descansar durante a noite e deixar a Lua fazer seu trabalho." E assim, o Sol aprendeu uma importante lição sobre responsabilidade e equilíbrio, e o mundo voltou a sua rotina normal, com Sol durante o dia e Lua à noite.`,
    read: false,
    quiz: [
      {
        question: "Por que o Sol decidiu tirar um dia de folga?",
        options: ["Porque ele estava cansado de iluminar o mundo todos os dias.", "Porque estava chovendo.", "Porque a Lua pediu para ele descansar.", "Porque os humanos não precisavam mais de sua luz."],
        correctAnswer: 0
      },
      {
        question: "O que aconteceu com as pessoas quando o Sol não apareceu?",
        options: ["Elas foram dormir novamente.", "Elas não perceberam a falta do Sol.", "Elas fizeram uma festa para a Lua.", "Elas ficaram surpresas e confusas porque não amanhecia."],
        correctAnswer: 3
      },
      {
        question: "Como os animais noturnos reagiram à ausência do Sol?",
        options: ["Eles aproveitaram para caçar mais.", "Eles ficaram confusos, sem saber se deveriam dormir ou ficar acordados.", "Eles ficaram felizes por poder viver o dia todo na escuridão.", "Eles voltaram para suas tocas imediatamente."],
        correctAnswer: 1
      },
      {
        question: "Qual foi a solução que a Lua encontrou para lidar com a falta do Sol?",
        options: ["Ela decidiu brilhar com mais força para iluminar o dia.", "Ela foi conversar com o Sol para convencê-lo a voltar.", "Ela foi conversar com o Sol para convencê-lo a voltar.", "Ela decidiu deixar o mundo sem luz até o Sol voltar."],
        correctAnswer: 2
      },
      {
        question: "Como o Sol reagiu quando a Lua tentou convencê-lo a voltar?",
        options: ["Ele se recusou e pediu para a Lua cuidar do dia.", "Ele disse que precisava de mais tempo para descansar, mas acabou voltando.", "Ele concordou imediatamente e voltou para o céu.", "Ele se escondeu ainda mais."],
        correctAnswer: 1
      },
      {
        question: "Qual foi a lição que o Sol aprendeu ao final da história?",
        options: ["Que ele pode tirar folga quando quiser, sem avisar ninguém.", "Que o mundo não depende tanto dele quanto ele pensava.", "Que ele tem uma grande responsabilidade e deve descansar nos momentos apropriados.", "Que a Lua deveria assumir o papel de iluminar o mundo sempre."],
        correctAnswer: 2
      }
    ]
  },
  {
    id: 4,
    title: "A Girafa que Tinha Medo de Alturas",
    year: 2024,
    author: "Camilo Duvane",
    content: `<p>Gigi Descobre seu Medo</p>
Era uma vez, em uma vasta savana africana, onde vivia uma jovem girafa chamada Gigi. Gigi era alta, com um pescoço comprido como todas as girafas, mas havia algo que a diferenciava: ela tinha medo de alturas! Tudo começou em um dia ensolarado, quando Gigi estava comendo folhas do topo de uma árvore alta. Curiosa, ela olhou para baixo e sentiu um frio na barriga. "Ai, que alto!", pensou, tremendo um pouco. Suas longas pernas pareceram bambear e, naquele momento, ela descobriu que tinha um grande medo de olhar para baixo.

<p>Os Animais Tentam Ajudar</p>
A notícia sobre o medo de Gigi rapidamente se espalhou pela savana. Todos os outros animais ficaram surpresos: "Como uma girafa, que é tão alta, pode ter medo de altura?" Mas, ao invés de rirem dela, os amigos de Gigi decidiram ajudar. O elefante sugeriu: "Você deveria tentar subir em colinas pequenas e olhar para baixo, para se acostumar". O macaco, que adorava balançar nas árvores, disse: "Tente subir em uma árvore comigo, Gigi, e vamos balançar lá do alto!". Mas nada disso parecia funcionar. Cada vez que Gigi olhava para baixo, seu medo voltava.

<p>Gigi Pratica Olhar para Cima</p>
Desanimada, Gigi pensou que jamais superaria seu medo. Foi então que uma coruja sábia, que observava tudo de longe, deu um conselho diferente: "Gigi, ao invés de olhar para baixo, por que você não tenta olhar para cima? O céu é vasto e bonito. Quem sabe isso ajude a acalmar seu coração." Gigi ficou pensativa. "Olhar para cima? Nunca pensei nisso!" No dia seguinte, Gigi começou a praticar. Toda vez que sentia o medo chegar, ela olhava para o céu azul, para as nuvens fofas, e aos poucos começou a se sentir mais confiante. "O céu é lindo", pensava, "e não há nada a temer quando olho para cima."

<p>O Filhote de Pássaro em Perigo</p>
Certo dia, enquanto caminhava pela savana, Gigi ouviu um piado desesperado. Olhando para o alto de uma árvore, ela viu que um filhote de pássaro tinha caído do ninho e estava preso em um galho mais abaixo. A mãe pássaro voava em pânico ao redor, mas não conseguia alcançar o filhote. Gigi olhou em volta e percebeu que, por mais que outros animais quisessem ajudar, nenhum deles era alto o suficiente para alcançar o filhote. Ela sabia que só ela poderia salvá-lo. "Eu sou a única que pode fazer isso", pensou Gigi, seu coração acelerando.

<p>Gigi Supera seu Medo</p>
Com o filhote choramingando, Gigi sabia que não podia hesitar. Apesar de sentir o medo apertar em seu peito, ela lembrou-se do que havia aprendido: "Olhe para cima, Gigi!" Com determinação, ela ergueu a cabeça, olhou para o céu, e estendeu seu pescoço longo e elegante até o galho onde o filhote estava preso. Sem olhar para baixo, Gigi gentilmente pegou o filhote com sua boca e o devolveu ao ninho seguro. Todos os animais ao redor aplaudiram sua coragem. Gigi, surpresa com o que acabara de fazer, percebeu que, ao focar no que realmente importava — o filhote —, o medo desaparecera. Ela havia superado seu medo de altura!

<p>Uma Nova Giraffa</p>
Depois daquele dia, Gigi nunca mais teve medo de altura. Ela entendeu que às vezes nossos maiores medos podem ser superados quando nos concentramos em algo mais importante. Gigi continuou a olhar para o céu, mas agora, sempre que necessário, ela também conseguia olhar para baixo com confiança. A savana comemorava sua bravura, e Gigi, que antes tinha medo de ser tão alta, agora tinha orgulho de sua altura, sabendo que isso a tornava especial e capaz de grandes feitos.`,
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
      },
      {
        question: "Como os outros animais reagem ao medo de Gigi?",
        options: ["Eles riem dela.", "Eles ignoram seu medo.", "Eles dizem que ela deve ficar longe de alturas.", "Eles tentam ajudá-la a superar seu medo."],
        correctAnswer: 3
      },
      {
        question: "Qual conselho a coruja sábia dá a Gigi?",
        options: ["Olhar para cima em vez de para baixo.", "Ignorar seu medo.", "Olhar para cima", "Pedir ajuda a outros animais."],
        correctAnswer: 0
      },
      {
        question: "O que Gigi descobre sobre alturas ao salvar o filhote de pássaro?",
        options: ["Que alturas são sempre assustadoras.", "Que ela prefere ficar no chão.", "Que alturas não são tão assustadoras como ela pensava", "Que nunca mais quer subir em árvores"],
        correctAnswer: 2
      }
    ]
  },
  {
    id: 5,
    title: "O Peixe que Queria Voar",
    year: 2024,
    author: "Camilo Duvane",
    content: `Finn, o peixinho, olhava para o céu enquanto os pássaros voavam em grandes círculos. Seus olhos brilhavam com a ideia de fazer o mesmo. “Oh, como seria maravilhoso tocar as nuvens e sentir o vento nas nadadeiras!” ele pensava, sonhando em voar.

Determinada, Finn começou a praticar. Com todo o impulso que conseguia, ele nadava até a superfície e pulava para fora da água, esticando suas nadadeiras como asas. Mas, inevitavelmente, caía de volta na água com um splash. Ele tentava, tentava, mas o resultado era sempre o mesmo.

Um dia, enquanto tentava mais uma vez, uma gaivota chamada Gabi pousou na beira da água e o observou. "Por que você está tentando voar, Finn?", perguntou ela. Finn respondeu: "Quero ser livre como vocês, os pássaros." A gaivota sorriu com carinho e disse: "Ser livre não significa ser como os outros. Nós, pássaros, voamos no céu, mas vocês, peixes, têm um mundo imenso para explorar debaixo d'água."

Refletindo sobre as palavras de Gabi, Finn percebeu que podia “voar” de uma forma diferente, explorando o oceano com suas nadadeiras. Ele começou a nadar mais rápido, dando voltas e piruetas na água. Sentiu-se livre, sentiu-se feliz. Descobriu que, ao movimentar as nadadeiras e o corpo com agilidade, podia ‘voar’ debaixo d'água, como nunca havia pensado antes.

Finn, cheio de alegria, voltou para perto da superfície e chamou Gabi e os outros pássaros para verem. Ele fez um verdadeiro espetáculo aquático, girando, saltando e fazendo acrobacias. Os pássaros ficaram impressionados e aplaudiram seu talento. "Uau, Finn!", disseram eles, "você realmente sabe voar!". Finn, finalmente, sentiu que não precisava ser como os pássaros para sentir a liberdade que tanto desejava. Ele havia encontrado seu próprio voo. `,
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
  }, 


{
    id: 6,
    title: "A Formiga e a Cigarra",
    year: 2024,
    author: "Camilo Duvane",
    content: `Era uma vez, numa floresta cheia de vida, uma cigarra que passava os dias cantando e tocando sua música alegre. A cigarra adorava o verão, com seu calor acolhedor e abundância de comida. Ela passava os dias pulando de folha em folha, apreciando a vida ao máximo.

Enquanto isso, a formiga, sua vizinha, estava ocupada trabalhando arduamente. A formiga sabia que o verão não duraria para sempre. Ela coletava grãos e sementes, armazenando provisões para o inverno rigoroso que viria. Cada dia, ela saía cedo para trabalhar e voltava tarde, sempre carregando algo para o seu formigueiro.

<p>A cigarra observava a formiga e ria dela.</p>
– Formiga, por que você trabalha tanto? – perguntava a cigarra. – Venha cantar e aproveitar o verão! A vida é curta demais para desperdiçar com trabalho.

<p>A formiga, pacientemente, respondia:</p>
– Estou me preparando para o inverno. Quando o frio chegar, você verá que o meu trabalho valerá a pena. E você, cigarra, o que fará quando a neve cobrir tudo e não houver mais comida?

A cigarra apenas dava de ombros e continuava a cantar. Ela não conseguia imaginar que o verão algum dia acabaria.

Os dias quentes e ensolarados passaram rapidamente, e o outono chegou com seus ventos frios e folhas caindo. A cigarra começou a perceber a mudança no ar, mas ainda assim continuava a cantar, embora com menos entusiasmo.

Finalmente, o inverno chegou com toda a sua força. A floresta, antes cheia de vida, agora estava coberta de neve. As árvores estavam nuas, e não havia mais folhas ou grãos disponíveis. A cigarra, tremendo de frio e faminta, tentou encontrar algo para comer, mas tudo estava coberto de gelo.

<p>Desesperada, a cigarra foi até a casa da formiga. Bateu na porta, quase sem forças, e implorou: </p>
– Formiga, por favor, me ajude! Estou morrendo de fome e frio. Não tenho onde ficar nem o que comer.

A formiga abriu a porta e, ao ver a cigarra em tão mau estado, sentiu compaixão. Convidou a cigarra para entrar e deu-lhe um pouco de comida quente.

– Durante o verão, enquanto eu trabalhava, você só cantava. – disse a formiga. – Agora você vê a importância do trabalho e da preparação.

<p>A cigarra, arrependida, abaixou a cabeça. </p>
– Você tem razão, formiga. Eu fui tola em não me preparar para o inverno. Se você me permitir, prometo que no próximo verão trabalharei duro ao seu lado e nunca mais subestimarei a importância de estar preparada.

A formiga, sendo generosa e compassiva, aceitou a promessa da cigarra. E assim, durante todo o inverno, as duas viveram juntas, compartilhando a comida e o calor.

Quando o verão voltou, a cigarra cumpriu sua promessa. Trabalhou arduamente ao lado da formiga, coletando e armazenando provisões para o próximo inverno. E, de vez em quando, ainda encontrava tempo para cantar e tocar sua música, mas agora com a sabedoria de que o trabalho e a diversão podem coexistir de forma equilibrada.

Essa fábula destaca a importância do trabalho duro, da preparação e da responsabilidade, além de valorizar a compaixão e o perdão.`,
    read: false,
    quiz: [
      {
        question: "Qual é a principal diferença entre a formiga e a cigarra?",
        options: ["A formiga canta, enquanto a cigarra trabalha", "A formiga trabalha duro para se preparar, enquanto a cigarra se diverte sem se preocupar com o futuro", "A formiga é grande, e a cigarra é pequena", "A formiga não gosta de música, enquanto a cigarra toca instrumentos"],
        correctAnswer: 1
      },
      {
        question: "O que a formiga está fazendo durante o verão?",
        options: ["Coletando grãos e se preparando para o inverno", "Dormindo", "Procurando um lugar para morar", "Cantando e dançando"],
        correctAnswer: 0
      },
      {
        question: "Como a cigarra se sente quando o inverno chega?",
        options: ["Feliz e satisfeita", "Esperançosa e otimista", "Atraente e popular", "Fria e faminta"],
        correctAnswer: 3
      }
    ]
}, 
{
    id: 7,
    title: "A Travessia da Floresta - Uma Jornada de Coragem é Números",
    year: 2025,
    author: "Camilo Duvane",
    content: `Camilo Duvane, um jovem de 16 anos, vivia na pequena Vila Serenidade, cercada por uma floresta tão densa que parecia esconder segredos de eras esquecidas. O caminho até a escola, que ficava na cidade vizinha, exigia atravessar essa floresta. Poucos se arriscavam por lá, mas Camilo não tinha escolha. Seu sonho de se tornar contador e auditor não permitia que ele desistisse, não importava o quão perigoso fosse o trajeto.

<p>Primeiro Dia: O Começo do Desafio</p>
Com a mochila nas costas e uma calculadora no bolso, Camilo deu seus primeiros passos na floresta. Mal entrou na trilha e já sentiu que algo o observava. De repente, um rugido ensurdecedor ecoou. Um monstro gigantesco, com olhos brilhantes e presas afiadas, emergiu das sombras. Era uma criatura que parecia um cruzamento entre um gorila e um crocodilo.

Camilo, tremendo de medo, lembrou-se das aulas de matéria financeira. Ele pensou rápido: “Se isso fosse uma negociação, como eu apresentaria uma solução?” Usando sua lanterna, projetou uma sombra que assustou o monstro, dando-lhe tempo para correr.

“Preciso de um plano melhor se quiser sobreviver a isso todos os dias”, murmurou enquanto recuperava o fôlego.

<p>O Segundo Dia: Estratégia e Números</p>
Determinado a se preparar melhor, Camilo levou um caderno onde desenhou mapas e anotou tudo o que encontrava na floresta. No segundo dia, ao atravessar um rio, deparou-se com um monstro semelhante a uma serpente gigante que bloqueava sua passagem. Camilo usou um truque matemático: calculou a trajetória das pedras no rio para criar um caminho seguro. Jogando algumas pedras para distrair a serpente, atravessou o rio ileso. Ele sentiu uma pequena vitória e anotou: “É tudo uma questão de resolver problemas.”

<p>O Terceiro Dia: Aliados Inesperados</p>
No terceiro dia, Camilo encontrou macacos agitados que o alertaram para o perigo. Agradecendo pela ajuda, ofereceu uma fruta e, em troca, os macacos passaram a segui-lo como guias. Ao longo do caminho, enfrentaram juntos um monstro com corpo de árvore e tentáculos que prendiam quem tentasse passar. Camilo usou um truque: desenhou um esquema financeiro na terra, distraindo o monstro enquanto os macacos criavam uma rota alternativa.

“Quem diria que até monstros se interessam por planejamento financeiro?”, ele brincou.

<p>Uma Semana de Surpresas</p>
Com o passar dos dias, Camilo começou a observar padrões no comportamento dos monstros. Em uma manhã nebulosa, deparou-se com um gigante feito de rochas que bloqueava o caminho. O monstro parecia inabalável, mas Camilo percebeu que ele se movia de forma lenta e previsível. Usando um cronograma que rabiscou em seu caderno, esperou pelos momentos exatos para avançar entre as passadas pesadas da criatura. No fim do dia, anotou em seu diário: “Análise de padrões e gestão de tempo funcionam até com monstros.”

Em outra ocasião, a floresta se encheu de uma névoa espessa que fazia Camilo perder o rumo. Ele calculou a direção usando um relógio de sol improvisado e os mapas que desenhara. No caminho, encontrou um esquilo que parecia saber onde estava indo. Camilo o seguiu, apenas para descobrir que o pequeno animal o estava levando a uma clareira onde ele enfrentaria uma aranha gigante com oito olhos flamejantes.

Desta vez, Camilo usou lógica simples: distraiu a criatura com reflexos de luz usando um pequeno espelho da mochila, criando confusão suficiente para escapar. 

<p>Um Mês Depois: O Enigma do Labirinto Vivo</p>
Após semanas de travessias desafiadoras, Camilo encontrou o que parecia ser um labirinto formado por árvores que se moviam lentamente, mudando de posição sempre que ele escolhia um caminho. Ele lembrou-se das aulas de probabilidade e começou a marcar cada rota que já havia tentado. Depois de várias tentativas, conseguiu atravessar o labirinto e deixou um registro detalhado do trajeto para futuras viagens.

Ao sair do labirinto, encontrou Luna, uma garota corajosa que também atravessava a floresta. Ela revelou que seu objetivo era semelhante ao de Camilo: chegar à escola e alcançar seus sonhos. Juntos, começaram a enfrentar os desafios, combinando suas habilidades e desenvolvendo estratégias cada vez mais eficazes.

<p>O Terceiro Ano: A União Faz a Força</p>
No terceiro ano, os monstros da floresta pareciam estar mais organizados. Camilo e Luna começaram a observar que algumas criaturas agiam em grupos, formando verdadeiras emboscadas. Eles criaram um sistema de comunicação com apitos e sinais visuais para alertar um ao outro de perigos iminentes.

Certa vez, enfrentaram um grupo de pássaros gigantes que atacavam em revoada. Camilo usou sua habilidade de cálculos rápidos para prever as trajetórias dos pássaros, enquanto Luna usava uma funda para derrubar alguns e criar uma rota de fuga. “Auditoria de riscos nunca foi tão literal”, Camilo comentou com um sorriso nervoso.

<p>O Quarto Ano: A Jornada Final</p>
Durante os quatro anos de travessias diárias, Camilo aprendeu a lidar com os desafios da floresta usando sua paixão pela contabilidade. Ele criou estratégias baseadas em análises de risco, fez anotações detalhadas sobre os monstros e suas fraquezas e desenvolveu um sistema para economizar energia e tempo.

No último dia antes de se formar no ensino geral, a floresta parecia mais ameaçadora do que nunca. Uma tempestade tornava o caminho quase intransitável, e monstros gigantes cercavam a trilha. Mas Camilo estava pronto. Ele usou um plano detalhado, onde cada passo era calculado. Usou até mesmo estatísticas para prever o comportamento dos monstros e atravessou a floresta com sucesso.

Ao chegar à escola, sentiu uma mistura de alívio e orgulho. Sua dedicação aos estudos o levou a ser aceito em uma renomada universidade, onde se especializou em Contabilidade e Auditoria.

<p>A Formação e a Distinção de Honra</p>
Na faculdade, Camilo aplicou tudo o que aprendeu na floresta. Suas análises financeiras eram tão precisas quanto os planos que usava para escapar de monstros. Em sua formatura, recebeu uma distinção de honra pelo excelente desempenho acadêmico.

Durante o discurso, Camilo disse: “A contabilidade me salvou da floresta, e os números me mostraram que, com coragem e planejamento, podemos enfrentar qualquer desafio. Nunca desistam de seus sonhos, mesmo que haja monstros no caminho."`,
    read: false,
    quiz: [
      {
question: "Qual era o principal objetivo de Camilo ao atravessar a floresta diariamente?",
      options: ["Buscar frutas raras para vender", "Ir à escola para realizar o sonho de ser contador e Auditor", "Explorar a floresta para escrever um livro", "Fugir da vila Serenidade"],
      correctAnswer: 1
      },

      question: "O que Camilo usou para assustar o monstro no primeiro dia?",
      options: ["Uma pedra", "Uma sombra projetada pela lanterna", "Um grito alto", "Um esquema financeiro"],
      correctAnswer: 1

question: "Como Camilo conseguiu atravessar o rio bloqueado pela serpente gigante?", 
options: ["Pulando diretamente sobre a serpente", "Usando um barco improvisado", "Jogando pedras para distraí-la e calculando a trajetória segura", "Chamando ajuda dos macaco"], 
correctAnswer: 2

queation: "Qual foi a primeira aliança formada por Camilo na floresta?", 
options: ["Com Luna, a garota corajosa", "Com macacos que o ajudaram a identificar perigos", "Com um esquilo que o guiou", "Com o monstro rochoso"],
correctAnswer: 1

question: "O que Camilo encontrou no labirinto vivo", 
options: ["Um caminho direto para a escola", "Luna, que também atravessava a floresta", "Um grupo de pássaros gigantes em revoada", "Um esquilo com um mapa mágico"], 
correctAnswer: 1

      question: "Qual foi o principal ensinamento da história de Camilo?" 
      options: ["Evitar florestas perigosas a todo custo", "A união faz a força em tempos difíceis", "Planejamento, coragem e análise podem superar qualquer desafio", "A contabilidade é uma ferramenta apenas para a vida académica"], 
      correctAnswer: 2
      }
    ]
  },




















  
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
