# FindMyMovie | Умный поиск фильмов

Проект для усовершенствования системы пользовательского поиска фильмов на русском языке.

### Phase-2 | Team project

## 🦸‍♂️Команда
1. [Салман Чакаев](https://github.com/veidlink)
2. [Гриша Ржищев](https://github.com/Rzhischev)
3. [Дмитрий Ванякин](https://github.com/cobalt1705)
   
## 🎯 Задача
Разработка приложения с использованием Streamlit.
Сервис развернут на [HuggingFace Spaces](https://huggingface.co/spaces/veidlink/find_my_movie_hf).

## 🚂 Модель
Приложение работает на модели BERT - [rubert-tiny2](https://huggingface.co/cointegrated/rubert-tiny2).

## 📝 Схема работы
1. Мы спарсили 12,000 фильмов из каталога mail.ru. Информация о фильме, используемая для предложений - это описание со страницы фильма и ревью редакции.
2. Bert представляет описание+ревью на каждый фильм в виде вектора.
3. Пользователь вводит описание фильма, он прогоняется через BERT, получаем вектор.
4. С использованием [faiss](https://github.com/facebookresearch/faiss), на основе евкилдова расстояния между пользовательским описанием и фильмами из каталога mail.ru выводится выбранное количество предсказаний с наибольшим сходством.
