# Análisis de Afluencia y Sentimiento del Usuario para la Optimización del Metro CDMX

![Banner del Metro CDMX](httpst://i.imgur.com/example.png) ## 📜 Descripción del Proyecto

Este proyecto tiene como objetivo analizar dos fuentes de datos clave del Sistema de Transporte Colectivo (STC) Metro de la Ciudad de México: la **afluencia de pasajeros** y el **sentimiento de los usuarios** expresado en redes sociales.

Mediante la combinación de análisis de series temporales, análisis geoespacial y Procesamiento de Lenguaje Natural (NLP), buscamos identificar patrones, puntos críticos de congestión y correlacionar la afluencia con la opinión pública. El objetivo final es proponer recomendaciones basadas en datos para la optimización del servicio.

## 🎯 Objetivos

1.  **Analizar la Afluencia:** Identificar patrones horarios, diarios y estacionales de la afluencia de pasajeros por estación y línea.
2.  **Analizar el Sentimiento:** Extraer y clasificar el sentimiento (positivo, negativo, neutro) de los usuarios en redes sociales (como X/Twitter) sobre el servicio del Metro.
3.  **Modelar Temas (Topic Modeling):** Identificar las quejas y elogios más comunes (ej. "retrasos", "limpieza", "seguridad", "vagoneros").
4.  **Correlacionar Datos:** Cruzar los datos de afluencia con los picos de sentimiento negativo para localizar "puntos de dolor" operativos.
5.  **Generar Recomendaciones:** Proveer insights accionables para la optimización de la asignación de trenes, personal de mantenimiento y comunicación al usuario.

## 📊 Fuentes de Datos

* **Afluencia:** [Portal de Datos Abiertos de la CDMX](https://datos.cdmx.gob.mx/dataset/afluencia-diaria-del-sistema-de-transporte-colectivo-metro-por-linea) - Afluencia diaria (o por hora, si está disponible) por estación y línea.
* **Sentimiento:** API de X (Twitter) o scraping de tweets que mencionen `@MetroCDMX`, `#MetroCDMX`, y nombres de las líneas.
* **Datos Geoespaciales:** Coordenadas de las estaciones del Metro para visualización en mapas.

## 🛠️ Metodología y Stack Tecnológico

Este proyecto se desarrolla en `Python 3.10` y utiliza las siguientes bibliotecas:

* **Adquisición de Datos:** `Tweepy` (para la API de X), `Requests`/`BeautifulSoup` (para scraping si es necesario).
* **Análisis y Manipulación de Datos:** `Pandas`, `NumPy`, `GeoPandas`.
* **Visualización de Datos:** `Matplotlib`, `Seaborn`, `Plotly`, `Folium` (para mapas interactivos). 
* **Procesamiento de Lenguaje Natural (NLP):** `NLTK`, `spaCy`, `Scikit-learn` (para TF-IDF, CountVectorizer).
* **Análisis de Sentimiento:** `VADER Sentiment`, `TextBlob`, o un modelo pre-entrenado de `Hugging Face Transformers`.
* **Entorno de Trabajo:** `Jupyter Notebooks` / `Jupyter Lab`.

## 📂 Estructura del Repositorio

```
analisis-metro-cdmx/
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt      # Lista de dependencias del proyecto
├── data/
│   ├── raw/              # Datasets originales
│   └── processed/        # Datasets limpios
├── notebooks/
│   ├── 01_Adquisicion_y_Limpieza_Afluencia.ipynb
│   ├── 02_Adquisicion_y_Limpieza_Tweets.ipynb
│   ├── 03_EDA_Analisis_de_Afluencia.ipynb
│   ├── 04_NLP_Analisis_de_Sentimiento.ipynb
│   ├── 05_Correlacion_y_Resultados.ipynb
└── src/
    ├── data_utils.py     # Funciones de limpieza
    └── nlp_utils.py      # Funciones de procesamiento de texto
```

## 📈 Resultados Principales (En Proceso)

*Aquí se agregarán las visualizaciones y conclusiones clave a medida que el proyecto avance.*

* **Ejemplo:** Se observa un pico de sentimiento negativo en la Línea 7 que se correlaciona con la afluencia máxima de la mañana (8:00 - 9:00 am), sugiriendo una necesidad urgente de optimización en ese horario. 
* **Ejemplo:** El análisis de temas revela que el 35% de las quejas están relacionadas con "retrasos" y "aglomeraciones", mientras que un 15% se enfoca en "fallas de escaleras eléctricas".

## 🚀 Cómo Empezar

Para replicar este análisis, sigue estos pasos:

1.  Clona el repositorio:
    ```bash
    git clone [https://github.com/tu-usuario/analisis-metro-cdmx.git](https://github.com/tu-usuario/analisis-metro-cdmx.git)
    cd analisis-metro-cdmx
    ```

2.  Crea un entorno virtual e instala las dependencias:
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Windows: venv\Scripts\activate
    pip install -r requirements.txt
    ```

3.  Descarga los datasets de afluencia del [Portal de Datos Abiertos](https://datos.cdmx.gob.mx/dataset/afluencia-diaria-del-sistema-de-transporte-colectivo-metro-por-linea) y colócalos en la carpeta `data/raw/`.

4.  Configura tus credenciales de la API de X (Twitter) en un archivo `.env` (asegúrate de que `.env` esté en tu `.gitignore`).

5.  Ejecuta los notebooks en orden (de `01` a `05`) en la carpeta `notebooks/`.

## 👤 Autor

* **[Tu Nombre]**
* [Tu LinkedIn](https://www.linkedin.com/in/tu-usuario/)
* [Tu Portafolio](https://tu-sitio-web.com)
