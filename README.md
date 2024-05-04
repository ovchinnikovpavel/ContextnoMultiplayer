# Сорвеновательный режим для игры констекстно.рф

_Автор оригинальной игры - https://github.com/yuloskov (Артем Юлосков)_

## Как играть в контекстно?

Цель игры - угадать секретное слово. Это слово занимает первое место в списке.

### Основные правила (из оригинальной игры)

У тебя есть неограниченное количество попыток.
Все слова в списке ранжированы по их схожести с секретным словом.
Чем выше слово в списке (чем меньше его номер), тем оно ближе к секретному слову

### Принцип работы

Это как игра горячо-холодно. Например, если секретное слово "кот", то "кошка" будет выше в списке (ближе к "коту") по сравнению с "собака".
Алгоритм анализировал множество текстов и использует контекст для определения сходства слов.
Введи случайное слово в поле ввода и нажми на кнопку со стрелочкой. Правила сразу станут понятны. Удачи!

---

_Проект использует API контекстно.рф, загадать можно любое слово что есть в словаре оригинальной игры!_

## Механики дополнения

### Комнаты

Комната - игра, каждое загаданное слово создаёт комнату к которой может подключится неограниченное количество игроков.

### Игроки

Каждый игрок имеет своё место, цвет и никнейм. Место вычисляется относительно очков других игроков в комнате, очки же в свою очередь устанавливаются за ранг ближайшего к загаданному слову

### Подсказки

Подсказок из оригинальной игры нету, вместо этого оператор (лидер лобби) может сам подсказывать игрокам слова связанные с загаданным, либо словами описать что загаданное слово из себя представляет.
Любой игрок в комнате может поделится имеющимся у себя словом с другим игроком, наведя на него курсор и нажав соответствующую кнопку на слове. Делится словами можно неограниченно.

### Оператор

Лидер лобби сразу становится оператором. Оператор может видеть, какие слова пишут игроки и в зависимости от правильности хода их мыслей направлять на загаданное слово. Оператором может стать игрок, который отгадал загаданное слово.

### Лучше всего играть в компании, с голосовым чатом

---

# Развертывание проекта локально

После клонирования репозитория установите все зависимости в директориях `client/` и `server/`

> `$ cd client && npm i` > `$ cd server && npm i`

В папке client создайте файл `.env.local` и укажите ключ `NEXT_PUBLIC_SOCKET_IO_SERVER`, это будет IP-адрес с портом **25535**
_Пример:_
`.env.local`
`NEXT_PUBLIC_SOCKET_IO_SERVER="http://localhost:25535"`

Запуск проекта осуществляется запуском веб приложения и сервера где происходит общение клиентов (игроков) между собой

> `$ cd server` >`$ npm start`

> `$ cd client` >`$ npx next dev`

### Готово! Проект запущен на порту 3000!
