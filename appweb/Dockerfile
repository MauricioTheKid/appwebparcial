#Usa una imagen base de maven con OpenJDK 11
FROM maven:3.8.4-openjdk-11-slim


#Instala git
RUN apt-get update && apt-get install -y git

#Crea un directorio de trabajo dentro del contenedor
WORKDIR /app

#Clona el repositorio desde GitHub
RUN git clone https://github.com/lichito/HelloWorld.git

#Cambia al directorio del repositorio clonado
WORKDIR /app/HelloWorld

#Cambia a rama principal donde estan los fuentes del proyecto
RUN git checkout master

#Descarga los ultimos cambios del repositorio en la rama indicada
RUN git pull origin master

#Ejecuta el proceso de construccion con Maven
RUN mvn clean package

#Cambia al directorio donde se encuentra el archivo JAR
WORKDIR /app/HelloWorld/target

 #Establece el comando de ejecucion para iniciar la aplicacion
CMD ["java", "-jar", "helloworldjavaWeb-1.0.jar"]                     
