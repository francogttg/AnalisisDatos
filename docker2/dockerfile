# imagen base
FROM python:3.9-slim

# establecer mi directorio de trabajo
WORKDIR /app

# copiar el archivo de dependencias / lbirerias
COPY requirements.txt ./

# instalar las librerias
RUN pip install --no-cache -r requirements.txt

# copiamos todos los archivos
COPY . .

EXPOSE 5000

# COMANDO por defecto que ejecutara el contendor
CMD ["python", "app.py"]