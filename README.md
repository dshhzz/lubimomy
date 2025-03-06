<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Поздравление с пол года</title>
    <style>
        body {
            background-color: pink;
            font-family: Arial, sans-serif;
            text-align: center;
            color: purple;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .content {
            display: none;
            text-align: center;
        }
        .btn, .back-btn {
            background-color: #ff69b4;
            padding: 20px;
            font-size: 20px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            margin-top: 20px;
        }
        .container {
            margin-top: 50px;
        }
        img {
            width: 300px;
            height: auto;
            border-radius: 15px;
        }
        .button-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }
        .large-btn {
            padding: 30px 50px;
            font-size: 24px;
            background-color: #ff69b4;
            border-radius: 15px;
            cursor: pointer;
        }
        .gallery img {
            width: 200px;
            height: auto;
            margin: 10px;
            border-radius: 10px;
        }
        /* Анимация для конверта */
        #envelope {
            width: 200px;
            height: 150px;
            background-color: #ff69b4;
            border-radius: 15px;
            margin: 0 auto;
            position: relative;
        }

        #envelope:before {
            content: "";
            position: absolute;
            top: -20px;
            left: 10px;
            width: 180px;
            height: 10px;
            background-color: #fff;
            border-radius: 5px;
        }

        #letter {
            display: none;
            animation: slideIn 2s forwards;
        }

        @keyframes slideIn {
            0% {
                transform: translateY(100%);
            }
            100% {
                transform: translateY(0);
            }
        }

    </style>
</head>
<body>

<!-- Главная страница -->
<div id="home-page" class="content" style="display:block;">
    <h1>Поздравляю с пол года, любимый</h1>
    <img src="main.jpg" alt="Фото любимого">
    <br>
    <button class="btn" onclick="showButtons()">Нажми</button>
</div>

<!-- Страница с кнопками-прямоугольниками -->
<div id="button-page" class="content">
    <h1>Выберите раздел</h1>
    <div class="button-container">
        <button class="large-btn" onclick="showLovePage()">Почему я тебя люблю</button>
        <button class="large-btn" onclick="showGalleryPage()">Наши фоточки</button>
        <button class="large-btn" onclick="showCongratsPage()">Поздравляю!!</button>
    </div>
    <button class="back-btn" onclick="goBack('home-page')">Назад</button>
</div>

<!-- Страница "Почему я тебя люблю" -->
<div id="love-page" class="content">
    <h1>Почему я тебя люблю</h1>
    <div class="button-container">
        <button class="large-btn" onclick="showText(1)">Нажми</button>
        <button class="large-btn" onclick="showText(2)">Нажми</button>
        <button class="large-btn" onclick="showText(3)">Нажми</button>
        <button class="large-btn" onclick="showText(4)">Нажми</button>
        <button class="large-btn" onclick="showText(5)">Нажми</button>
    </div>
    <div id="love-text" style="margin-top: 30px; font-size: 20px;"></div>
    <div id="love-image" style="margin-top: 20px;"></div> <!-- Место для изображения -->
    <button class="back-btn" onclick="goBack('button-page')">Назад</button>
</div>

<!-- Страница "Наши фоточки" -->
<div id="gallery-page" class="content">
    <h1>Наши фоточки</h1>
    <div class="gallery-container">
        <button class="arrow left" onclick="prevImage()">&#10094;</button>
        <img id="gallery-image" src="your-image1.jpg" alt="Фото 1">
        <button class="arrow right" onclick="nextImage()">&#10095;</button>
    </div>
    <button class="back-btn" onclick="goBack('button-page')">Назад</button>
</div>

<style>
    .gallery-container {
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        width: 500px; /* Размер галереи */
        margin: 0 auto;
    }

    #gallery-image {
        width: 450px; /* Ширина изображения */
        height: auto;
        border-radius: 15px;
    }

    .arrow {
        background-color: transparent;
        border: none;
        font-size: 30px;
        cursor: pointer;
        margin: 0 10px;
    }
</style>

<script>
    let currentImageIndex = 0;
    const imagePaths = [
        "6.jpg",
        "7.jpg",
        "8.jpg",
        "9.jpg",
        "10.jpg",
        "11.jpg",
        "12.jpg"
    ];
    
    const galleryImage = document.getElementById("gallery-image");

    function updateGallery() {
        galleryImage.src = imagePaths[currentImageIndex];
    }

    function prevImage() {
        currentImageIndex = (currentImageIndex - 1 + imagePaths.length) % imagePaths.length;
        updateGallery();
    }

    function nextImage() {
        currentImageIndex = (currentImageIndex + 1) % imagePaths.length;
        updateGallery();
    }
</script>
<!-- Страница "Поздравляю!!" -->
<div id="congrats-page" class="content">
    <h1>Поздравляю нас с пол года!</h1>
    <div id="envelope">
        <button class="btn" onclick="openEnvelope()">Открыть письмо</button>
    </div>
    <div id="letter" style="display:none; font-size: 24px; margin-top: 30px;">
        <p>Любимый Бодечка, поздравляю нас с пол года наших отношений. Я очень рада, что мы с тобой познакомились, встретились, и рада, что встретились именно так. Я безумно дорожу нашими отношениями и хочу чтоб мы были вместе всегда. Спасибо тебе за все моменты, за все подарки, за все твое внимание и старания и прости, если я что-то делаю не так, но я очень стараюсь для нас. Просто знай, что я очень тебя люблю и ценю. Eres mio💋</p>
    </div>
    <button class="back-btn" onclick="goBack('button-page')">Назад</button>
</div>

<script>
    function showButtons() {
        document.getElementById('home-page').style.display = 'none';
        document.getElementById('button-page').style.display = 'block';
    }

    function showLovePage() {
        document.getElementById('button-page').style.display = 'none';
        document.getElementById('love-page').style.display = 'block';
    }

    function showGalleryPage() {
        document.getElementById('button-page').style.display = 'none';
        document.getElementById('gallery-page').style.display = 'block';
    }

    function showCongratsPage() {
        document.getElementById('button-page').style.display = 'none';
        document.getElementById('congrats-page').style.display = 'block';
    }

    function showText(buttonId) {
        let text = '';
        let image = '';
        if (buttonId === 1) {
            text = 'Самый красивый котик, самый симпатичный и милый, вечность бы смотрела в твои глазки';
            image = '<img src="photo1.jpg" alt="Фото 1">';
        } else if (buttonId === 2) {
            text = 'Самый заботливый, люблю когда целуешь ножки и ухаживаешь за мной';
            image = '<img src="2.jpg" alt="Фото 2">';
        } else if (buttonId === 3) {
            text = 'Самый добрый, и люблю, когда стараешься ради меня';
            image = '<img src="3.jpg" alt="Фото 3">';
        } else if (buttonId === 4) {
            text = 'Мой страстный хихих';
            image = '<img src="4.jpg" alt="Фото 4">';
        } else if (buttonId === 5) {
            text = 'Люблю тебя за то, что ты есть в моей жизни';
            image = '<img src="5.jpg" alt="Фото 5">';
        }
        document.getElementById('love-text').innerText = text;
        document.getElementById('love-image').innerHTML = image; // Показываем фотографию
    }

    function openEnvelope() {
        document.getElementById('envelope').style.display = 'none';
        document.getElementById('letter').style.display = 'block';
    }

    function goBack(pageId) {
        const pages = document.querySelectorAll('.content');
        pages.forEach(page => page.style.display = 'none');
        document.getElementById(pageId).style.display = 'block';
    }
</script>

</body>
</html>
