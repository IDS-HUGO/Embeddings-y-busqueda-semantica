# AI_USAGE.md — Lab 5: Embeddings y búsqueda semántica

## Herramienta utilizada
- **Claude (claude.ai)** — modelo Claude Sonnet

---

## Uso declarado

| Sección | Celda / actividad | Qué proporcionó la IA | Qué cambié o verifiqué yo |
|---------|-------------------|------------------------|---------------------------|
| A.1 | Carga de FastText | Sintaxis de `fasttext.util.download_model` y `ft.get_word_vector` | Verifiqué contra la documentación oficial de fastText (facebookresearch/fastText) |
| A.3 | `cos_vec` | Implementación de coseno con `numpy` y manejo de norma cero | Validé numéricamente contra la función `coseno` de bolsa de palabras del Lab 2/3 |
| B.1 | `vector_documento` | Patrón de promedio de vectores con `np.mean` y caso de tokens vacíos | Decidí devolver vector cero (en vez de lanzar excepción) para no romper la comparación en B.3 |
| B.3 | Tabla comparativa de 3 sistemas | Estructura de impresión lado a lado | Elegí `'problemas de agua'` como consulta de prueba precisamente porque verifiqué manualmente que d02 usa `hidrico` y no `agua`, para forzar el caso de la "falla del agua" |
| B.4 | Análisis de NDCG por consulta | — | Verifiqué empíricamente (ejecutando TF-IDF/BM25 sin FastText) que `buscar_tfidf('problemas de agua')` y `buscar_bm25('problemas de agua')` NO recuperan d02, confirmando la hipótesis del análisis antes de redactarlo |

---

## Lo que NO se generó con IA

- Los qrels y las funciones de métricas (P@k, R@k, MRR, MAP, NDCG): reutilizados sin cambios del Lab 3, ya validados en esa entrega.
- El preprocesamiento (`normalizar`, `preprocesar`): reutilizado sin cambios del Lab 1/2/3.
- La elección de las 3 consultas de prueba en B.3 y el razonamiento sobre cuándo gana el semántico vs. cuándo gana BM25.
- Este mismo documento.

## Nota de entorno

Este laboratorio requiere descargar `cc.es.300.bin` (vectores FastText en español, varios GB),
tal como indica el propio enunciado. La ejecución completa con salidas debe hacerse en Google
Colab o en una máquina local con suficiente RAM, no en un entorno con red restringida.

---

*Hugo Francisco Luis Inclán — UPCh 2026A — Minería de Datos*
