Primero descargamos la imagen de jupiter

sudo docker pull jupyter/datascience-notebook:ubuntu-20.04

cremaos un contendor con la imagen

sudo docker run -p 10000:8888 jupyter/scipy-notebook:85f615d5cafa

Una vez iniciado ya podriamos usarlo desde el navegador

http://localhost:10000/

Para loguearnos tenemos que insertar el token