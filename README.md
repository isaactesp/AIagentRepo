# AIagentRepo

Este es un chatbot experto en responder preguntas sobre una pizzería utilizando RAG (Retrieval-Augmented Generation) con LangChain y Ollama.

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

Con **python**:
```bash
python main.py
```

## Comandos Útiles

- **Detener el servicio de Ollama**: `sudo systemctl stop ollama`
- **Reiniciar el servicio de Ollama**: `sudo systemctl restart ollama`
- **Salir del chatbot**: Escribe `q` o presiona `Ctrl + C`
