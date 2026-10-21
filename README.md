# Limpieza y Análisis Exploratorio de Datos: Turnos Médicos

## 1. Descripción del proyecto

Este proyecto tiene como objetivo realizar la limpieza y el análisis exploratorio de un conjunto de datos reales de turnos médicos mediante Python y la biblioteca Pandas.

El análisis busca identificar patrones relacionados con la asistencia e inasistencia de los pacientes, con el propósito de obtener información que permita comprender mejor el comportamiento de los turnos programados.

## 2. Fuente de datos

**Dataset:** Medical Appointment No Shows.

**Fuente:** [Kaggle - Medical Appointment No Shows](https://www.kaggle.com/datasets/joniarroba/noshowappointments).

El conjunto de datos original contiene aproximadamente 110.527 registros de turnos médicos y 14 variables relacionadas con los pacientes, sus características, las fechas de los turnos y la asistencia.

Entre las variables utilizadas se encuentran:

- `Gender`: género del paciente.
- `ScheduledDay`: fecha y hora de programación del turno.
- `AppointmentDay`: fecha del turno.
- `Age`: edad del paciente.
- `Neighbourhood`: barrio donde se encuentra el centro de atención.
- `SMS_received`: indicador de recepción de SMS.
- `No-show`: indicador de asistencia o inasistencia.

## 3. Herramientas utilizadas

- Python.
- Pandas.
- NumPy.
- Google Colab.
- GitHub.

## 4. Diagnóstico inicial

Se realizó una inspección inicial para conocer la estructura y la calidad de los datos mediante los métodos `shape`, `info()`, `describe()`, `isnull().sum()` y `duplicated()`.

Los resultados mostraron:

- Ausencia de valores nulos en las columnas analizadas.
- Ausencia de registros completamente duplicados.
- Un registro con edad negativa, considerado inválido y excluido del análisis.
- Necesidad de convertir las columnas de fechas al tipo de dato datetime para facilitar su procesamiento.

## 5. Proceso de limpieza

Las tareas de limpieza realizadas fueron:

1. Creación de una copia del dataset original para preservar los datos de origen.
2. Revisión de valores nulos y duplicados.
3. Eliminación del registro con edad negativa.
4. Reinicio del índice mediante `reset_index(drop=True)`.
5. Conversión de `ScheduledDay` y `AppointmentDay` al tipo datetime.
6. Verificación de las dimensiones y de los tipos de datos después de las transformaciones.

No fue necesario imputar valores faltantes, ya que el diagnóstico inicial no detectó valores nulos.

## 6. Análisis exploratorio y agrupaciones

Se realizaron agrupaciones con `groupby()` para responder preguntas relacionadas con la asistencia de los pacientes.

### 6.1. Asistencia general

Se analizaron 110.526 turnos después de la limpieza:

- Turnos con asistencia registrada: 88.207 (79,81%).
- Turnos con inasistencia registrada: 22.319 (20,19%).

Los resultados muestran que aproximadamente dos de cada diez turnos no registraron asistencia.

### 6.2. Inasistencias según recepción de SMS

Se compararon las tasas de inasistencia entre los turnos con y sin SMS registrado:

- Sin SMS registrado: 75.044 turnos, con una tasa de inasistencia del 16,70%.
- Con SMS registrado: 35.482 turnos, con una tasa de inasistencia del 27,57%.

Se observó una diferencia de 10,87 puntos porcentuales entre ambos grupos. Esta comparación es descriptiva y no permite establecer una relación causal.

### 6.3. Inasistencias por barrio

Se agruparon los turnos por barrio y se calcularon el total de turnos, las inasistencias y su porcentaje.

Entre los diez barrios con mayor cantidad absoluta de inasistencias:

- Jardim Camburi presentó 1.465 inasistencias, con una tasa del 18,98%.
- Itararé registró la tasa más alta de la lista, con un 26,27%.
- Jardim da Penha presentó la tasa más baja de la lista, con un 16,28%.

Los resultados permiten observar diferencias entre barrios, considerando tanto la cantidad de inasistencias como el total de turnos de cada zona.

## 7. Conclusiones

El análisis permitió identificar que el 20,19% de los turnos analizados correspondió a inasistencias.

También se observaron diferencias en las tasas de inasistencia según la recepción de SMS y el barrio. Estos resultados pueden servir como punto de partida para profundizar el estudio de los factores asociados a las ausencias.

Las diferencias observadas no demuestran causalidad. Para comprender mejor estos patrones, sería necesario considerar otras variables, como la edad de los pacientes y el tiempo transcurrido entre la programación y la fecha del turno.

## 8. Archivos del proyecto

- `limpieza_analisis_turnos.ipynb`: notebook con el código, las transformaciones y los resultados.
- `README.md`: documentación del proyecto y descripción de las decisiones de limpieza.
- Dataset original o enlace a su fuente de descarga.

## 9. Objetivo de aprendizaje

Este trabajo permitió practicar la carga, inspección, limpieza y transformación de datos con Pandas, así como el uso de agrupaciones para obtener información relevante a partir de un conjunto de datos real.# limpieza-analisis-turnos-medicos
