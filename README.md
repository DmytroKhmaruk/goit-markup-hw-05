# goit-markup-hw-05
+ «A1» Всі стилі написані в одному файлі styles.css, який знаходиться в папці css.

+ «A2» Вихідний код відформатований за допомогою Prettier.

+ «A3» Всі зображення та текстовий контент взяті з макета.

+ «A4» На всіх HTML-сторінках підключений нормалізатор стилів modern-normalize.

+ «A5» Код написаний з дотриманням настанови.

+ «A6» Скрипт модального вікна підключений в HTML окремим файлом modal.js.

Розмітка
+ «B1» Виконана HTML-розмітка всіх елементів макету.

+ «B2» Теги використані відповідно до їх семантичного змісту.

Оформлення
+ «C1» Для всіх ефектів ховер і фокуса (колір, фон, тінь) зроблені переходи. Час - 250ms, функція розподілу часу - cubic-bezier(0.4, 0, 0.2, 1).

+ «C2» У переходах та анімаціях явно зазначені анімовані властивості. Ніде немає значення all.

+ «C3» В секції Чим ми займаємось текст з фоном спозиційований поверх зображення.

+ «C4» В головній навігації, за допомогою псевдоелемента ::after, зроблено підкреслення посилання поточної сторінки (на якій зараз знаходиться користувач).

+ «C5» Синій оверлей з текстом на картках сторінки Портфоліо з'являється при ховері в будь-якому місці картки.

+ «C6» Синій оверлей в картках сторінки Портфоліо виїжджає знизу, як показано на відео.

+ «C7» У псевдоелементів відсутній текстовий контент у властивості content. Вони використані виключно для декоративного оформлення.

Модальне вікно

+ «D1» Виконана розмітка і оформлення «бекдропа» (темного напівпрозорого фону) модального вікна.

+ «D2» «Бекдроп» заповнює 100% висоти і ширини в'юпорту браузера і фіксований в ньому.

+ «D3» Виконана розмітка і оформлення модального вікна.

+ «D4» Модальне вікно вертикально і горизонтально спозиційоване посередині бекдропа.

+ «D5» Виконана розмітка і оформлення кнопки закриття модального вікна у верхньому правому куті.

+ «D6» Спочатку модальне вікно і бекдроп приховані за допомогою класу is-hidden на бекдропі, в селекторі якого використовуються властивості visibility, opacity і pointer-events.

+ «D7» Якщо прибрати з бекдропа клас is-hidden - з'являється бекдроп і модальне вікно.

+ «D8» Поява і приховування модального вікна анімовано за допомогою переходу з довільним ефектом, наприклад scale або translate, і opacity.

Відкриття/закриття модального вікна

+ Модальне вікно з формою заявки відкривається по натисканню на кнопку "Замовити послугу". Для того щоб скрипт спрацював, необхідно додати до розмітки спеціальні атрибути, за якими скрипт шукає елементи:

+ data-modal-open - на кнопку відкриття модального вікна.
+ data-modal-close - на кнопку закриття модального вікна.
+ data-modal - на бекдроп модального вікна.
+ Після чого, перед закриваючим тегом body додати тег script з посиланням на файл скрипту для модально вікна. Можна подивитися відео-інструкцію.

<body>
  <!-- Вся твоя розмітка, включно з розміткою модалки -->

  <!-- Ставимо перед закриваючим тегом body -->
  <script src="./js/modal.js"></script>
</body>

+ Скрипт, який необхідно скопіювати і вставити у файл modal.js.

(() => {
  const refs = {
    openModalBtn: document.querySelector("[data-modal-open]"),
    closeModalBtn: document.querySelector("[data-modal-close]"),
    modal: document.querySelector("[data-modal]"),
  };

  refs.openModalBtn.addEventListener("click", toggleModal);
  refs.closeModalBtn.addEventListener("click", toggleModal);

  function toggleModal() {
    refs.modal.classList.toggle("is-hidden");
  }
})();