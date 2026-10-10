# RUTA PEDAGÓGICA: FUNDAMENTOS DE BASES DE DATOS RELACIONALES (DESDE CERO)
## Nivelación Conceptual y Estructural Previa a SQL y Python
### Ficha 3571501 — Técnico en Procesamiento de Datos para Modelos de Inteligencia Artificial

> **CENTRO:** CENTRO DE DESARROLLO INDUSTRIAL, EMPRESARIAL Y CAMPESINO - CDIEC (Código: 9232)  
> **REGIONAL:** Cundinamarca  
> **INSTRUCTOR FACILITADOR:** Melqui Alexander Romero Veru  
> **COMPETENCIA:** 220501115 — Integración de datos desde múltiples fuentes de datos  
> **FASE FORMATIVA:** Análisis / Alistamiento Conceptual  
> **MODALIDAD:** Presencial / Desconectada (Lápiz, Papel, Pizarra y Análisis Lógico)

---

## 1. Justificación Pedagógica y Contexto

Durante las primeras aproximaciones a la formación técnica, se identificó que el grupo presenta vacíos estructurales en dos pilares fundamentales:
1. **Comprensión lógica de qué es una Base de Datos Relacional:** El aprendiz promedio tiende a pensar en una base de datos simplemente como "un archivo de Excel grande" o "una lista de cosas". Desconoce la naturaleza de las entidades, la necesidad de claves primarias, por qué se relacionan las tablas y qué significa la integridad referencial.
2. **Fundamentos de programación:** Si se introduce de golpe `sqlite3` y el módulo `os` en Python sin antes afianzar el modelo mental relacional, se genera una sobrecarga cognitiva insostenible: el aprendiz debe descifrar simultáneamente la sintaxis del lenguaje, la lógica de punteros/conexiones y la teoría del modelo de datos.

### La Estrategia: "Aislar la Dificultad"
Antes de escribir una sola línea de código en Python o sentencias complejas en SQLite, **separamos los conceptos**. Este módulo de nivelación se enfoca al 100% en:
- Comprender el valor del dato y su estructura organizada.
- Comprender la anatomía visual y funcional de una tabla/entidad.
- Entender el concepto de identificación unívoca (Llave Primaria - PK).
- Conectar información sin duplicarla (Llave Foránea - FK y Cardinalidad).
- Limpiar y estructurar modelos mediante normalización intuitiva.
- Resolver talleres prácticos de diseño con problemas de la vida real.

---

## 2. Mapa de Contenidos del Módulo

Este material está concebido para ser utilizado por el instructor en el ambiente de formación (CV-306, CV-309, CV-310) utilizando el tablero, presentaciones, debates grupales y talleres de lápiz y papel.

| Documento | Enfoque Pedagógico | Pregunta Clave que Resuelve |
| :--- | :--- | :--- |
| **[01. Anatomía de una Entidad](file:///c:/MELQUI/GIT_ORACLE/documentos/GitHub/planificador/desarrolloClases/trimestre_4/01_mode/fundamentos_bd_relacionales/01_que_es_una_bd_y_anatomia_entidad.md)** | De lo tangible a lo abstracto | *¿Por qué Excel no es una base de datos y cómo se compone una tabla por dentro?* |
| **[02. Llaves e Integridad (PK y FK)](file:///c:/MELQUI/GIT_ORACLE/documentos/GitHub/planificador/desarrolloClases/trimestre_4/01_mode/fundamentos_bd_relacionales/02_llaves_primarias_foraneas_e_integridad.md)** | Identidad y conexión lógica | *¿Por qué mi cédula es única y cómo conecto dos cosas sin repetir información?* |
| **[03. Relaciones y Cardinalidad](file:///c:/MELQUI/GIT_ORACLE/documentos/GitHub/planificador/desarrolloClases/trimestre_4/01_mode/fundamentos_bd_relacionales/03_relaciones_cardinalidades_y_modelo_er.md)** | Modelado visual (1:1, 1:N, N:M) | *¿Por qué existen tablas intermedias y cómo interactúan las cosas del mundo real?* |
| **[04. Normalización Intuitiva](file:///c:/MELQUI/GIT_ORACLE/documentos/GitHub/planificador/desarrolloClases/trimestre_4/01_mode/fundamentos_bd_relacionales/04_normalizacion_intuitiva_1fn_2fn_3fn.md)** | Calidad de datos (1FN, 2FN, 3FN) | *¿Cómo evitamos la duplicación de datos y errores fatales al registrar información?* |
| **[05. Banco de Talleres Prácticos](file:///c:/MELQUI/GIT_ORACLE/documentos/GitHub/planificador/desarrolloClases/trimestre_4/01_mode/fundamentos_bd_relacionales/05_talleres_practicos_desconectados.md)** | Trabajo activo de aprendices | *Ejercicios guiados: La Veterinaria, La Tienda, El SENA CDIEC y Datos para IA.* |
| **[06. Solucionario y Guía Docente](file:///c:/MELQUI/GIT_ORACLE/documentos/GitHub/planificador/desarrolloClases/trimestre_4/01_mode/fundamentos_bd_relacionales/06_solucionario_y_orientaciones_docente.md)** | Recursos de facilitación | *Soluciones paso a paso, errores típicos de los aprendices y preguntas detonantes.* |
| **[Simulador Visual Interactivo HTML](file:///c:/MELQUI/GIT_ORACLE/documentos/GitHub/planificador/desarrolloClases/trimestre_4/01_mode/fundamentos_bd_relacionales/simulador_visual_bd_relacionales.html)** | Apoyo audiovisual en clase | *Tablero digital interactivo con resaltado de partes, simulador PK/FK y relaciones.* |

---

## 3. ¿Cómo Conecta esto con la Inteligencia Artificial?

Para un técnico en **Procesamiento de Datos para Modelos de Inteligencia Artificial**:
1. **La IA se alimenta de datos estructurados:** Un modelo de Machine Learning no puede aprender de información caótica, inconsistente o duplicada.
2. **Las matrices y DataFrames son tablas relacionales:** Cuando un aprendiz use `pandas.read_sql()` o realice `pd.merge()`, estará aplicando exactamente los mismos principios de llaves y relaciones que aprende aquí.
3. **Calidad de datos desde el origen:** Entender restricciones (NOT NULL, UNIQUE, tipos de datos) evita el 80% de los errores habituales en pipelines de Machine Learning (valores atípicos, nulos inesperados y tipos mixtos).

---

## 4. Instrucciones de Uso para el Instructor

1. **Fase 1 (Explicación conceptual con metáforas cotidianas):** Utilice los archivos `01` y `02` acompañándose del proyector con el `simulador_visual_bd_relacionales.html`. Pida a los aprendices ejemplos de su propia vida (su carné SENA, su cédula, su historia clínica).
2. **Fase 2 (Modelado en la pizarra):** Utilice el archivo `03` y dibuje diagramas Entidad-Relación sencillos. Haga que los aprendices pasen al tablero a unir entidades con flechas y definir si la relación es 1:N o N:M.
3. **Fase 3 (Taller desconectado en equipos de 2 aprendices):** Asigne los ejercicios de `05_talleres_practicos_desconectados.md`. No permita el uso de computadores en esta fase; el objetivo es que piensen la estructura en papel cuadriculado.
4. **Fase 4 (Debate y retroalimentación):** Utilice `06_solucionario_y_orientaciones_docente.md` para comparar las soluciones de los diferentes grupos y mostrarles los "errores invisibles" (como crear relaciones N:M directas o permitir nulos en llaves primarias).
5. **Transición a código (Siguiente etapa):** Una vez superada esta nivelación conceptual, el paso a SQL puro y posteriormente a Python con `sqlite3` será fluido, intuitivo y sin frustraciones.
