# FBI System Authentication

El sistema de autenticación del FBI es una aplicación web segura que permite a los agentes autenticados acceder a un dashboard restringido. Utiliza tokens JWT para manejar la sesión y asegurar que solo los usuarios con credenciales válidas puedan acceder a las áreas protegidas de la aplicación.


## Tecnologías Utilizadas

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![Bootstrap](https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB) ![DOTENV](https://img.shields.io/badge/dotenv-0000?style=for-the-badge&logo=dotenv&logoColor=fff&color=b0a321) 
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)

## Funcionalidades

| Ruta            | Método | Descripción                               | Token Requerido |
|-----------------|--------|-------------------------------------------|-----------------|
| `/`             | GET    | Página de inicio con formulario de login. | No              |
| `/authenticate` | POST   | Autentica a los agentes y genera un token.| No              |
| `/restricted`   | GET    | Muestra el dashboard si el token es válido.| Sí             |
| `*`             | GET    | Muestra la página 404 para rutas no definidas.| No          |


# Instrucciones de Uso

Para acceder a la aplicación, debes utilizar las credenciales de los usuarios que están predefinidos en el sistema. Estos usuarios están almacenados en el archivo `agentModel.js` del proyecto, donde cada usuario tiene un conjunto de credenciales como nombre, email y contraseña.


## Consideraciones del Token

El token JWT tiene una duración de 2 minutos. Si el token se borra o expira, el usuario será redirigido a una página de error que indica que la sesión no es válida. Es importante iniciar sesión nuevamente para obtener un nuevo token y acceder al dashboard.

## Error Handling

Si se accede a una ruta inexistente o si el usuario intenta acceder al dashboard sin un token válido, se mostrará una página de error personalizada `404.html`.

### Instalación

Para iniciar la aplicación, siga estos pasos:

1. Clona este repositorio en tu máquina local:

```git clone https://github.com/gperzal/Desafio-FBI-System.git```

2. Navega al directorio del proyecto:

```cd Desafio-FBI-System.git```

3. Instala las dependencias necesarias:

```npm i```

4. Crear y configurar tu archivo:

 ```.env```

5. Inicia el servidor:

```npm start```