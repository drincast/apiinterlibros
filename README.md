# API REST APIInterLibros (DEMO)

Documentación de la API REST Para la aplicación intercambio de libros (InterLibro), aplicación demo para pruebas de semillero de Almundo.
* **espress:** Escritura de manejadores de peticiones con diferentes verbos HTTP en diferentes caminos URL (rutas).
* **body-parser:** Analizar el body de las solicitudes entrantes a la api
* **jwt-simple:** para el manejo de autenticación basada por token
* **momento:** para el el tiempo que perdurara el token de autorización
* **mongoose** para la conexión a la base de datos mongo en mlab, y el manejo de esquemas.

---

## **Inicio**
Descripción de los pasos para ejecutar la api
Instalar el entorno NodeJS

---

### **Instalación**
Clonar el repositorio 
* **HTTPS** `https://github.com/drincast/apiinterlibros.git`

Después de clonar el proyecto, entrar a la carpeta raíz y ejecutar el comando `npm install`.

---

### **Ejecutando la api en entorno local**
Para levantar la API ejecutar el siguiente comando `npm start`

---

La api se conecta a una base de datos alojada en https://mlab.com/, la configuración de la conexión se encuentra en el archivo index.js dentro de la carpeta raíz del proyecto
const basedatos = process.env.MONGO_URL || "mongodb://interlibros:interlibros123@ds041678.mlab.com:41678/interlibros";
# Recursos
La API se ejecutara el http://(IP local):1234/api

**Crear Usuario**
----
  Retorna el token, id de usuario, y nombre de usuario

* **URL**

  /login
  
* **Method:**

  `POST`
  
*  **URL Params (requerido)**

    None

* **Boby Params**

  `usuario=[string]`
  `password=[string]`

* **Respuesta:**

  * **Code:** 200
    **Content:** 
    ```
    {
        token:	"ASDJKL543890RWLKNJFSD9789080SJLKFSD9890"
        idUsuario:	"rewio5479043jjfljfl"
        usuario:	"usuario01"
    }


