<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>生日快乐！熊熊</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to top right, #ffe6f0, #e0f7fa);
      overflow: hidden;
      text-align: center;
    }
    h1 {
      font-size: 3em;
      margin-top: 50px;
      color: #ff4081;
    }
    #prompt {
      font-size: 1.2em;
      color: #888;
      margin-top: 10px;
      animation: fadeIn 1.5s infinite alternate;
    }
    @keyframes fadeIn {
      from { opacity: 0.5; }
      to { opacity: 1; }
    }
    #typewriter {
      width: 80%;
      height: 300px;
      margin: 30px auto;
      font-size: 1.5em;
      color: #444;
      white-space: pre-wrap;
      border-left: 3px solid #ff4081;
      padding-left: 10px;
      animation: caret 0.75s steps(1) infinite;
      display: none;
      overflow-y: auto;
      background: rgba(255,255,255,0.7);
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    @keyframes caret {
      50% { border-color: transparent; }
    }
  </style>
</head>
<body>
  <h1>生日快乐熊熊 🎉</h1>

  <div id="prompt">☞点击这里，接收祝福吧！🎈</div>

  <div id="typewriter"></div>

  <audio id="bgm" src="https://drive.google.com/uc?export=download&id=1hwnCt5nYmzeztridRSKsrPWryOcyHnpr" preload="auto"></audio>

   <script>
    const message = `熊熊，生日快乐～🎂\n\n\n在这个特别的日子里，我想对你说\n\n愿你一生努力，一生被爱\n\n想要的都拥有，得不到的都释怀\n\n愿你所有的辛劳与付出都能有美好的回报\n\n愿你无论在哪里，都能感受到爱与温暖\n\n身边的人都能给你带来无尽的欢笑与力量\n\n只愿你被这世界温柔相待，遇到的每一份温情都如同阳光，照亮你前行的路，给你带来满满的勇气与希望！🎈\n\n\n愿你笑口常开，愿你心事有解\n\n\n愿你眼里总是闪烁着光芒，愿你脚下的每一步都带着风，轻盈又坚定。未来的路上，不管你遇到什么，我都会在你身边\n\n陪着你一起走，一起笑，一起闯，一起经历所有美好的时光。\n\n\n祝你在新的一岁里，吃得开心，睡得香甜\n\n天天都能够笑出声，做自己喜欢的事\n\n遇到真心对待你的人，每一刻都觉得是值得的\n\n愿你每天都有无尽的精力去追求梦想\n\n无论多小的目标，都会因你的努力而闪闪发光\n\n每一步都走得坚定又自信!\n\n\n想永远和你做彼此心事的靠山\n\n想和你一起好奇、一起玩乐\n\n每一次的交流都像是重新认识你一样，有那么多的故事、那么多的欢笑\n\n\n\n生日快乐\n\n祝你越来越有钱\n\n越来越漂亮\n\n越来越自由\n\n越来越幸福\n\n\n希望你每一年都比上一年更加优秀、更加独立、更加闪耀!\n\n\t\t\t\t\t\t\t—— 来自方块 💛`;

    function showMessage() {
      const typewriter = document.getElementById('typewriter');
      typewriter.style.display = 'block';
      typewriter.innerText = '';
      let index = 0;
      function type() {
        if (index < message.length) {
          typewriter.innerText += message[index++];
          typewriter.scrollTop = typewriter.scrollHeight;
          setTimeout(type, 50);
        }
      }
      type();
    }

    const prompt = document.getElementById('prompt');
    const bgm = document.getElementById('bgm');

    prompt.onclick = () => {
      prompt.style.display = 'none';
      bgm.play().catch(e => console.warn('音乐播放失败：', e)); // 触发播放
      showMessage();
    };
  </script>
</body>
</html>
