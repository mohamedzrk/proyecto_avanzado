Archivo log con una descripción de los pasos seguidos (para una explicación mas detallada, conscisa y con capturas de pantalla leer la memoria)
1º Paso: Preparación
- Creamos el directorio de trabajo:
cd Escritorio
mkdir proyecto_avanzado
- Inicializamos el repositorio local haciendo uso de git init:
cd proyecto_avanzado
git init
- Creamos un archivo al cual llamaremos README.md y contendrá el texto especificado en la captura de pantalla de la memoria:
nano README.md
-Añadimos el archivo README.md al repositorio:
git add README.md
-Realizamos un commit inicial con el mensaje: "Inicio del proyecto con README":
git commit -m "Inicio del proyecto con README"

2º Paso: Conexión con un Repositorio Remoto 
- Creamos un repositorio en GitHub con el mismo nombre (proyecto_avanzado) y sin ningún archivo inicial
- Conectamos el repositorio local con el repositorio remoto utilizando HTTPS:
git remote add origin https://github.com/mohamedzrk/proyecto_avanzado.git
- Creamos la rama main:
git branch -M main
- Subimos los cambios locales al repositorio remoto en la rama main:
- git push -u origin main

3º Paso: Trabajo Colaborativo con Ramas
- Usamos git checkout -b para crear y movernos a una nueva rama llamada feature/avances:
git checkout -b feature/avances
- Añadimos un archivo denominado avance.txt:
nano avance.txt
- Añadimos el .txt y realizamos el primer commit:
git add avance.txt
git commit -m "Avance.txt act1"
- Editamos el archivo .txt, lo volvemos a añadir y realizamos el segundo commit:
git add avance.txt
git commit -m "Avance.txt act2"
- Subimos la rama feature/avances al repositorio remoto:
git push -u origin feature/avances

4ºPaso: Colaboración y Resolución de Conflictos 
-Nos movemos a la rama main:
git checkout main
- Creamos avance.txt,Añadimos avance.txt y realizamos un commit y subimos los cambios al repositorio:
nano avance.txt
git add avance.txt
git commit -m "Avance.txt de la rama main"
git push -u origin main
- Cambiamos a la rama feature/avances y tratamos de fusionarla con main.
git checkout feature/avances
git merge main

Vemos como la fusión automática falla por lo que deberemos resolver el conflicto de forma manual.

Lo que hacemos es editar el archivo avance.txt y volverlo a añadirlo, de esta forma resolvemos el conflicto:
En la edición quitamos las líneas de texto que se han añadido automáticamente, estas separaban el texto de las ramas de esta manera:

<<<<<<< HEAD
(texto de avance.txt de la rama main)

=======
(texto de avance.txt de la rama feature/avances)
>>>>>>> feature/avances

Y finalmente el texto combinado se ha guardado en el archivo avance.txt 
- Subimos y comprobamos las actualizaciones en github
git push

5º Paso: Tags y Versionado
- Creamos un tag llamado v1.0 en la rama main para marcar el estado actual del proyecto, y luego subimos dicha actualización al repositorio remoto:
git tag v1.0
git push origin v1.0

6º Paso: Clonación y Validación
- Primero creamos un nuevo directorio, para luego llevar a cabo la clonación dentro de este.
- Luego dentro del nuevo repositorio ejecutamos el siguiente comando:
git clone https://github.com/mohamedzrk/proyecto_avanzado.git
-Finalmente podemos comprobar que el estado del repositorio clonado coincide con el del repositorio remoto.



