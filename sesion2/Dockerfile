#Referenciar una imagen base de python
FROM ubuntu:20.04

#Evita que el sistema operativo retire instalaciones manuales
ENV DEBIAN_FRONTEND=noninteractive

#Se actualiza el sistema y se instala los paquetes
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    python3-dev \
    build-essential \
    wget && \
    apt-get clean

# Se crea el directorio
RUN pip3 install --upgrade pip && \
    pip3 install notebook==6.5.6

#Setear o definir mi directorio de trabajo
WORKDIR /workspace

# Se crea el directorio
RUN mkdir -p /root/.jupyter

# Configuraciones basicas para el Jupter Notebook:
    
RUN echo "c.NotebookApp.token = ''" >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.password = ''" >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.open_browser = False " >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.allow_root = True " >> /root/.jupyter/jupyter_notebook_config.py


# expone en el puerto (por defecto de jupyter)
EXPOSE 8888

# Comando por defecto para iniciar el contenedor
CMD ["jupyter","notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]



