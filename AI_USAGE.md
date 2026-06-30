
# AI_USAGE.md — Lab 5: Embeddings y búsqueda semántica

## Herramienta utilizada

- **Claude (claude.ai)** — modelo Claude Haiku 4.5

## Uso declarado

| Momento | Para qué consulté la IA                                                                                                                                   | Qué hice yo                                                                                                                  |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| A.1     | Error al descargar/cargar`cc.es.300.bin` (timeout y problema de memoria en la primera corrida local)                                                      | Pregunté la causa del error y ejecuté el notebook en Google Colab con GPU, como indica el enunciado                         |
| A.1     | Duda sobre la diferencia entre`ft.get_word_vector` y `ft.get_sentence_vector`                                                                           | Confirmé en la documentación oficial de fastText cuál correspondía al TODO y la usé                                      |
| B.4     | Duda de por qué el NDCG del semántico bajó en la consulta "sequía y cultivos" en vez de subir, contrario a lo que esperaba por la falla del agua de A.3 | Revisé el resultado a mano, comparé los documentos recuperados y redacté yo mismo la explicación en la celda de análisis |

## Lo que NO se generó con IA

- El código de las celdas `# TODO` (`vec`, `cos_vec`, `vector_documento`, `buscar_semantico`, comparación de los tres sistemas).
- Las funciones de métricas y los qrels (reutilizados sin cambios del Lab 3).
- El preprocesamiento (reutilizado sin cambios del Lab 1/2/3).
- Los análisis escritos en las celdas de markdown (vecinos sorprendentes, falla del agua, analogías, NDCG por consulta).
- Este documento.

## Nota de entorno

Este laboratorio requiere descargar `cc.es.300.bin` (vectores FastText en español, varios GB),
tal como indica el enunciado. La ejecución completa con salidas se hizo en Google Colab (GPU)
por el tamaño del modelo.

---

*Hugo Francisco Luis Inclán — UPCh 2026A — Minería de Datos*