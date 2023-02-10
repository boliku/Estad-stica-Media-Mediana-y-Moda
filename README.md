# Estadística: Media, Mediana y Moda
## Media

La media es la suma del conjunto de valores dividida entre el número total de valores

![Media](./Images/media_arit.png)

```
edades = [20, 15, 41, 19, 62, 37, 14]
promedio = sum(edades)/len(edades)          #sum() Suma todos los valores del array.
                                            #len() Devuelve la longitud del array.
print("Con funciones nativas:", promedio)


import numpy as np          #Importamos la librería numpy para el calculo estadístico.
edades = np.array([20, 15, 41, 19, 62, 37, 14])
promedio = edades.mean()    #Mean() Nos deuelve el valor promedio o media aritmética.        
print("Con numpy:", promedio)

# Redondeo
print("Redondeado:", round(promedio), "años")           #round() Redondea el valor numérico.
```

## Ejercicio alumnos

```
import pandas as pd
df_alumnos = pd.read_csv("./CSV/datos_alumnos.csv")         #read_csv() Nos permite leer un archivo .csv
df_alumnos
```
### Promedio de las edades de todos los alumnos
```
prom_edades = df_alumnos["Edad"].mean()
print("Promedio de edades:", round(prom_edades), "años")
```
### Promedio de alturas de las estudiantes mujeres

```
df_alumnas = df_alumnos[df_alumnos["Género"]=="Mujer"]
df_alumnas
```
promedio_altura_mujeres = df_alumnas["Altura"].mean()
print("Altura media de las mujeres:", round(promedio_altura_mujeres, 2), "metros")
```
# Moda
La moda es el valor que aparece con mayor frecuencia en un conjunto de valores de datos.

![Moda.pnh](./Images/moda.png)

```
notas = [12, 20, 15, 18, 16, 15, 12, 15, 11, 15, 12, 18]
cantidad = []
for i in notas:
    cantidad.append(notas.count(i))         #append() Agrega un elemento a la lista.
                                            #count() Devuelve la cantidad de veces que se repite un elemento en la lista. 
moda = notas[cantidad.index(max(cantidad))]         #Devuelve el máximo valor de la lista.
print("La moda es:", moda)
```
## Ejercicio catálogo de Netflix

```
df_netflix = pd.read_csv("netflix_titles.csv")
df_netflix
```
### ¿De qué año hay más películas y series en Netflix?

```
moda = df_netflix["release_year"].mode()        #mode() Devuelve la moda de un determinado conjunto de datos.
print("La moda es:", int(moda))
```
### ¿En qué país se han producido más películas y series?

```
moda = df_netflix["country"].mode()
print("La moda es:", moda)
```
### Mediana de edades

``edades = [20, 15, 41, 19, 62, 37, 14, 1]
edades = sorted(edades)
print("Edades ordenadas:", edades)

if len(edades) % 2 != 0:
    mediana = edades[(len(edades)-1)//2]
else:
    mediana = (edades[len(edades)//2-1] + edades[len(edades)//2])/2
print("Con funciones nativas:", mediana)


import numpy as np
edades = np.array([20, 15, 41, 19, 62, 37, 14, 1])
mediana = np.median(edades)         #median() Devuelve la mediana de un determinado conjunto de datos.
print("Con numpy:", mediana)`

```
## Ejercicio calificaciones de estudiantes

```
import pandas as pd
df_estudiantes = pd.read_csv("StudentsPerformance.csv")
df_estudiantes
```
### ¿Cuál es la mediana de las calificaciones en matemáticas?

```
mediana = df_estudiantes["math score"].median()
print("La mediana es:", mediana)
```
