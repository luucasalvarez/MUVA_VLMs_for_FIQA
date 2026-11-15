# Planteamiento del proyecto

## Contexto y objetivo

Este repositorio (`vlm-fiqa`) contiene el trabajo de la asignatura Biometría Informática del Máster Universitario en Visión Artificial (URJC), correspondiente al tema 4: **Modelos de visión-lenguaje para analizar la calidad biométrica de imágenes faciales**.

El objetivo es estudiar el estado del arte de la evaluación de calidad de imágenes faciales (Face Image Quality Assessment, FIQA), con especial atención a los modelos de visión-lenguaje (Vision-Language Models, VLMs), y analizar en qué medida estos modelos permiten estimar la calidad biométrica y explicar los factores que la condicionan.

La pregunta central del trabajo es: **¿pueden los VLMs evaluar y explicar la calidad de una imagen facial de manera que sus resultados se correspondan con su utilidad real para el reconocimiento biométrico, y no únicamente con su calidad perceptual?**

Se trata principalmente de un trabajo teórico y de revisión comparativa de la literatura científica. El documento final tendrá aproximadamente 15 páginas, con formato de artículo científico y referencias bibliográficas, acompañado de una presentación de unas 20 diapositivas.

## Estructura del trabajo

### 1. Introducción

- Contextualizar la evaluación de calidad dentro de los sistemas de reconocimiento facial y explicar su importancia para reducir los errores biométricos.
- Introducir la diferencia entre calidad perceptual de una imagen y utilidad biométrica.
- Presentar la motivación para incorporar VLMs: obtener evaluaciones interpretables y recomendaciones que permitan mejorar la captura facial.
- Definir los objetivos y el alcance del trabajo.

### 2. Estado del arte

Se seguirá una progresión desde los fundamentos generales de la evaluación de calidad de imágenes hasta su aplicación biométrica mediante modelos de visión-lenguaje.

#### 2.1. Image Quality Assessment (IQA)

- Definición de calidad de imagen y principales factores que la afectan: iluminación, desenfoque, ruido, resolución y compresión.
- Métodos con referencia completa (FR-IQA), referencia reducida (RR-IQA) y sin referencia (NR-IQA).
- Diferencias entre IQA general y FIQA: pose, expresión, oclusiones y condiciones de captura facial; relación con el rendimiento del reconocimiento.

#### 2.2. Vision-Language Models (VLMs)

- Fundamentos de los modelos multimodales y del aprendizaje conjunto de representaciones visuales y textuales.
- Arquitecturas y enfoques representativos: modelos contrastivos como CLIP y modelos multimodales generativos como Qwen-VL y LLaVA.
- Estrategias de adaptación a nuevas tareas: zero-shot, few-shot y fine-tuning.

#### 2.3. Deep Learning aplicado a Image Quality Assessment

- Evolución desde métricas tradicionales hasta métodos basados en redes neuronales profundas.
- Métodos basados en CNN, transformers y otras arquitecturas relevantes.
- Métodos específicos de FIQA basados en la utilidad biométrica y en las representaciones de los modelos de reconocimiento facial: SER-FIQ, SDD-FIQA, FaceQAN, ViT-FIQA y eDifFIQA, entre otros.
- Limitaciones de los métodos que proporcionan únicamente puntuaciones escalares de calidad.

#### 2.4. VLMs aplicados a IQA y FIQA

- Uso de modelos visión-lenguaje para estimar calidad, detectar degradaciones y generar explicaciones en lenguaje natural.
- Trabajos representativos en IQA general, como Q-Align, y en FIQA, como CLIB-FIQA.
- Análisis de métodos generativos recientes, especialmente el artículo de referencia del proyecto, que estudia VLMs generalistas en un escenario zero-shot.
- Comparación conceptual entre puntuaciones de calidad, etiquetas de atributos, explicaciones textuales y sistemas híbridos que combinan FIQA especializado con VLMs.

### 3. Experimentación y evaluación comparativa

El objetivo de este apartado es comparar los enfoques más utilizados y los avances recientes mediante los protocolos, datasets, métricas y resultados experimentales disponibles en la literatura. No se presupone la ejecución de experimentos propios: su posible incorporación se decidirá según el alcance acordado con el profesor y los recursos disponibles.

#### 3.1. Datasets y protocolos

Estudiar los conjuntos de datos utilizados en el campo, sus características y los escenarios de evaluación que representan. Como punto de partida:

| Dataset | Interés para el trabajo |
| --- | --- |
| LFW | Verificación facial en condiciones no controladas. |
| IJB-B | Reconocimiento facial con variaciones reales de captura, pose y oclusión. |
| SCFace | Imágenes de vigilancia obtenidas a diferentes distancias. |
| CelebA-HQ | Imágenes de alta calidad y generación de degradaciones sintéticas controladas. |

Se podrán incorporar otros datasets relevantes conforme avance la revisión bibliográfica, distinguiendo aquellos orientados a calidad perceptual de los que permiten medir utilidad biométrica.

#### 3.2. Comparación de métodos y resultados

- Comparar métodos FIQA especializados con enfoques basados en VLMs, teniendo en cuenta los modelos de reconocimiento facial empleados, el preprocesamiento y los protocolos de cada estudio.
- Analizar la utilidad biométrica mediante curvas Error-versus-Reject (EvR), FNMR a FMR fija y áreas parciales bajo la curva (pAUC).
- Evaluar la capacidad de detectar y explicar degradaciones, la fidelidad de las explicaciones, las alucinaciones, la consistencia de las puntuaciones y la sensibilidad al prompt.
- Considerar el coste computacional y la latencia cuando se disponga de mediciones comparables.

Los resultados se organizarán mediante tablas y figuras que faciliten la comparación. No se compararán directamente cifras obtenidas bajo protocolos incompatibles sin explicar sus diferencias. Se distinguirán los resultados publicados de cualquier resultado experimental propio.

### 4. Conclusiones y horizontes futuros

- Sintetizar los principales hallazgos del estado del arte y la evaluación comparativa.
- Valorar si los VLMs ofrecen una estimación de calidad realmente alineada con la utilidad biométrica y qué ventajas aportan en explicabilidad.
- Discutir las limitaciones actuales: alucinaciones, dependencia de la arquitectura y del prompt, generalización, coste computacional y posibles sesgos.
- Identificar líneas futuras: modelos especializados mediante fine-tuning, sistemas híbridos, mejores benchmarks de explicabilidad y validación en escenarios biométricos reales.

## Artículo de referencia

Sarıtaş, E., Onaran, E., Štruc, V. y Ekenel, H. K. (2026). *Employing Vision-Language Models for Face Image Quality Assessment*. IEEE International Conference on Automatic Face and Gesture Recognition (FG).

- Artículo: https://arxiv.org/abs/2605.17489
- Código: https://github.com/ThEnded32/VLM4FIQA

Este trabajo constituye el punto de partida, no la única fuente del proyecto. Compara VLMs generalistas con métodos FIQA especializados y estudia la utilidad biométrica, la detección de degradaciones, la consistencia de las explicaciones y la robustez frente a variaciones del prompt. Se ampliará la revisión con trabajos fundamentales y recientes para contextualizar y contrastar sus resultados.

## Directrices para colaboradores y agentes

- Mantener el foco en la calidad **biométrica facial**; la IQA general y los fundamentos de los VLMs sirven para contextualizar el problema.
- Respetar la estructura acordada y evitar desarrollar apartados ajenos al objetivo principal, como la detección de deepfakes o el reconocimiento de identidad como temas independientes.
- Priorizar artículos científicos originales, revisiones relevantes y documentación oficial de datasets y modelos. Registrar autores, año, publicación y DOI o enlace verificable.
- Distinguir entre calidad perceptual, utilidad biométrica, consistencia de las explicaciones y exactitud de las explicaciones: no son propiedades equivalentes.
- No inventar referencias, resultados ni experimentos. Indicar cuándo una afirmación procede de la literatura, cuándo es una interpretación y cuándo constituye una hipótesis o propuesta futura.
- Mantener una terminología coherente a lo largo del documento y definir las siglas en su primera aparición.
- Este planteamiento es una guía de contexto compartido para el repositorio. Podrá actualizarse conforme avance la revisión y se acuerde el índice definitivo con el profesor.
