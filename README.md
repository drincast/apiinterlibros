# API REST APIInterLibros (DEMO)

Documentación de la API REST Para la aplicación intercambio de libros (InterLibro), aplicación demo.

* **express:** Escritura de manejadores de peticiones con diferentes verbos HTTP en diferentes caminos URL (rutas).
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


**Obtener libros por título**
----
  Retorna un array de los libros disponibles, según el parámetro de entrada, búsqueda por titulo de libro

* **URL**

  /obtener-libros-titulo/:titulo

* **Method:**

  `GET`

*  **URL Params (requerido)**

    Titulo: string

* **Boby Params**

  `NONE

* **Respuesta:**

  * **Code:** 200
    **Content:**
    ```
    [
{ _id: 5a9137d71d6b6372201523bc,
    	idUsuario: '5a8b9aa38365314d7083af2a',
    titulo: '100 libros',
    autor: 'nn 1092',
    descripcion: 'el libro de misterios del mundo, El código JSX parece HTML pero realmente es una',
    urlImagen: 'https://letransfusion.files.wordpress.com/2009/06/libro_viejo.jpg',
    __v: 0 },
  { _id: 5a8e31bdbbf21e2d148cd65c,
    idUsuario: '5a8b9aa38365314d7083af2a',
    titulo: 'el libro',
    autor: 'el autor',
    descripcion: 'El código JSX parece HTML pero realmente es una mezcla de JavaScript y HTML. El',
    urlImagen: 'http://conceptodefinicion.de/wp-content/uploads/2015/01/libro.jpg',
    __v: 0 }
]


**Obtener libro **
----
  Retorna un datos de un libro

* **URL**

 /obtener-libro/:id

* **Method:**

  `GET`

*  **URL Params (requerido)**

    id: string

* **Boby Params**

  `NONE

* **Respuesta:**

  * **Code:** 200
    **Content:**
    ```
[ { _id: 5a8e31bdbbf21e2d148cd65c,
    idUsuario: '5a8b9aa38365314d7083af2a',
    titulo: 'el libro',
    autor: 'el autor',
    descripcion: 'El código JSX parece HTML pero realmente es una mezcla de JavaScript y HTML,
    urlImagen: 'http://conceptodefinicion.de/wp-content/uploads/2015/01/libro.jpg',
    __v: 0 } ]


**Mensajes por usuario **
----
  Retorna los mensajes de un usuario

* **URL**

 /mensajes-Usuario/:id  
* **Method:**

  `GET`

*  **URL Params (requerido)**

    id: string

* **Boby Params**

  `NONE

* **Respuesta:**

  * **Code:** 200
    **Content:**
    ```
[ { _id: 5a921a59c909811188c60ac5,
    idUsuario: '5a8b9aa38365314d7083af2a',
    idUsuarioEnvia: '5a8b9aa38365314d7083af2a',
    mensaje: 'El usuario usuario01 te envío un mensaje ... \n\nHola, me interesa tu libro, me gustaría hacer un intercambio, escribirme :) !!!!',
    tipo: 'Solicitud',
    __v: 0 },
  { _id: 5a921b1b3549bf432c99afbc,
    idUsuario: '5a8b9aa38365314d7083af2a',
    idUsuarioEnvia: '5a8b9aa38365314d7083af2a',
    mensaje: 'El usuario usuario01 te envío un mensaje ... \n\nHola, me interesa tu libro, me gustaría hacer un intercambio, escribirme :) !!!!',
    tipo: 'Solicitud',
    __v: 0 } ]

---
