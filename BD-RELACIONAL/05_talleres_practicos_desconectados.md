# GUÍA DE TALLERES PRÁCTICOS DESCONECTADOS (LÁPIZ Y PAPEL)
## Módulo de Fundamentos de Bases de Datos Relacionales (Nivel Cero)
### Ficha 3571501 — Técnico en Procesamiento de Datos para Modelos de Inteligencia Artificial

> **CENTRO:** CENTRO DE DESARROLLO INDUSTRIAL, EMPRESARIAL Y CAMPESINO - CDIEC (Código: 9232)  
> **REGIONAL:** Cundinamarca  
> **INSTRUCTOR FACILITADOR:** Melqui Alexander Romero Veru  
> **COMPETENCIA:** 220501115 — Integración de datos desde múltiples fuentes de datos  
> **METODOLOGÍA:** Trabajo individual o en parejas. Cada aprendiz debe resolver los retos en su cuaderno o en hojas cuadriculadas antes de usar cualquier software.

---

## TALLER 1: Identificación de Entidades, Atributos y Dominios
### Caso: Clínica Veterinaria "Patitas Felices"

### 1.1 Contexto del Caso
El doctor Roberto administra una veterinaria y anota todo en una libreta de papel. Desea modernizar su negocio y le explica a usted lo siguiente:
> *"Vienen muchos dueños con sus mascotas. De los dueños necesito su cédula, nombre completo, teléfono y dirección. De cada mascota me interesa saber su nombre, especie (perro, gato, ave, etc.), raza, fecha de nacimiento, peso en kilos y si está vacunada o no. Además, cuando un veterinario atiende a una mascota en una consulta, anota la fecha y hora de la cita, el motivo de la consulta (ej. 'vómito persistente') y el costo cobrado."*

### 1.2 Retos a Desarrollar por el Aprendiz:
1. **Identificar las Entidades:** Enumere los 4 sustantivos principales que representan entidades independientes.
2. **Construir el Diccionario de Atributos:** Para cada entidad identificada, dibuje una tabla con las siguientes 4 columnas:
   - Nombre técnico del atributo (usando formato `snake_case`).
   - Tipo de dato sugerido (`VARCHAR`, `INT`, `DECIMAL`, `DATE`, `DATETIME`, `BOOLEAN`).
   - ¿Puede ser nulo? (`NULL` o `NOT NULL`).
   - Breve justificación en español.
3. **Poblar con Datos Ficticios:** Dibuje en una hoja una cuadrícula con 3 filas de ejemplo para la entidad `mascotas`.

---

## TALLER 2: El Detective de Llaves Primarias y Errores de Integridad
### Caso: Plataforma de Streaming de Música "MelodyStream"

### 2.1 Reto de Selección de Llaves Primarias (PK)
Para cada una de las siguientes entidades, analice los atributos y seleccione cuál es la **mejor opción para ser Llave Primaria (PK)**. Justifique si es una Llave Natural o Subrogada:
- **Entidad `canciones`:** Atributos disponibles: `titulo`, `duracion_segundos`, `artista`, `id_cancion`, `anio_lanzamiento`.
- **Entidad `usuarios`:** Atributos disponibles: `correo_electronico`, `nombre_completo`, `id_usuario`, `pais`, `fecha_registro`.
- **Entidad `vehiculos_reparto`:** Atributos disponibles: `numero_placa`, `color`, `modelo_anio`, `marca`.

### 2.2 Auditoría de Tablas con Errores Críticos
Observe las dos tablas siguientes y encuentre **los 4 errores graves de integridad y diseño**:

#### Tabla: `categorias`
| id_categoria (PK) | nombre_categoria |
| :---: | :--- |
| 1 | Rock |
| 2 | Pop |
| 1 | Salsa |
| NULL | Urbana |

#### Tabla: `albumes`
| id_album (PK) | titulo_album | anio | id_categoria (FK) |
| :---: | :--- | :---: | :---: |
| 501 | Abbey Road | 1969 | 1 |
| 502 | Thriller | 1982 | 2 |
| 503 | Canción Animal | 1990 | 99 |

*Preguntas del detective:*
1. ¿Qué anomalías hay en la Llave Primaria de la tabla `categorias`?
2. ¿Qué error de Integridad Referencial ocurre en el álbum con ID `503`?
3. Si intentamos borrar la categoría `1 (Rock)` de la tabla `categorias`, ¿qué problema se presenta con el álbum `501`?

---

## TALLER 3: Modelado de Relaciones y Cardinalidades
### Tres Escenarios de la Vida Cotidiana

### 3.1 Clasificación de Cardinalidad
Para cada uno de los siguientes enunciados, defina si la relación es **Uno a Uno (1:1)**, **Uno a Muchos (1:N)** o **Muchos a Muchos (N:M)**:
1. Un **País** y su **Presidente actual**.
2. Un **Profesor** y las **Asignaturas** que enseña (el profesor enseña varias y una asignatura puede ser dictada por varios profesores).
3. Una **Madre biológica** y sus **Hijos**.
4. Un **Cliente** y sus **Tarjetas de crédito**.
5. Una **Película** y los **Actores** que actúan en ella.

### 3.2 El Reto de la Tabla Intermedia (N:M)
Tome el caso 5: **`pelicula`** y **`actor`**.
- Explique con sus propias palabras por qué es imposible relacionarlas directamente sin una tabla intermedia.
- Proponga un nombre claro para la tabla intermedia.
- Dibuje la tabla intermedia indicando:
  * Sus dos llaves foráneas.
  * Al menos 2 atributos propios del encuentro (por ejemplo: `nombre_personaje` que interpreta el actor, `pago_honorarios`).
  * Tres filas de ejemplo inventadas.

---

## TALLER 4: Normalización Paso a Paso de una Hoja de Cálculo Real
### Caso: Taller Mecánico Automotriz "MotorTech"

A usted le entregan la siguiente hoja de cálculo donde el taller anota las reparaciones de vehículos:

### Hoja Original: `reparaciones_taller.xlsx`

| cod_orden | fecha | cliente_nombre | cliente_celular | placa_carro | carro_marca | mecanico_nombre | repuestos_usados | costo_mano_obra |
| :---: | :---: | :--- | :--- | :---: | :--- | :--- | :--- | :---: |
| 701 | 2026-10-01 | Andrés Ruiz | 3112233445 | ABC-123 | Renault | Pedro Gómez | Aceite sintético ($120.000), Filtro ($35.000) | $80.000 |
| 702 | 2026-10-02 | Diana Rojas | 3158899001 | XYZ-789 | Chevrolet | Carlos Meza | Pastillas de freno ($150.000) | $60.000 |
| 703 | 2026-10-03 | Andrés Ruiz | 3112233445 | ABC-123 | Renault | Pedro Gómez | Bujías ($90.000), Correa ($110.000) | $100.000 |

### 4.1 Actividades de Normalización:
1. **Paso 1 (1FN):** Elimine las listas de repuestos en celdas compuestas. Muestre cómo queda la tabla asegurando que cada repuesto sea una fila con precio y cantidad atómica.
2. **Paso 2 (2FN):** Identifique qué datos no dependen de la orden de reparación (los repuestos tienen su propio nombre y precio de inventario). Separe la tabla `repuestos`.
3. **Paso 3 (3FN):** Note que los datos del cliente (`cliente_nombre`, `cliente_celular`) se repiten en cada visita de Andrés Ruiz. Separe la entidad `clientes` y la entidad `vehiculos`.
4. **Paso 4 (Diagrama DER Final):** Dibuje en su cuaderno las tablas finales (`clientes`, `vehiculos`, `ordenes_reparacion`, `repuestos`, `detalle_repuestos_orden`) con sus respectivas conexiones PK y FK.

---

## TALLER 5: Modelado de Datos para un Proyecto de Inteligencia Artificial
### Caso: Monitoreo Predictivo de Servidores de IA en un Data Center

### 5.1 Enunciado del Problema
Una empresa de Inteligencia Artificial entrena modelos de Visión por Computadora en un centro de datos. Para evitar que las tarjetas gráficas (GPUs) y servidores se dañen por recalentamiento, quieren diseñar una base de datos para almacenar telemetría que luego alimentará un **modelo de Machine Learning predictivo de fallas de hardware**.

El sistema cuenta con:
- Múltiples **Servidores**, cada uno con su modelo, memoria RAM instalada y fecha de encendido.
- Múltiples **Sensores de Hardware** instalados en los servidores (ej. sensor de temperatura GPU, sensor de velocidad de ventilador RPM, sensor de voltaje). Cada sensor mide un tipo de variable física y tiene una unidad de medida (°C, RPM, Voltios).
- Una entidad de **Lecturas de Telemetría** en tiempo real: cada segundo, un sensor registra el valor medido numérico y la fecha/hora exacta (`timestamp`).
- Una entidad de **Eventos de Falla**: cuando un servidor se apaga repentinamente o reporta un fallo crítico, se registra la hora de la falla y la causa diagnóstica.

### 5.2 Entregable del Aprendiz:
1. Diseñe el esquema relacional completo (4 entidades).
2. Para cada entidad defina su Llave Primaria (PK) y sus Llaves Foráneas (FK).
3. Identifique los tipos de datos con precisión (vital para ingestión de datos en IA).
4. Explique con un párrafo: **¿Por qué la tabla de lecturas de telemetría crecerá millones de veces más rápido que la tabla de servidores y cómo las llaves foráneas evitan duplicar información?**
