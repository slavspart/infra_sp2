FROM python:3.7-slim

RUN mkdir /app

COPY requirements.txt /app

RUN pip3 install -r /app/requirements.txt --no-cache-dir

COPY ./ /app

WORKDIR /app
# Артём, прости, не понял, что от меня требуется. Ты пишешь, что workdir хорошая инструкция. 
# Но ведь я же ее и использую.

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000"] 
