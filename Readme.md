<p align="center">
  <img src="https://github.com/Abdujalil2107/Gif/blob/main/canva_2.gif" alt="My profile gif" width="100%" />
</p>

![logo](https://github.com/Abdujalil2107/Abdujalil2107/blob/main/Blue%20Yellow%20Futuristic%20Virtual%20Technology%20Blog%20Banner%20(1600%20%C3%97%20800%20px).gif)
<h1 align="center" style="color: #2E8B57;">Hi 👋, I'm Abdujalil</h1>
<h3 align="center" style="color: #4682B4;">"Connecting the Physical World to the Digital: Development on GitHub"</h3>

<img align="right" alt="Hacking" width="400" src="https://media.tenor.com/GfSX-u7VGM4AAAAC/coding.gif">

<p align="center"> 
  <img src="https://komarev.com/ghpvc/?username=Abdujalil2107&label=Profile%20views&color=0e75b6&style=flat" alt="Abdujalil2107" style="border-radius: 10px; background-color: #f0f8ff; padding: 5px;"/> 
</p>

<div align="center" style="border: 2px solid #4682B4; border-radius: 10px; background-color: #f0f8ff; padding: 15px; width: 80%; margin: 10px auto;">
    <p style="margin: 0; font-size: 1.2em;">📈 <strong style="color: #2E8B57;">Currently Learning:</strong> <span style="font-weight: bold;">Python 😊</span></p>
    <p style="margin: 0; font-size: 1.2em;">⚡ <strong style="color: #2E8B57;">Fun Fact:</strong> <span style="font-weight: bold;">"Don't chase after companies"</span></p>
</div>

### 🤝 Connect with me:
<p align="left">
<a href="https://twitter.com/Nizomiddinov_A" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="twitter" height="30" width="40" /></a>
<a href="https://linkedin.com/in/abdujalil-nizomiddinov" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="linkedin" height="30" width="40" /></a>
<a href="https://facebook.com/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/facebook.svg" alt="facebook" height="30" width="40" /></a>
<a href="https://www.youtube.com/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" alt="youtube" height="30" width="40" /></a>
<a href="https://www.codechef.com/" target="blank"><img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.1.0/icons/codechef.svg" alt="codechef" height="30" width="40" /></a>
</p>

### 🛠️ Languages and Tools:
<p align="left"> 
    <a href="https://www.python.org/" target="_blank" rel="noreferrer" style="display: inline-block;"> 
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" width="40" height="40"/>
    </a>
    <a href="https://en.wikipedia.org/wiki/C_(programming_language)" target="_blank" rel="noreferrer" style="display: inline-block;">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="C" width="40" height="40"/>
    </a>
    <a href="https://www.mathworks.com/" target="_blank" rel="noreferrer" style="display: inline-block;"> 
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/Matlab_Logo.png" alt="MATLAB" width="40" height="40"/>
    </a>
</p>

### 📊 GitHub Stats
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Abdujalil2107&show_icons=true&theme=radical&hide_title=true" alt="GitHub Stats" width="100%"/>
</p>







<style>
  #game {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    width: 400px;
    height: 400px;
    border: 2px solid #4682B4;
    background-color: #f0f8ff;
    margin: 20px auto;
    overflow: hidden;
  }

  .snake {
    background-color: #2E8B57;
    position: absolute;
  }

  .food {
    background-color: #ff4500;
    position: absolute;
  }
</style>

<div id="game"></div>

<script>
  const gameArea = document.getElementById('game');
  const gameSize = 20;
  let snake = [{ x: 9, y: 9 }];
  let food = { x: 5, y: 5 };
  let direction = { x: 0, y: 0 };
  let score = 0;

  function draw() {
    gameArea.innerHTML = '';
    snake.forEach(segment => {
      const snakeElement = document.createElement('div');
      snakeElement.classList.add('snake');
      snakeElement.style.width = `${gameSize}px`;
      snakeElement.style.height = `${gameSize}px`;
      snakeElement.style.left = `${segment.x * gameSize}px`;
      snakeElement.style.top = `${segment.y * gameSize}px`;
      gameArea.appendChild(snakeElement);
    });

    const foodElement = document.createElement('div');
    foodElement.classList.add('food');
    foodElement.style.width = `${gameSize}px`;
    foodElement.style.height = `${gameSize}px`;
    foodElement.style.left = `${food.x * gameSize}px`;
    foodElement.style.top = `${food.y * gameSize}px`;
    gameArea.appendChild(foodElement);
  }

  function moveSnake() {
    const head = { x: snake[0].x + direction.x, y: snake[0].y + direction.y };
    
    if (head.x === food.x && head.y === food.y) {
      score++;
      food = { x: Math.floor(Math.random() * (gameArea.clientWidth / gameSize)), 
               y: Math.floor(Math.random() * (gameArea.clientHeight / gameSize)) };
    } else {
      snake.pop();
    }

    snake.unshift(head);
  }

  function gameLoop() {
    moveSnake();
    draw();
    setTimeout(gameLoop, 100);
  }

  document.addEventListener('keydown', event => {
    if (event.key === 'ArrowUp') {
      direction = { x: 0, y: -1 };
    } else if (event.key === 'ArrowDown') {
      direction = { x: 0, y: 1 };
    } else if (event.key === 'ArrowLeft') {
      direction = { x: -1, y: 0 };
    } else if (event.key === 'ArrowRight') {
      direction = { x: 1, y: 0 };
    }
  });

  draw();
  gameLoop();
</script>





