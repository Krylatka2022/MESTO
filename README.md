# Проект: Место

### Обзор

Техническое задание было предоставлено в графическом редакторе Figma:
**Figma**

- [Ссылка на макет в Figma](https://www.figma.com/file/2cn9N9jSkmxD84oJik7xL7/JavaScript.-Sprint-4?node-id=0%3A1);

В работе также реализованы навыки адаптивой и резиновой верстки под разрешения экрана: 320px 1280px.

Учтены относительные и абсолютные показатели

Использовались такие инструменты как **Grid layot** и **Flex**.

Структура проекта выполнена согласно _Nested БЭМ_.

Тексты написаны бесплатным шрифтом _”Inter“_

- [Ссылка на проект](https://krylatka2022.github.io/mesto/)

### Особенности и отличия, спринт 4.

Добавлена функциональная часть **javascript**:

Реализовано одно диалоговое окно **popup** из макета — «Редактировать профиль».

В нём доступны для редактирования два поля: «Имя» и «О себе», а также кнопка «Сохранить» (специальное событие submit)

Рализовано переполнение содержимого в блоке profile и element.

Проект проверен на соответствие макету при помощи **PerfectPixel** для Chrome и **Pixel Perfect Pro** для Firefox

### Особенности и отличия, спринт 5

1. Реализовано добавление 6 карточек из массива с возможностью удаления и отметкой "нравится"

2. Клонирование элементов массива с помощью template

3. Реализована возможность увеличения картинок из массива

4. Реализована возможность добавления карточек по данным пользователя

Для реализации выполнения пунктов 3 и 4 было создано 2 дополнительных попапа

### Особенности и отличия, спринт 6.

1. Реализована валидация всех форм попапа с помощью функциональности **javascript**: пользователь, который неправильно ввел дданые в поля "редактировать профиль" или "добавление карточек" не сможет реализовать изменения. Если хотя бы одно из полей не прошло валидацию, кнопка «Сохранить» остается неактивной
   Использованы стандартные браузерные тексты ошибок.

2. Реализрвано закрытие попапа кликом на оверлей

3. Реализовано закрытие попапа нажатием на Esc

4. Улучшен UX при работе с попапами.

### Особенности и отличия, спринт 7.

#### Организация (рефакторинг) кода. Создание двух отдельных классов **Card** и **FormValidator**. ООП. Ванильный Js.

1. Kласс **Card** создаёт карточку с текстом и ссылкой на изображение:

- принимает в конструктор её данные и селектор её template-элемента;
- содержит приватные методы, которые работают с разметкой, устанавливают слушателей событий;
- содержит приватные методы для каждого обработчика;
- содержит один публичный метод, который возвращает полностью работоспособный и наполненный данными элемент карточки.

Для каждой карточки создан экземпляр класса **Card**.

2. Kласс **FormValidator** настраивает валидацию полей формы:

- принимает в конструктор объект настроек с селекторами и классами формы;
- принимает вторым параметром элемент той формы, которая валидируется;
- имеет приватные методы, которые обрабатывают форму: проверяют валидность поля, изменяют состояние кнопки сабмита, устанавливают все обработчики;
- имеет публичный метод enableValidation, который включает валидацию формы.

Для каждой проверяемой формы создан экземпляр класса **FormValidator**.

3. Разбивка JavaScript на модули. В проекте 3 js-файла:

- Card.js с кодом класса Card,
- FormValidator.js с кодом класса FormValidator,
- index.js со всем остальным кодом.

Классы Card и FormValidator экспортируются из соответствующих файлов, импортируются в index.js и используются в нём.

Отдельные js-файлы подключены в index.html как модули
