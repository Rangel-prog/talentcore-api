Agente Recursos - Sistema de Desarrollo de Software Multi-Agente

Descripción General

Este repositorio contiene el código fuente de Agente Recursos, un sistema automatizado basado en agentes de inteligencia artificial (IA) diseñado para gestionar y ejecutar el ciclo de vida completo del desarrollo de software.

El proyecto orquesta una serie de agentes especializados que simulan los roles de un equipo de desarrollo tecnológico. Utilizando modelos de lenguaje de gran escala (LLMs) a través de la integración con Groq, el sistema es capaz de analizar requisitos, diseñar la arquitectura, escribir código, realizar pruebas y preparar el entorno de despliegue de manera autónoma.

Arquitectura del Sistema

El flujo de trabajo se divide en etapas secuenciales, cada una liderada por un agente especializado:

Product Owner (01_agente_product_owner.py): Encargado de interpretar las necesidades del usuario, definir los requerimientos funcionales y establecer la visión del producto.

Arquitecto de Software (02_agente_arquitecto.py): Responsable de diseñar la estructura del sistema, seleccionar las tecnologías adecuadas (ej. FastAPI) y definir las interfaces de comunicación.

Desarrollador (03_agente_developer.py): Implementa el código fuente de la aplicación basándose en las especificaciones del Arquitecto.

Ingeniero de QA (Quality Assurance): Desarrolla y ejecuta pruebas automatizadas para garantizar el correcto funcionamiento del código.

Revisor de Código (Reviewer): Analiza el código generado en busca de vulnerabilidades, asegura el cumplimiento de buenas prácticas y propone optimizaciones.

Ingeniero DevOps (DevOps): Configura los contenedores mediante Docker y Docker Compose, y establece los flujos de integración y despliegue continuos (CI/CD) a través de GitHub Actions.

Tecnologías Utilizadas

Lenguaje Principal: Python 3.x

Framework Web (Proyecto Generado): FastAPI

Inteligencia Artificial: Groq API

Contenerización: Docker y Docker Compose

CI/CD: GitHub Actions

Gestión de Entornos: venv, python-dotenv

Estructura del Directorio

agente-recursos/
├── 01_agente_product_owner.py
├── 02_agente_arquitecto.py
├── 03_agente_developer.py
├── ... (Otros scripts de agentes)
├── generated_project/          # Código fuente de la aplicación generada por los agentes
│   ├── main.py                 # API de FastAPI
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── .github/workflows/      # Pipelines de CI/CD
├── venv/                       # Entorno virtual de Python
├── requirements.txt            # Dependencias del proyecto
└── README.md


Requisitos Previos

Para ejecutar este proyecto en un entorno local, se requiere:

Python 3.8 o superior.

Docker y Docker Compose instalados en el sistema.

Una clave de API válida proporcionada por Groq.

Instalación y Configuración

Clonar el repositorio:

git clone https://github.com/usuario/agente-recursos.git
cd agente-recursos


Crear y activar el entorno virtual:

python -m venv venv
# En Windows:
venv\Scripts\activate
# En macOS/Linux:
source venv/bin/activate


Instalar las dependencias:

pip install -r requirements.txt


Configuración de Variables de Entorno:
Cree un archivo nombrado .env en el directorio raíz del proyecto y agregue sus credenciales:

GROQ_API_KEY=su_clave_api_aqui


Uso

Para iniciar el ciclo de desarrollo automatizado, ejecute los scripts de los agentes de manera secuencial o utilice el script orquestador principal (si aplica):

python 01_agente_product_owner.py
python 02_agente_arquitecto.py
python 03_agente_developer.py
# Continúe con los agentes restantes...


Los artefactos resultantes, incluyendo el código de la API y las configuraciones de despliegue, se generarán dentro del directorio generated_project/.
