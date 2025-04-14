<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Пробный тест для госслужбы</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f9f9f9;
      padding: 20px;
      max-width: 700px;
      margin: auto;
    }
    h1, h2 {
      color: #333;
    }
    .question {
      margin-bottom: 20px;
      background: #fff;
      padding: 15px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .question p {
      font-weight: bold;
    }
    .options label {
      display: block;
      margin: 5px 0;
    }
    button {
      padding: 10px 20px;
      background: #007bff;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
    }
    #result {
      margin-top: 30px;
      font-size: 18px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Пробный тест для госслужбы</h1>
  <form id="quizForm">
    <div class="question">
      <p>1. Какой орган осуществляет исполнительную власть в РК?</p>
      <div class="options">
        <label><input type="radio" name="q1" value="0"> А) Парламент</label>
        <label><input type="radio" name="q1" value="0"> Б) Верховный суд</label>
        <label><input type="radio" name="q1" value="1"> В) Правительство</label>
        <label><input type="radio" name="q1" value="0"> Г) Акимат</label>
      </div>
    </div>
    <div class="question">
      <p>2. Кто принимает Конституцию РК?</p>
      <div class="options">
        <label><input type="radio" name="q2" value="1"> А) Народ на референдуме</label>
        <label><input type="radio" name="q2" value="0"> Б) Президент</label>
        <label><input type="radio" name="q2" value="0"> В) Парламент</label>
        <label><input type="radio" name="q2" value="0"> Г) Конституционный совет</label>
      </div>
    </div>
    <button type="button" onclick="checkAnswers()">Проверить результат</button>
  </form>
  <div id="result"></div>

  <script>
    function checkAnswers() {
      let form = document.getElementById('quizForm');
      let result = 0;
      let total = 2; // всего вопросов

      let q1 = form.q1.value;
      let q2 = form.q2.value;

      result += parseInt(q1 || 0);
      result += parseInt(q2 || 0);

      let percent = Math.round((result / total) * 100);

      document.getElementById('result').innerText = `Вы набрали ${result} из ${total} правильных ответов (${percent}%)`;
    }
  </script>
</body>
</html>
