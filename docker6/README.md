Primero descargamos la imagen de jupiter

sudo docker pull jupyter/datascience-notebook:ubuntu-20.04

cremaos un contendor con la imagen

sudo docker run -p 10000:8888 jupyter/scipy-notebook:85f615d5cafa

Una vez iniciado ya podriamos usarlo desde el navegador

http://localhost:10000/

Para loguearnos tenemos que insertar el token

![tok](https://user-images.githubusercontent.com/101642915/203522983-99fef024-80ef-4f76-8f07-23481c00e9e4.png)


Este token aparece cuando iniciar el contenedor
![log](https://user-images.githubusercontent.com/101642915/203523184-aca8c413-25a0-4732-9b13-e2ee55f0d575.png)


Este es el interfaz nada mas entrar
![in](https://user-images.githubusercontent.com/101642915/203523401-83866aec-8627-47a0-8c59-1672ce046eb1.png)

Podemos elegir pyton y ponernos a programar
![image](https://user-images.githubusercontent.com/101642915/203523587-93d7dec5-733d-426b-bf7e-f7f50d7661b4.png)


Jupiter Notebook es una aplicacion muy parecida a google collab, desde la cual vamos a poder programar en python.
