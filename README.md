# CampusLands Management System

## Introducción

CampusLands es un sistema de gestión integral diseñado para administrar un bootcamp de programación. Este proyecto permite gestionar campers (estudiantes), trainers (instructores), coordinadores, grupos, rutas de formación y reportes de rendimiento. El sistema está desarrollado en Python y utiliza un archivo JSON como base de datos para almacenar toda la información.

El objetivo principal es facilitar la administración diaria del bootcamp, desde el registro de nuevos estudiantes hasta la graduación, pasando por la asignación de grupos, calificación de módulos y generación de reportes.

## Instalación

### Requisitos Previos

- Python 3.6 o superior instalado en el sistema.

### Pasos de Instalación

1. Clona o descarga el repositorio del proyecto en tu máquina local.
2. Navega al directorio raíz del proyecto: `proyecto-python`.
3. No se requieren dependencias externas adicionales, ya que el proyecto utiliza únicamente módulos estándar de Python (como `json`).

### Ejecución

Para ejecutar el sistema, abre una terminal en el directorio raíz del proyecto y ejecuta:

```bash
python main.py
```

## Uso

El sistema es completamente basado en consola y utiliza menús interactivos. Al ejecutar `main.py`, se presenta un menú principal con las siguientes opciones:

1. **Campers**: Permite a los estudiantes registrarse, iniciar sesión, ver su información y retirarse del programa.
2. **Trainers**: Los instructores pueden calificar a los estudiantes, ver su información personal y consultar la lista de estudiantes en sus grupos.
3. **Coordinación**: Área administrativa para gestionar campers, trainers, grupos, rutas y generar reportes.

### Funcionalidades Principales

- **Gestión de Campers**:
  - Registro de nuevos candidatos.
  - Cambio de estados (En proceso → Inscrito → Aprobado → Cursando → Graduado).
  - Asignación a grupos.
  - Expulsión o retiro voluntario.

- **Gestión de Trainers**:
  - Registro de nuevos instructores.
  - Calificación de módulos para campers (con pesos: 30% teoría, 60% práctica, 10% trabajos/quizes).
  - Consulta de estudiantes asignados.

- **Coordinación**:
  - Administración de grupos (crear, editar, asignar trainers y rutas).
  - Gestión de rutas de formación (NodeJS, Java, NetCore).
  - Reportes de campers en riesgo de bajo rendimiento.
  - Visualización de información por rutas y grupos.

### Estados de los Campers

Los campers pueden tener los siguientes estados:
- **En proceso**: Candidato registrado, esperando examen.
- **Inscrito**: Tomó el examen de admisión.
- **Aprobado**: Pasó el examen (promedio ≥ 60).
- **Cursando**: Activamente en el programa.
- **Graduado**: Completó todos los módulos.
- **Expulsado**: Removido del programa.
- **Retirado**: Abandono voluntario.
- **Denegado**: No pasó el examen.

## Estructura del Proyecto

```
proyecto-python/
│
├── main.py                    # Archivo principal que inicia el sistema y maneja el menú principal
├── importaciones.py           # Archivo que importa todos los módulos necesarios
│
├── data/
│   ├── __init__.py
│   └── baseDatos.json         # Base de datos JSON que almacena toda la información del sistema
│
├── design/
│   └── design.py              # Contiene las definiciones de menús y elementos visuales de la consola
│
├── functions/
│   └── funciones.py           # Funciones utilitarias (validación de entrada, pausa, etc.)
│
├── module/
│   ├── campers.py             # Funciones relacionadas con la gestión de campers
│   ├── coordinacion.py        # Funciones de coordinación y administración
│   ├── datosJson.py           # Funciones para leer/escribir en el archivo JSON
│   └── trainers.py            # Funciones relacionadas con la gestión de trainers
│
├── 1.jpg                      # Archivos de imagen (posiblemente recursos no utilizados)
├── 2.jpg                      # Archivos de imagen (posiblemente recursos no utilizados)
│
└── README.md                  # Este archivo
```

### Descripción de Archivos y Carpetas

- **main.py**: Punto de entrada del programa. Contiene el bucle principal del menú y la lógica para seleccionar entre campers, trainers y coordinación.

- **importaciones.py**: Centraliza todas las importaciones de módulos para mantener el código organizado.

- **data/baseDatos.json**: Archivo JSON que actúa como base de datos. Contiene arrays y objetos para campers, trainers, grupos, rutas, salones, jornadas, etc.

- **design/design.py**: Define los menús y textos que se muestran en la consola para una mejor experiencia de usuario.

- **functions/funciones.py**: Contiene funciones auxiliares como validación de entrada numérica, pausas en la ejecución y otras utilidades.

- **module/campers.py**: Maneja todas las operaciones relacionadas con los campers: registro, login, visualización de datos, retiro.

- **module/coordinacion.py**: El módulo más complejo, maneja la administración del sistema: gestión de campers, trainers, grupos, rutas y reportes.

- **module/datosJson.py**: Proporciona funciones para cargar y guardar datos en el archivo JSON.

- **module/trainers.py**: Gestiona las funcionalidades de los trainers: calificación, consulta de información personal y estudiantes.

## Dependencias

El proyecto utiliza únicamente módulos estándar de Python, por lo que no requiere instalación de dependencias externas:

- `json`: Para el manejo de archivos JSON.
- `os` (implícito): Para operaciones del sistema de archivos.

