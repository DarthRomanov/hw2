# Docker-команда FROM вказує базовий образ контейнера
# Наш базовий образ - це Linux з попередньо встановленим python-3.10
FROM python:3.10

# Встановимо змінну середовища
ENV APP_HOME /app

# Встановимо робочу директорію всередині контейнера
WORKDIR $APP_HOME

COPY Pipfile $APP_HOME/Pipfile
COPY Pipfile.lock $APP_HOME/Pipfile.lock

# Встановимо залежності всередині контейнера
RUN pip install pipenv
RUN pipenv config virtualenvs.create false && pipenv install


# Скопіюємо інші файли в робочу директорію контейнера
COPY . .


# Позначимо порт, де працює застосунок всередині контейнера
EXPOSE 5000

# Запустимо наш застосунок всередині контейнера
ENTRYPOINT ["python", "main.py"]