# 1.
docker pull httpd   -  para descargar la imagen  
docker images    -    para comprobar que se ha descargado  
# 2. + 3.
Creamos primero el archivo docker-compose.yml y le añadimos la siguiente información:  
services:    
asir_httpd:  
image: httpd:2.4  
ports:  
-"80:80"  
volumes:  
-/home/fabi/SRI/Tarea_volumenes/APACHE/paginas  
container_name: asir_httpd  

Despues, creamos el contenedor con el siguiente comando, incluyendo el número de puerto que queremos mapear:  
docker run -dit --name my-apache-app -p 8000:80 -v /home/fabi/SRI/Tarea_volumenes/APACHE/paginas:/usr/local/apache2/htdocs/ httpd:2.4
# 4.
Utilizamos para esto el siguiente comando:  
docker run -dit --name my-apache-app -p 8000:80 -v -v"$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd:2.4  
# 5.
Creamos un archivo index.html en el mismo directorio que el docker-compose.yml  
Le añadimos:  
< html >  
< h1 >Hola mundo < /h1 >  
</ html >   
En la barra del navegador escribimos: "localhost:8000" y aparecerá nuestro texto.  
# 6.

Realizamos los mismos pasos que antes pero con los nuevos datos:    
services:    
asir_web1:  
image: httpd:2.4  
ports:  
-"8000:80"  
volumes:  
-/home/fabi/SRI/Tarea_volumenes/APACHE/paginas  
container_name: asir_web1  

docker run -dit --name my-apache-app -p 8000:80 -v /home/fabi/SRI/Tarea_volumenes/APACHE/paginas:/usr/local/apache2/htdocs/ httpd:2.4
# 7. 
Como anteriormente, 
Creamos index.html añadiendo: 
< html >  
< h1 >Hola mundo < /h1 >  
</ html >   
En la barra del navegador escribimos: "localhost:8000" y aparecerá nuestro texto.  
# 8.
Realizamos los mismos pasos que antes pero con los nuevos datos:    
services:    
asir_web2:  
image: httpd:2.4  
ports:  
-"9080:80"  
volumes:  
-/home/fabi/SRI/Tarea_volumenes/APACHE/paginas  
container_name: asir_web2  

docker run -dit --name my-apache-app -p 9080:80 -v /home/fabi/SRI/Tarea_volumenes/APACHE/paginas:/usr/local/apache2/htdocs/ httpd:2.4 
# 9.
Consultando: 
"localhost:8000"  
"localhost:9080"  
Vemos que los dos sirven la misma página
# 10.
Sale la misma página.