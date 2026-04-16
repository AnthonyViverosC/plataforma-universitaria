# Plataforma Universitaria

Aplicacion web para la gestion de cursos, tareas, entregas, calificaciones y usuarios en un entorno academico. Este proyecto funciona como frontend de una plataforma universitaria conectada a servicios en AWS y fue construido con React + Vite.

## Descripcion

La aplicacion permite administrar el flujo basico de una plataforma educativa:

- Crear y editar cursos.
- Registrar tareas por curso.
- Subir entregas de estudiantes.
- Revisar entregas y registrar calificaciones.
- Gestionar usuarios con roles de estudiante y docente.

Su objetivo principal es servir como demo funcional y como base para evolucionar hacia una solucion mas profesional.

## Demo

- Frontend desplegado: `http://plataforma-uni.s3-website-us-east-1.amazonaws.com/`

## Tecnologias utilizadas

- React 18
- Vite 5
- JavaScript
- CSS
- AWS S3
- AWS API Gateway

## Caracteristicas principales

- Interfaz moderna y responsive.
- Navegacion modular por secciones.
- Capa de servicios para centralizar llamadas HTTP.
- Componentes reutilizables para metricas, mensajes y estados vacios.
- Configuracion por variables de entorno.
- Preparado para integrarse con un backend mas robusto.

## Estructura del proyecto

```text
plataforma-universitaria/
├── public/
├── src/
│   ├── components/   # Componentes reutilizables de UI
│   ├── pages/        # Pantallas y modulos de la aplicacion
│   ├── services/     # Cliente HTTP y funciones de integracion API
│   ├── utils/        # Helpers y formateadores
│   ├── App.jsx       # Layout principal
│   ├── config.js     # Configuracion general
│   ├── index.css     # Estilos globales
│   └── main.jsx      # Punto de entrada
├── .env.example
├── index.html
├── package.json
└── README.md
```

## Requisitos previos

Antes de ejecutar el proyecto, asegúrate de tener instalado:

- Node.js 18 o superior
- npm 9 o superior

## Instalacion

1. Clona el repositorio:

```bash
git clone <URL_DEL_REPOSITORIO>
cd plataforma-universitaria
```

2. Instala las dependencias:

```bash
npm install
```

3. Crea tu archivo de entorno:

```bash
cp .env.example .env
```

4. Configura la variable `VITE_API` con tu endpoint real:

```env
VITE_API=https://tu-api.execute-api.us-east-1.amazonaws.com
```

## Scripts disponibles

- `npm run dev`: inicia el servidor de desarrollo.
- `npm run build`: genera el build de produccion.
- `npm run preview`: sirve localmente el build generado.
- `npm run lint`: ejecuta ESLint sobre el proyecto.

## Ejecucion en desarrollo

```bash
npm run dev
```

Luego abre en el navegador la URL que te muestre Vite, normalmente:

```text
http://localhost:5173
```

## Build de produccion

```bash
npm run build
```

Los archivos optimizados quedaran en la carpeta `dist/`.

## Integracion con backend

El backend no esta incluido en este repositorio. El frontend espera una API compatible con endpoints como:

- `/cursos`
- `/tareas`
- `/usuarios`
- `/entregas`
- `/calificaciones`
- `/subir-tarea`

Para una integracion estable, se recomienda que el backend:

- Mantenga nombres de propiedades consistentes en todas las respuestas.
- Devuelva errores y respuestas de exito con un formato uniforme.
- Maneje autenticacion y autorizacion por rol.
- Genere URLs firmadas para archivos privados en S3 cuando sea necesario.

## Despliegue

Este proyecto puede desplegarse facilmente como sitio estatico en:

- AWS S3
- CloudFront
- Vercel
- Netlify

Si usas AWS S3, asegúrate de:

- Subir el contenido de `dist/`.
- Configurar correctamente el hosting estatico.
- Verificar permisos de lectura para el frontend.
- Revisar CORS en la API y permisos de acceso a archivos en S3.

## Estado actual

Actualmente el proyecto incluye:

- Refactor de UI para una experiencia mas profesional.
- Componentes reutilizables para mejor mantenimiento.
- Capa de servicios para ordenar el consumo de API.
- README y configuracion listos para publicar en Git/GitHub.

## Mejoras futuras

- Autenticacion de usuarios.
- Dashboard con metricas reales.
- Filtros avanzados y busqueda global.
- Validaciones mas fuertes de formularios.
- Backend documentado con OpenAPI.
- Manejo de archivos mediante URLs firmadas.

## Autor

Proyecto desarrollado como demo academica de plataforma universitaria.

## Licencia

Este proyecto puede adaptarse a la licencia que prefieras para tu repositorio. Si aun no has definido una, puedes agregar una licencia MIT.
