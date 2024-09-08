# **CIE10Codes_MBDS_TFM**


## English Version

Research project for the extraction of ICD-10 codes from clinical notes using Mistral 7B through different techniques.

This repository contains the code and resources used in the research project to evaluate the Mistral 7B model in the task of coding clinical notes (medical free text) according to the ICD-10 standard. Efforts have been made to improve the model's performance through Prompt Engineering and RAG (Retrieval-Augmented Generation) techniques.

### Repository Structure
The repository is organized into the following folders:

#### data
Contains the databases used in the project:

- **DS_v1.csv**: Initial database with clinical notes synthesized through ChatGPT (not validated, awaiting the official database).
- **ntt_synthetic_data_notes_150.csv**: 150 notes created by NTT for model validation.
- **ntt_synthetic_data_150.csv**: Validated entities and their respective validated ICD-10 codes, compared with the entities and codes returned by the model.
- **codigos_cie_format.csv**: CSV with all ICD-10 codes and their respective official descriptions.
- **raw/**: Folder containing a .txt file for each of the 150 notes created by NTT and their validated responses (entities and ICD-10 codes).

#### notebooks
Contains the Jupyter notebooks used in the project, organized into three subdirectories:

##### auxiliar
- **Formato_bd_cie10.ipynb**: Generates the file `codigos_cie_format.csv` from the original txt format.
- **NTT_synthetic_data.ipynb**: Generates the `ntt_synthetic_data_150.csv` and `ntt_synthetic_data_notes_150.csv` databases.

##### mistral
Organized into two versions, each with its respective notebooks:

- **Mistral_v1**: 
  - **Mistral_CIE10_v1.ipynb**: Evaluation of the raw Mistral model.
  - **Mistral_Prompt_Engineering_v1.ipynb**: Evaluation with Prompt Engineering techniques.
  - **Mistral_RAG_v1.ipynb**: Evaluation with RAG techniques using BioBERT and ClinicalBERT.

- **Mistral_v2**: 
  - **Mistral_CIE10_v2.ipynb**: Evaluation of the raw Mistral model.
  - **Mistral_Prompt_Engineering_v2.ipynb**: Evaluation with Prompt Engineering techniques.
  - **Mistral_CIE10_v2_RAG_BERT.ipynb**: Evaluation with RAG using BERT.
  - **Mistral_CIE10_v2_RAG_BioBERT.ipynb**: Evaluation with RAG using BioBERT.
  - **Mistral_CIE10_v2_RAG_ClinicalBERT.ipynb**: Evaluation with RAG using ClinicalBERT.
  - `prompt_example.txt`: Example of the prompt used in the Prompt Engineering notebook.

##### evaluation
- **eval_v2_NTT_synthetic_data_150.ipynb**: Retrieves the metrics and evaluations of the results for the NTT database (150 validated notes).
- **embedder_eval.ipynb**: Study of the RAG performance evaluating the chunks deemed relevant by BioBERT and ClinicalBERT.

#### output
Contains the obtained results:
- **results_eval_v1**: CSV and JSON results of the evaluation of the first database using different techniques.
- **results_mistral_v2**: CSV and JSON results of the codes and entities recognized by Mistral for the NTT-synthesized database (150 notes) using different techniques.
- **results_mistral_v1**: CSV results of the codes and entities recognized by Mistral for the first database using different techniques.

### Usage

#### Requisrements
- Python 3.8+
- Jupyter Notebook
- Mistral 7B

#### Installation
1. Clone the repository:
    ```sh
    git clone https://github.com/paulasanjuan/CIE10Codes_MBDS_TFM.git
    cd CIE10Codes_MBDS_TFM
    ```

2. Create and activate a virtual environment:
    ```sh
    python -m venv venv
    source venv/bin/activate  # En Windows usa `venv\Scripts\activate`
    ```

3. Install dependencies:
    ```sh
    pip install -r requirements.txt
    ```

4. Set up Mistral (if necessary):
    - [Link to the official Mistral documentation](https://docs.mistral.ai/)

#### Execution

1. Navigate to the `notebooks` folder and open the appropriate notebook based on the task you want to perform.
2. Follow the instructions in the notebook to run the model and obtain the necessary responses or evaluations.

### Conclusion

This project was developed to assess and improve accuracy in clinical note coding using advanced natural language processing techniques.


---

## Versión en Español

Proyecto de investigación para la extracción de códigos CIE-10 de notas clínicas utilizando Mistral 7B mediante diferentes técnicas. 

Este repositorio contiene el código y los recursos utilizados en el proyecto de investigación para evaluar el modelo Mistral 7B en la tarea de codificar notas clínicas (texto libre médico) según el estándar CIE-10. Se ha intentado refinar la performance del modelo mediante técnicas de Prompt Engineering y RAG (Retrieval-Augmented Generation).

### Estructura del Repositorio

El repositorio está organizado en las siguientes carpetas:

#### data
Contiene las bases de datos empleadas en el proyecto:
- **DS_v1.csv**: Base de datos inicial con notas clínicas sintetizadas a través de ChatGPT (no validadas, en espera de la base de datos oficial).
- **ntt_synthetic_data_notes_150.csv**: 150 notas creadas por NTT para la validación del modelo.
- **ntt_synthetic_data_150.csv**: Entidades validadas y sus respectivos códigos CIE-10 validados, comparados con las entidades y códigos devueltos por el modelo.
- **codigos_cie_format.csv**: CSV con todos los códigos CIE-10 y sus respectivas descripciones oficiales.
- **raw/**: Carpeta que contiene un .txt por cada una de las 150 notas creadas por NTT y sus respuestas validadas (entidades y códigos CIE-10).

#### notebooks
Contiene los notebooks de Jupyter utilizados en el proyecto, organizados en tres subdirectorios:

##### auxiliar
- **Formato_bd_cie10.ipynb**: Genera el archivo `codigos_cie_format.csv` a partir del formato txt original.
- **NTT_synthetic_data.ipynb**: Genera las bases de datos `ntt_synthetic_data_150.csv` y `ntt_synthetic_data_notes_150.csv`.

##### mistral
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

##### evaluation
- **eval_v2_NTT_synthetic_data_150.ipynb**: Obtiene las métricas y evaluaciones de los resultados para la base de datos de NTT (150 notas validadas).
- **embedder_eval.ipynb**: Estudio de la actuación de RAG evaluando los chunks considerados relevantes por BioBERT y ClinicalBERT.

#### output
Contiene los resultados obtenidos:
- **results_eval_v1**: Resultados CSV y JSON de la evaluación de la primera base de datos utilizando diferentes técnicas.
- **results_mistral_v2**: Resultados CSV y JSON de los códigos y entidades reconocidos por Mistral para la base de datos sintetizada por NTT (150 notas) utilizando diferentes técnicas.
- **results_mistral_v1**: Resultados CSV de los códigos y entidades reconocidos por Mistral para la primera base de datos utilizando diferentes técnicas.

### Uso

#### Requisitos
- Python 3.8+
- Jupyter Notebook
- Mistral 7B

#### Instalación
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

#### Ejecución

1. Navega a la carpeta `notebooks` y abre el notebook correspondiente según la tarea que desees realizar.
2. Sigue las instrucciones dentro del notebook para ejecutar el modelo y obtener las respuestas o evaluaciones necesarias.


### Conclusión

Este proyecto ha sido desarrollado para evaluar y mejorar la precisión en la codificación de notas clínicas utilizando técnicas avanzadas de procesamiento de lenguaje natural. Agradecemos cualquier retroalimentación y contribución para mejorar aún más este trabajo.
