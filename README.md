# Instrucciones y dependencias para el proyecto de GNU/Linux @ Conociverso

## Notas Importantes

Estas instrucciones asumen un sistema GNU/Linux basado en Debian (Ubuntu, PopOS, Linux Mint, etc), si usas un sistema distinto deberás ajustar el gestor de paquetes mencionado en este texto (apt) de acuerdo a tu instalación.

## Contenido

1. Dependencias del sistema operativo
2. Miniforge3
3. Instalación existente de Anaconda/Miniconda
4. Instalación de ambientes virtuales

## 1. Dependencias del sistema operativo

Nota para los usuarios de Ubuntu: Cada día es mas frecuente encontrar que hay paquetes que no están disponibles al tratarlos de instalarlos desde `apt`, si alguno de los siguientes programas te dá problemas para instalarlo de esta manera puedes intentar con `snap` 

Para instalar los programas te recomiendo que primero hagas una actualización de tu sistema: 

`sudo apt update && sudo apt upgrade`

A continuación instala los siguientes paquetes con:

`sudo apt install [nombre de (los) paquete(s)]`

Recuerda que los corchetes "[ ]" sólo indican que debes sustituir algo dentro de los mismos y no debes escribirlos en el comando final.

|Programa|Descripción|Notas|
|--------|-----------|-----|
|bat|Versión mejorada de `cat`| Disponible a partir de Debian 12 |
|btop|Versión mejorada de `top`|Disponible a partir de Debian 12 |
|htop|Versión mejorada de `top`|Muchas veces ya instalada|
|curl|Gestor de descargas de la linea de comando||
|dmidecode|Gestor de información de hardware||
|exa|Versión mejorada de `ls`|No disponible en versiones viejas de Debian/Ubuntu|
|fd-find|Buscador de archivos en la terminal||
|git|Programa de gestion de versiones||
|gzip|Descompresor de archivos||
|nala|Versión mejorada de `apt`||
|nano|Editor de texto|Muchas veces ya instalado|
|neofetch|Informa de parámetros generales del sistema||
|wget|Gestor de descargas|Muchas veces ya instalado|

Ninguno de los programas arriba mencionados son directamente necesarios para terminar el proyecto del curso, de manera que si alguno de ellos no lo logras instalar no interferirá con tu aprendizaje.

## 2. Miniforge3

Miniforge es una distribución de Anaconda, que a su vez es una forma de instalar Python, R y dependencias relacionadas en una forma menos destructiva que las instalaciones en el sistema operativo. 

**CONTINUA SÓLO SI NO TIENES UNA INSTALACIÓN DE ANACONDA O MINICONDA EN TU SISTEMA ACTUALMENTE, DE LO CONTRARIO PASA AL PUNTO 3 DE ESTE MANUAL**

Lo primero que debes hacer es instalar miniforge, el método de instalación mas rapido es con el siguiente comando (requiere `curl`, de la lista de software del primer punto de este manual):

`curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh`

**recuerda leer con detenimento TODO lo que se presenta en pantalla durante la instalación**

En caso de que se te pregunte si deseas hacer un "init" contesta que si.

Al terminar la instalación ejetuta cierra la terminal y abre una nueva

Si la instalación se concretó con éxito deberias ver en el prompt de tu terminal el texto **"(base)"**, de lo contrario ejecuta el siguiente comando:

`miniforge3/condabin/mamba init`

Cierra y abre la terminal, ya debarías ver **"(base)"** en tu prompt.

Te recomiendo que revises la documentación de miniforge en su [repositorio](https://github.com/conda-forge/miniforge) oficial

Pasa al punto 4 de este tutorial.

## 3. Instalación existente de Anaconda/Miniconda

En caso de que ya tengas una instalación existente tienes cuatro opciones

1. Si tu instalación no es tan importante o sabes como hacer un respaldo, te recomiendo que simplemente borres por completo la carpeta anaconda o miniconda de tu directorio home y pases al punto 2 de este tutorial.

2. Si no deseas eliminar tu instalación existente puedes intentar instalar `mamba` en tu ambiente base, este programa es una version mejora de `conda` que facilita la instalación y la resolucion de conflictos de dependencias, lee las advertencias y sigue las instrucciones de instalación del [repositorio oficial](https://mamba.readthedocs.io/en/latest/installation/mamba-installation.html) para una instalación existente de conda.

3. Alternativamente puedes intentar los pasos del punto 4 usando `conda` en lugar de `mamba`, dependiendo de lo saludable que sea tu instalación actual de Anaconda esto puede funcionar o no, si el comando se cuelga y no ocurre nada después de varios minutos de comenzado te recomiendo que tomes cualquiera de las otras opciones de esta lista.

4. Usa la máquina virtual ;)

## 4. Instalación de ambientes virtuales

A continuación deberás crear los ambientes virtuales que necesitaremos en el curso, para ello descarga los archivos con extensión **yml** y estando en la carpeta que los contiene ejecuta lo siguiente.

`mamba env create -f bowtie2-env.yml`

`mamba env create -f homer-env.yml`

`mamba env create -f intervene-env.yml`


