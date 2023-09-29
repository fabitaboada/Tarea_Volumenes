# 1.
docker pull httpd   -  para descargar la imagen  
docker images    -    para comprobar que se ha descargado  
# 2. + 3.
Creamos primero el archivo docker-compose.yml y le añadimos la siguiente información:  
services:    
asir_httpd:  
image: httpd:2.4  
ports:  
-"8080"  
volumes:  
-/home/fabi/SRI/Tarea_volumenes/APACHE/paginas  
container_name: asir_httpd  

Despues, creamos el contenedor con el siguiente comando, incluyendo el número de puerto que queremos mapear:  
docker run -dit --name my-apache-app -p 8000:80 -v /home/fabi/SRI/Tarea_volumenes/APACHE/paginas:/usr/local/apache2/htdocs/ httpd:2.4
# 3.
Para mapear el puerto lo hacemos con el siguiente comando:  
docker run -dit --name my-apache-app -p 8000:80 httpd:2.4  