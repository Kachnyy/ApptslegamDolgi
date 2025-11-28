<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Долговой помощник</title>
<style>
    body {
        font-family: 'Segoe UI', sans-serif;
        background-color: #f7f7f7;
        margin: 0;
        padding: 0;
        color: #222;
    }
    header {
        background-color: #2c3e50;
        color: #fff;
        text-align: center;
        padding: 20px;
    }
    header h1 {
        margin: 0;
        font-size: 24px;
    }
    .services {
        padding: 20px;
        display: flex;
        flex-direction: column;
        gap: 15px;
    }
    .service {
        background: #fff;
        border-radius: 8px;
        padding: 15px;
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    .service h2 {
        margin: 0 0 10px 0;
        font-size: 18px;
        color: #34495e;
    }
    .service p {
        margin: 0 0 5px 0;
        font-size: 14px;
    }
    .price {
        font-weight: bold;
        color: #e74c3c;
    }
    .form-container {
        padding: 20px;
        background: #ecf0f1;
        border-radius: 8px;
        margin: 20px;
    }
    .form-container input, .form-container select {
        width: 100%;
        padding: 10px;
        margin: 8px 0;
        border-radius: 5px;
        border: 1px solid #ccc;
        box-sizing: border-box;
    }
    .form-container button {
        background-color: #2c3e50;
        color: #fff;
        padding: 12px;
        border: none;
        border-radius: 5px;
        width: 100%;
        font-size: 16px;
        cursor: pointer;
    }
    .form-container button:hover {
        background-color: #34495e;
    }
</style>
</head>
<body>

<header>
    <h1>Добро пожаловать в Долговой помощник</h1>
    <p>Работаем по делу, минимизируем риски, сохраняем спокойствие</p>
</header>

<section class="services">
    <div class="service">
        <h2>Разбор долговой ситуации <span class="price">2 000 ₽</span></h2>
        <p>🔍 Анализ всей картины: кто давит, риски, слабые и сильные стороны.</p>
        <p>📌 Получаешь чёткий план на ближайший месяц.</p>
    </div>
    <div class="service">
        <h2>Переговоры с кредиторами <span class="price">4 500 ₽</span></h2>
        <p>Ты присылаешь диалог, угрозы. Я готовлю стратегию, аргументацию и линию поведения.</p>
    </div>
    <div class="service">
        <h2>Переговоры “под ключ” <span class="price">10 000 ₽</span></h2>
        <p>Полное ведение процесса: стратегия, ответы, давление, сценарий на несколько шагов.</p>
    </div>
    <div class="service">
        <h2>Подготовка к встречам с кредиторами <span class="price">3 000 ₽</span></h2>
        <p>Уверенность и психологическое преимущество на переговорах.</p>
    </div>
    <div class="service">
        <h2>Консультация по банкротству <span class="price">5 000 ₽</span></h2>
        <p>Анализ: подходит ли банкротство, риски, имущество, документы, ходы заранее.</p>
    </div>
    <div class="service">
        <h2>Сопровождение банкротства <span class="price">от 20 000 ₽</span></h2>
        <p>Весь путь под контролем: документы, подсказки, кредиторы, минимизация ошибок.</p>
    </div>
    <div class="service">
        <h2>Доступ к людям в ФССП <span class="price">5 000 ₽</span></h2>
        <p>Консультации: как общаться с приставом, заявления, снятие ограничений.</p>
    </div>
    <div class="service">
        <h2>Full Support <span class="price">30 000 ₽ / месяц</span></h2>
        <p>Максимальный пакет: разбор, стратегия, переговоры, сопровождение, 24/7 поддержка.</p>
    </div>
</section>

<section class="form-container">
    <h2>Оставить заявку</h2>
    <input type="text" id="name" placeholder="Ваше имя" required>
    <input type="text" id="contact" placeholder="Телеграм или телефон" required>
    <select id="service">
        <option value="" disabled selected>Выберите услугу</option>
        <option>Разбор долговой ситуации</option>
        <option>Переговоры с кредиторами</option>
        <option>Переговоры “под ключ”</option>
        <option>Подготовка к встречам с кредиторами</option>
        <option>Консультация по банкротству</option>
        <option>Сопровождение банкротства</option>
        <option>Доступ к людям в ФССП</option>
        <option>Full Support</option>
    </select>
    <button onclick="submitForm()">Отправить заявку</button>
</section>

<script>
function submitForm() {
    const name = document.getElementById('name').value.trim();
    const contact = document.getElementById('contact').value.trim();
    const service = document.getElementById('service').value;

    if(!name || !contact || !service) {
        alert('Пожалуйста, заполните все поля!');
        return;
    }

    // Telegram WebApp integration
    if(window.Telegram.WebApp) {
        window.Telegram.WebApp.sendData(JSON.stringify({name, contact, service}));
        alert('Заявка отправлена! Мы свяжемся с вами.');
    } else {
        alert('Заявка сохранена локально (для теста).');
        console.log({name, contact, service});
    }

    document.getElementById('name').value = '';
    document.getElementById('contact').value = '';
    document.getElementById('service').value = '';
}
</script>

</body>
</html>
