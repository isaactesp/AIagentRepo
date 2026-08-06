# AIagentRepo - Chatbot con RAG para Pizzería

Este proyecto es un asistente inteligente diseñado para responder preguntas específicas sobre una pizzería basándose en reseñas reales de clientes. Utiliza una arquitectura de **Generación Aumentada por Recuperación (RAG)**, lo que permite al chatbot consultar una base de datos de conocimientos local antes de generar una respuesta, garantizando que la información sea precisa y esté contextualizada.

### ¿Cómo funciona?
1.  **Ingesta de Datos**: El sistema lee un archivo CSV (`restaurant_reviews.csv`) que debemos incluir en el repositorio con opiniones de los clientes de la pizzeria.
2.  **Base de Datos Vectorial**: Las reseñas se procesan y almacenan en una base de datos vectorial (**ChromaDB**) utilizando el modelo de embeddings `mxbai-embed-large`.
3.  **Recuperación (Retrieval)**: Cuando el usuario hace una pregunta, el sistema busca las reseñas más relevantes.
4.  **Generación**: Finalmente, el modelo de lenguaje **Llama 3.2** (ejecutado localmente a través de **Ollama**) genera una respuesta coherente utilizando los fragmentos de reseñas encontrados como contexto.

## Requisitos Previos

1.  **Instalar Ollama**:
    ```bash
    curl -fsSL https://ollama.com/install.sh | sh
    ```
2.  **Instalar dependencias del sistema** (necesario para la extracción de Ollama):
    ```bash
    sudo apt-get update && sudo apt-get install -y zstd
    ```

## Configuración del Proyecto

### 1. Preparar los Modelos
Asegúrate de tener los modelos necesarios descargados en Ollama:
```bash
ollama pull llama3.2
ollama pull mxbai-embed-large
```

### 2. Instalación de Dependencias de Python
Si tienes `uv` instalado (recomendado):
```bash
uv sync
```
O si prefieres usar `pip`:
```bash
pip install -r requirements.txt
```

## Ejecución

Para iniciar el chatbot, ejecuta:

Con **uv**:
```bash
uv run main.py
```

Con **python**(desde sistema Ubuntu):
```bash
source .venv/bin/activate
```

E iniciamos el chatbot:
```bash
python main.py
```

## Comandos Útiles

- **Detener el servicio de Ollama**: `sudo systemctl stop ollama`
- **Reiniciar el servicio de Ollama**: `sudo systemctl restart ollama`
- **Salir del chatbot**: Escribe `q` o presiona `Ctrl + C`
