---
dataset_info:
  features:
  - name: text
    dtype: 'null'
  - name: inputs
    struct:
    - name: 1-instruction
      dtype: string
    - name: 2-input
      dtype: string
    - name: 3-output
      dtype: string
  - name: prediction
    dtype: 'null'
  - name: prediction_agent
    dtype: 'null'
  - name: annotation
    dtype: 'null'
  - name: annotation_agent
    dtype: 'null'
  - name: vectors
    struct:
    - name: input
      sequence: float64
    - name: instruction
      sequence: float64
    - name: output
      sequence: float64
  - name: multi_label
    dtype: bool
  - name: explanation
    dtype: 'null'
  - name: id
    dtype: string
  - name: metadata
    dtype: 'null'
  - name: status
    dtype: string
  - name: event_timestamp
    dtype: timestamp[us]
  - name: metrics
    dtype: 'null'
  splits:
  - name: train
    num_bytes: 984065676
    num_examples: 52002
  download_size: 652741327
  dataset_size: 984065676
task_categories:
- text-generation
language:
- es
size_categories:
- 10K<n<100K
---
# Dataset Card de "somos-alpaca-es"

Este conjunto de datos es una versión traducida del dataset Alpaca en Español. 

Este conjunto de datos sirve como referencia para el esfuerzo colaborativo de limpieza y mejora del dataset durante el hackathon SomosNLP 2023.

Cuantas más personas y equipos participen mayor calidad final se podrá obtener. 

## El reto

A continuación se describen los pasos y normas para participar:

1. Se debe utilizar este conjunto de datos como punto de partida y mantener tanto los `ids` como la estructura. Esto es así para poder realizar tareas posteriores de validación cruzada y mejoras programáticas del dataset final.
2. Se trata de un dataset en formato compatible con Argilla. Cada equipo o persona que quiera participar, puede trabajar con su propia instancia de Argilla. Una forma fácil de desplegar Argilla es desplegar [Argilla en Spaces](https://huggingface.co/new-space?template=argilla/argilla-template-space).
3. Si se usa Argilla en Spaces, es muy recomendable realizar copias periódicas del dataset utilizando `rg.load("nombre_del_dataset").to_datasets().push_to_hub()` dado que si se reinicia el Space se pierden los datos. También se puede hacer un upgrade del Space a CPU-Upgrade.
4. Argilla se puede utilizar para validar y etiquetar manualmente y usando búsquedas y similitud semántica desde la UI. Para ello se pondrán ejemplos de uso del lenguaje de búsqueda en esta página, pero se recomienda consultar [la guía de uso](https://docs.argilla.io/en/latest/guides/query_datasets.html).
5. La validación humana es necesaria para garantizar la calidad final pero se pueden también limpiezas programáticas para aquellos casos en los que sea más eficiente. En cualquier caso, para el éxito del experimento se deberán utilizar las etiquetas propuestas, aunque se modifique programáticamente el dataset.
6. No se deben borrar registros del dataset, si un registro es inválido se deberá indicar en la etiqueta (por ejemplo `BAD INPUT`) o con el status `discard`.

El resultado del reto será un dataset por persona o equipo que contenga el dataset original etiquetado parcialmente, y opcionalmente otras versiones/subconjuntos del dataset con los datos corregidos, mejorados o aumentados. En estos casos es conveniente mantener un dataset a parte con los ids originales.

## Como empezar a etiquetar

Para etiquetar el dataset tienes que:

1. Lanzar tu Argilla Space siguiendo [este link](https://huggingface.co/spaces/somosnlp/somos-alpaca-es?duplicate=true). Esto te guiará para crear una instancia de Argilla en el Hub que cargará automaticamente el dataset. **IMPORTANTE**: que el Space se Public para poder leer los datos etiquetados desde Python. El proceso de carga puede tardar hasta 10 minutos, puedes consultar los logs para comprobar que se están cargando los datos.
2. Mientras se carga tu Argilla Space con el dataset puedes aprovechar para leer las guías de anotación.
3. Recomendamos que abras Colab o un notebook en local y que guardes el dataset periodicamente en un dataset del Hub (puede ser en tu espacio personal o tu organización). Para ello recomendamos leer el apartado como guardar el dataset en el Hub.

## Guías de anotación

Antes de empezar a anotar, es necesario leer la [guía de anotación](guia-de-anotacion.md) al completo.

## Como guardar el dataset en el Hub
Periodicamente se recomienda guardar una copia del dataset en el Hub ejecutando el siguiente código:

```python
import argilla as rg

# usar rg.init() si es necesario para definir la API_URL y API_KEY como en el notebook de carga del dataset
rg.load("somos-alpaca-es").to_datasets().push_to_hub("somos-alpaca-es") # se puede poner el nombre que se quiera en la llamada a push_to_hub
```

Una vez hecho esto se puede recuperar el dataset y volver a cargar en Argilla con el notebook de "Como cargar el dataset en Argilla"

## Ejemplos de consultas y trucos para etiquetar

TODO