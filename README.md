# Agente Recursos: Sistema de Desarrollo de Software Multiagente

## Descripción general

Este repositorio contiene el código fuente de **Agente Recursos**, un sistema automatizado basado en agentes de inteligencia artificial (IA) diseñado para gestionar y ejecutar el ciclo de vida completo del desarrollo de software.

El proyecto orquesta un conjunto de agentes especializados que simulan los roles de un equipo de desarrollo tecnológico. Mediante modelos de lenguaje de gran escala (LLM), integrados a través de la API de Groq, el sistema es capaz de analizar requisitos, diseñar la arquitectura, escribir código, realizar pruebas y preparar el entorno de despliegue de forma autónoma.

## Arquitectura del sistema

El flujo de trabajo se divide en etapas secuenciales, cada una dirigida por un agente especializado:

1. **Product Owner** (`01_agente_product_owner.py`): interpreta las necesidades del usuario, define los requisitos funcionales y establece la visión del producto.
2. **Arquitecto de Software** (`02_agente_arquitecto.py`): diseña la estructura del sistema, selecciona las tecnologías adecuadas (por ejemplo, FastAPI) y define las interfaces de comunicación.
3. **Desarrollador** (`03_agente_developer.py`): implementa el código fuente de la aplicación conforme a las especificaciones del Arquitecto.
4. **Ingeniero de QA (Quality Assurance)**: desarrolla y ejecuta pruebas automatizadas para garantizar el correcto funcionamiento del código.
5. **Revisor de Código (Reviewer)**: analiza el código generado con el fin de detectar vulnerabilidades, verificar el cumplimiento de las buenas prácticas y proponer optimizaciones.
6. **Ingeniero DevOps**: configura los contenedores mediante Docker y Docker Compose, y establece los flujos de integración y despliegue continuos (CI/CD) a través de GitHub Actions.

## Tecnologías utilizadas

- **Lenguaje principal:** Python 3.x
- **Framework web (proyecto generado):** FastAPI
- **Inteligencia artificial:** API de Groq
- **Contenerización:** Docker y Docker Compose
- **CI/CD:** GitHub Actions
- **Gestión de entornos:** `venv` y `python-dotenv`

## Estructura del directorio

```
agente-recursos/
├── 01_agente_product_owner.py
├── 02_agente_arquitecto.py
├── 03_agente_developer.py
├── ...                         # Demás scripts de agentes
├── generated_project/          # Código fuente de la aplicación generada por los agentes
│   ├── main.py                 # API de FastAPI
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── .github/workflows/      # Flujos de CI/CD
├── venv/                       # Entorno virtual de Python
├── requirements.txt            # Dependencias del proyecto
└── README.md
```

## Requisitos previos

Para ejecutar este proyecto en un entorno local, se requiere lo siguiente:

- Python 3.8 o superior.
- Docker y Docker Compose instalados en el sistema.
- Una clave de API válida proporcionada por Groq.

## Instalación y configuración

1. **Clonar el repositorio:**

   ```bash
   git clone https://github.com/usuario/agente-recursos.git
   cd agente-recursos
   ```

2. **Crear y activar el entorno virtual:**

   ```bash
   python -m venv venv

   # En Windows:
   venv\Scripts\activate

   # En macOS/Linux:
   source venv/bin/activate
   ```

3. **Instalar las dependencias:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configurar las variables de entorno:**
   Cree un archivo denominado `.env` en el directorio raíz del proyecto y agregue sus credenciales:

   ```
   GROQ_API_KEY=su_clave_api_aqui
   ```

## Uso

Para iniciar el ciclo de desarrollo automatizado, ejecute los scripts de los agentes de manera secuencial o, de estar disponible, utilice el script orquestador principal:

```bash
python 01_agente_product_owner.py
python 02_agente_arquitecto.py
python 03_agente_developer.py
# Continúe con los agentes restantes
```

Los artefactos resultantes, incluidos el código de la API y las configuraciones de despliegue, se generarán dentro del directorio `generated_project/`.
