# CIE10Codes_MBDS_TFM
Proyecto de investigación para la extracción de códigos CIE-10 de notas clínicas utilizando Mistral 7B mediante diferentes técnicas. 

Este repositorio contiene el código y los recursos utilizados en el proyecto de investigación para evaluar el modelo Mistral 7B en la tarea de codificar notas clínicas (texto libre médico) según el estándar CIE-10. Se ha intentado refinar la performance del modelo mediante técnicas de Prompt Engineering y RAG (Retrieval-Augmented Generation).

## Estructura del Repositorio

El repositorio está organizado en las siguientes carpetas:

### data
Contiene las bases de datos empleadas en el proyecto:
- **DS_v1.csv**: Base de datos inicial con notas clínicas sintetizadas a través de ChatGPT (no validadas, en espera de la base de datos oficial).
- **ntt_synthetic_data_notes_150.csv**: 150 notas creadas por NTT para la validación del modelo.
- **ntt_synthetic_data_150.csv**: Entidades validadas y sus respectivos códigos CIE-10 validados, comparados con las entidades y códigos devueltos por el modelo.
- **codigos_cie_format.csv**: CSV con todos los códigos CIE-10 y sus respectivas descripciones oficiales.
- **raw/**: Carpeta que contiene un .txt por cada una de las 150 notas creadas por NTT y sus respuestas validadas (entidades y códigos CIE-10).

### notebooks
Contiene los notebooks de Jupyter utilizados en el proyecto, organizados en tres subdirectorios:

#### auxiliar
- **Formato_bd_cie10.ipynb**: Genera el archivo `codigos_cie_format.csv` a partir del formato txt original.
- **NTT_synthetic_data.ipynb**: Genera las bases de datos `ntt_synthetic_data_150.csv` y `ntt_synthetic_data_notes_150.csv`.

#### mistral
Organizado en dos versiones, cada una con sus respectivos notebooks:
- **Mistral_v1**: 
  - **Mistral_CIE10_v1.ipynb**: Evaluación del modelo Mistral en crudo.
  - **Mistral_Prompt_Engineering_v1.ipynb**: Evaluación con técnicas de Prompt Engineering.
  - **Mistral_RAG_v1.ipynb**: Evaluación con técnicas RAG usando BioBERT y ClinicalBERT.
- **Mistral_v2**: 
  - **Mistral_CIE10_v2.ipynb**: Evaluación del modelo Mistral en crudo.
  - **Mistral_Prompt_Engineering_v2.ipynb**: Evaluación con técnicas de Prompt Engineering.
  - **Mistral_CIE10_v2_RAG_BERT.ipynb**: Evaluación con RAG usando BERT.
  - **Mistral_CIE10_v2_RAG_BioBERT.ipynb**: Evaluación con RAG usando BioBERT.
  - **Mistral_CIE10_v2_RAG_ClinicalBERT.ipynb**: Evaluación con RAG usando ClinicalBERT.
  - `prompt_example.txt`: Ejemplo del prompt empleado en el notebook de Prompt Engineering.

#### evaluation
- **eval_v2_NTT_synthetic_data_150.ipynb**: Obtiene las métricas y evaluaciones de los resultados para la base de datos de NTT (150 notas validadas).
- **embedder_eval.ipynb**: Estudio de la actuación de RAG evaluando los chunks considerados relevantes por BioBERT y ClinicalBERT.

### output
Contiene los resultados obtenidos:
- **results_eval_v1**: Resultados CSV y JSON de la evaluación de la primera base de datos utilizando diferentes técnicas.
- **results_mistral_v2**: Resultados CSV y JSON de los códigos y entidades reconocidos por Mistral para la base de datos sintetizada por NTT (150 notas) utilizando diferentes técnicas.
- **results_mistral_v1**: Resultados CSV de los códigos y entidades reconocidos por Mistral para la primera base de datos utilizando diferentes técnicas.

## Uso

### Requisitos
- Python 3.8+
- Jupyter Notebook
- Mistral 7B

### Instalación
1. Clonar el repositorio:
    ```sh
    git clone https://github.com/paulasanjuancam/CIE10Codes_MBDS_TFM.git
    cd CIE10Codes_MBDS_TFM
    ```

2. Crear y activar un entorno virtual:
    ```sh
    python -m venv venv
    source venv/bin/activate  # En Windows usa `venv\Scripts\activate`
    ```

3. Instalar las dependencias:
    ```sh
    pip install -r requirements.txt
    ```

4. Configurar Mistral (si es necesario):
    - [Enlace a la documentación oficial de Mistral](https://docs.mistral.ai/)

### Ejecución

1. Navega a la carpeta `notebooks` y abre el notebook correspondiente según la tarea que desees realizar.
2. Sigue las instrucciones dentro del notebook para ejecutar el modelo y obtener las respuestas o evaluaciones necesarias.


---

Este proyecto ha sido desarrollado para evaluar y mejorar la precisión en la codificación de notas clínicas utilizando técnicas avanzadas de procesamiento de lenguaje natural. Agradecemos cualquier retroalimentación y contribución para mejorar aún más este trabajo.
