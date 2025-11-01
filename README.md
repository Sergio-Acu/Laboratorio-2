# Laboratorio-2
### Integrantes: 
Sergio Andrés Acuña Alzate

Maria Camila Castrillón Ocampo

Juan David Vargas Rodriguez

## Descripción:
Este proyecto consiste en procesamiento y limpieza de datos de un dataset de Pokémon (pokemonDB_dataset.json).
El objetivo principal es preparar los datos para análisis y visualización, transformando información textual en valores numéricos y separando atributos compuestos para facilitar su uso en análisis posteriores.

## Etapa 1: Procesamiento y limpieza de datos

1.*Carga y exploración del dataset*

-Se cargó el archivo pokemonDB_dataset.json usando la librería json.
-Conversión del diccionario en un DataFrame de pandas (pd.DataFrame.from_dict).
-Exploración inicial de las columnas, llaves y pares clave-valor (keys(), items()) para comprender la estructura del dataset.
-Revisión de tipos de datos y estadísticas descriptivas usando df.info() y df.describe(include='all').

2.*Extracción y conversión de valores numéricos*

-Extracción de valores de altura y peso de las columnas Height y Weight mediante expresiones regulares.
-Conversión de estas columnas a tipo numérico (float) para permitir análisis cuantitativo.
-Conversión de columnas de estadísticas base (HP Base, Attack Base, Defense Base, Speed Base, Special Attack Base, -Special Defense Base, Base Exp) a numérico usando pd.to_numeric(errors='coerce').

3.*Separación de columnas compuestas*

-Separación de la columna Type en Type1 y Type2 para identificar tipos primario y secundario.
-Limpieza de espacios en blanco con str.strip().
-Extracción de porcentajes de género de la columna Gender en nuevas columnas Male_% y Female_%, convertidas a valores numéricos.

4.*Creación del dataset limpio*

-Selección de columnas relevantes para análisis en un DataFrame limpio poke_clean.
-Verificación y manejo de valores nulos (isnull().sum()).
-Clasificación de variables
-Identificación de columnas numéricas y categóricas para análisis exploratorio posterior.
-Listado de variables numéricas (Val_num) y categóricas (Val_cat) para facilitar la planificación de visualizaciones y análisis estadísticos.

## Etapa 2: Exploratory Data Analysis (EDA)

### Respuestas 10 preguntas

1.*¿Cuál es el promedio, mínimo y máximo de los atributos base (HP, Attack, Defense, Speed) de todos los Pokémon?*

**R/**
HP= 71,24(mean);  1(min); 255(max)
ATB= 81,15(mean); 5(min); 190(max)
DFB= 75,01(mean); 5(min); 250(max)
SPB= 70,03(mean); 5(min); 200(max)

Se logra evidenciar que la media más alta es la perteneciente a la estadística Ataque base, por otro lado el más bajo es perteneciente a la estadística Velocidad base, a pesar de estos datos el que tiene un valor máximo menor es la misma estadística que tiene una mayor media; el valor con el máximo mas grande es el mismo que tiene el menor de los mínimos siendo esta la estadistica de HP base.

2.*¿La distribución es simétrica o sesgada?*

**R/**
 La distribución es segada a la derecha porque la mayor cantidad de valores esta hacia la izquierda y la mayor cantidad  y muy pocos tienen valores muy altos por esta razon es sesgada positiva.

 <img width="854" height="553" alt="image" src="https://github.com/user-attachments/assets/ca674c2f-0d8d-48a7-b325-ea0abdf7a618" />


3.*¿Qué tipo de Pokémon tiene ataques más altos en promedio?

**R/**
Los valores presentados son: 

**Tipo lucha**: 104.96

**Tipo dragón**: 103.81

**Tipo tierra**: 94.08

Al revisar las medianas se puede ver que las estadísticas de ataque base tienen a ser mayores en pokemones de tipo lucha esto dado a la naturaleza del tipo del cual todos sus ataques son tipo físicos.


<img width="1389" height="590" alt="image" src="https://github.com/user-attachments/assets/c9360b71-9a57-49ab-a476-41ce80c3b7e6" />


4.*¿Cuál es el top 5 de especies (Species) más frecuentes en el dataset?*

**R/**

**Paradox Pokémon** 22

**Mouse Pokémon** 14

**Fox Pokémon** 9

**Dragon Pokémon** 9

**Pumpkin Pokémon** 8

Esta revision del dataset se muestra que la mayor cantidad de pokemones son de un tipo que incorporaron hace poco, pero aun asi son la mayor porque son versiones futuras o pasadas de pokemones existentes y al no tener una categoría como si forman entre ellos el mas grande grupo de especies de Pokémon.


5.*¿Qué tipo es el más común?*

**R/**

El tipo mas comun en los pokeon es el tipo agua con aproximadamente 150 pokemones. 

Esto demuestra que a lo largo de la historia pokemon el tipo más común o más diverso ha sido el tipo agua, que aunque no es el tipo mas querido, ni el mas fuerte aun asi ha sido el mas abundante en cada generacion emergente.


<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/ee9096ce-c6a0-4afb-9795-0c06571ebd90" />


6.*¿Qué atributos están más correlacionados entre sí?*

**R/**
Las correlaciones más importantes están dadas entre (Ataque Base y HP) y ( Ataque Base y Defensa Base ) estas siendo de 1-0.461 y 1-0.468 respectivamente.

Esto demuestra que el ataque esta más correlacionado hacia la estadistica de Defensa Base, aunque la diferencia con el Hp es mínima; siendo la diferencia más grande con la velocidad en todas las estadísticas con énfasis en la defensa.


7.*Interprete el mapa de calor de correlaciones.*

**R/**
La estadística speed muestra una menor correlación mostrando el color mas oscuro de la grafica mientras que las demas estadísticas son más similares entre ellas acercandose a un color mas claro segun la paleta de colores de esta grafica.

Las estadísticas bases de un Pokémon son poco predecibles dado a que estas no llegan a variar o depender de alguna resistencia, habiendo pokemones con muy bajas estadísticas base y otros con extraordinarias estadísticas, pero esos extremos tienen en común que sus fuerza o su debilidad es en múltiples estadísticas.


<img width="593" height="470" alt="image" src="https://github.com/user-attachments/assets/6f1febc4-4474-4898-85e9-5da0094c4db6" />


8.*¿Existe relación entre el peso de un Pokémon y su capacidad de ataque?*

**R/**
No específicamente.

Si se analiza la grafica se puede evidenciar que hay pokeones con mucho peso y bajo que tienen su Ataque Base muy alto, siendo mas concistente entre un peso de 200 y 600 en los cuales la estadística se mantiene entre 50-150 aproximadamente, no teniendo tanto salto como en los pokemones mas pesados ni en los mas livianos.


<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/9909618a-dea5-444a-a5a3-ad3e20536078" />


9.*¿Qué tipo tiende a tener Pokémon más grandes?*

**R/**
Los tipos con Pokémon más grandes son:
1. **Poison**: 59.02 kg promedio, 3.61 m altura
2. **Steel**: 228.53 kg promedio, 2.05 m altura
3. **Dragon**: 121.13 kg promedio, 2.04 m altura


10.*¿Qué tipo de Pokémon tiende a ser más rápido?*

**R/**
Eléctrico.

En las graficas se logra evidenciar como el tipo electrico ademas de abarcar gran area es el unico que tiene pokemones que alcanzan velocidades de mas de 200 en su estadistica por lo cual al momento de sacar la media entre los diferentes tipos, la mas grande es el electrico dejando a esta como el tipo de pokemon mas rápido entre los 3.


<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/f4faca56-7303-49f8-81f6-ede66a6c77e1" />





