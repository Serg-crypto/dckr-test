FROM python:3.7-alpine 

WORKDIR /code

#VARIABLES DE ENTORNO DE FLASK
ENV FLASK_APP=app.py 
ENV FLASK_RUN_HOST=0.0.0.0
#EJECUCION
RUN apk add --no-cache gcc musl-dev linux-headers

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Exponer un puerto
EXPOSE 5000

# Copiar el codigo dentro de la imagen
COPY . .
#Ejecución del código
CMD ["flask","run"]