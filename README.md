<!DOCTYPE html>
<html>
<head>
<title>Анимация по наведению</title>
<style>
  .card {
    width: 200px;
    height: 200px;
    margin: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    overflow: hidden;
    cursor: pointer;
    position: relative; /* Для позиционирования элементов внутри карточки */
    transition: all 0.3s ease; /* Плавный переход для анимации */
  }

  .card:hover {
    transform: scale(1.1); /* Увеличение карточки при наведении */
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2); /* Тень */
  }

  .card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease; /* Плавный переход для анимации изображения */
  }

  .card:hover img {
    transform: scale(1.2); /* Увеличение изображения при наведении */
  }

  .card-text {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 10px;
    color: #fff;
    background-color: rgba(0, 0, 0, 0.5);
    opacity: 0; /* Скрываем текст по умолчанию */
    transition: opacity 0.3s ease; /* Плавный переход для анимации */
  }

  .card:hover .card-text {
    opacity: 1; /* Показывать текст при наведении */
  }

  /* Дополнительный стиль для отображения информации при клике */
  .card-info {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background-color: #fff;
    padding: 10px;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }

  .card:hover .card-info {
    display: block;
  }
</style>
</head>
<body>

  <div class="card">
    <img src="https://picsum.photos/200/200" alt="Картинка">
    <div class="card-text">
      Текст для карточки 1
    </div>
    <div class="card-info">
      Дополнительная информация для карточки 1
    </div>
  </div>

  <div class="card">
    <img src="https://picsum.photos/200/200" alt="Картинка">
    <div class="card-text">
      Текст для карточки 2
    </div>
    <div class="card-info">
      Дополнительная информация для карточки 2
    </div>
  </div>

  <div class="card">
    <img src="https://picsum.photos/200/200" alt="Картинка">
    <div class="card-text">
      Текст для карточки 3
    </div>
    <div class="card-info">
      Дополнительная информация для карточки 3
    </div>
  </div>

  <script>
    // Получаем все карточки
    const cards = document.querySelectorAll('.card');

    // Добавляем обработчик события 'click' для каждой карточки
    cards.forEach(card => {
      card.addEventListener('click', () => {
        // Получаем блок с информацией
        const info = card.querySelector('.card-info');

        // Если блок информации скрыт, показываем его
        if (info.style.display === 'none') {
          info.style.display = 'block';
        } else {
          // Иначе скрываем блок информации
          info.style.display = 'none';
        }
      });
    });
  </script>

</body>
</html>

