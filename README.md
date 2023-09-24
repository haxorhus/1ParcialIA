# 1° Parcial - Inteligencia Artificial
## Objetivos 
El proyecto consiste en entrenar un modelo capaz de predecir si un alumno abandona o no una materia.
## Dataset utilizado
Se uso el dataset proveido por el profesor 'rend_2016a2022_modificado.csv', donde se encuentran los datos de todos los alumnos y todas sus materias desde el año 2016 hasta el 2020.
Se eligio hacer la prediccion sobre la materia 'Calculo 2'; Una materia de alta retencion.
## Consideraciones
No se tomaron en cuenta los datos obtenidos del año 2020, debido a la irregularidad de este año.
## Datos utilizados
### Se utilizaron los siguientes datos del dataset:
- 'Asignatura', tipo: Object; Se utilizo para aislar los datos de la materia elegida.
- 'Cod.Car.Sec', tipo: object; Se utilizo para  saber a que carrera esta matriculado el alumno 
- 'Idalumno', tipo: int; Para asegurarnos de que hablamos del mismo alumno cuando realizamos ciertos calculos.
- 'Anho','ciclo', tipo: int; Para saber el momento en el que el alumno curso alguna materia.
- 'Firma.Anho', tipo: int; Se usa para saber si el alumno es recursante o no.
- '1P','2P','T', tipo: int; Para saber el rendimiento del alumno en el proceso.
- 'Asistencia', tipo: int; Para saber si el alumno cumplió con el requisito de asistencia.

### Se crearon los siguientes datos para el entrenamiento
- 'Cant.Materias', tipo: int; Aqui se guardan la cantidad de materias que el alumno cursa en ese ciclo.
- 'Cant. C1', tipo: int; Contiene la cantidad de veces que el alumno curso la materia C1.
- 'Recursante' tipo: int; Para saber si el alumno ya curso la materia (1=si, 0=no).
- 'CGF', 'CIV', 'IND', 'MEC', 'ELE', 'MCT', 'ECA', tipo: int; Para saber a que carrera esta matriculado el alumno (1=si, 0=no).

### El dato de salida
- 'Abandono', tipo: int; Es la salida del modelo, que indica si el alumno abandonó la materia o no (1=si, 0=no).

## Modelo utilizado
Como tenemos un problema de clasificacion, decidimos utilizar el modelo de regresion lineal.

## Analisis de los resultados
Para analizar los resultados, ademas de mirar su precision tambien revisamos los graficos de 'loss' y 'val_loss' a lo largo de las epochs.
Si en el grafico las dos curvas se separan, y 'val_loss' aumenta mas que 'loss', esto significa que hubo overfitting y que debemos de utilizar menos iteraciones.
Con este analisis decidimos dejar las epochs=35 y tuvimos mejores resultados.
