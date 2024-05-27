# api_final_yatube

### Описание:

Данный проект реализует API для социальной сети Yatube. Не авторизованные пользователи могут только просматривать публикации и комментарии. Авторизованные пользователи могут создавать и редактировать свои публикации, писать комментарии к постам всех пользователей и редактировать их, а также подписываться на других пользователей. Для аутентификации используйте JWT-токены.

### В проекте использованы следующие технологиии:

Python 3.9, Django 3.2, Django REST framework 3.12, Simple JWT 4.7, Pillow 9.3, PyJWT 2.1

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```sh
git clone https://github.com/Ilya1202/api_final_yatube.git
```

```sh
cd api_final_yatube
```

Создать и активировать виртуальное окружение:

```sh
python3 -m venv env
```

```sh
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```sh
python3 -m pip install --upgrade pip
```

```sh
pip install -r requirements.txt
```

Выполнить миграции:

```sh
python3 manage.py migrate
```

Запустить проект:

```sh
python3 manage.py runserver
```

### Примеры:

Получить 5 публикаций начиная с 11:

```http
GET /api/v1/posts/?limit=5&offset=10
```

---
Создать публикацию с указанием группы:

```http
POST /api/v1/posts/
```
тело:
```json
{
    "text": "Текст публикации.",
    "group": {{group_id}}
}
```
---
Получить все комментарии определенной публикации:

```http
GET /api/v1/posts/{{post_id}}/comments/
```
---
Добавить комментарий к публикации:

```http
POST /api/v1/posts/{{post_id}}/comments/
```
тело:
```json
{
    "text": "Текст комментария."
}
```
---
Подписать на пользователя:

```http
POST /api/v1/follow/
```
тело:
```json
{
    "following": "{{username}}"
}
```

### Автор: Илья
