# Accidentes Aereos
A lo largo de la historia, el ser humano creó diversos objetos que ayudarian a solucionar diversos problemas, pero tambien provocarian catastrofes, uno de esos inventos llega a ser el tema de este analisis, los objetos aereos suelen ser un medio de ayuda en transporte de cargas o viajes pero tambien puede ser un metodo para privar de la vida a personas, soy Ismael Flores y realice este proyecto para analizar accidentes aereos.

![accidente](https://www.publico.es/psicologia-y-mente/wp-content/uploads/2023/05/transport-1024x683.jpg)

## Objetivo

## Herramientas utilizadas:
- Python:
  - Pandas
  - Numpy
  - Pandas_profiling
  - Seaborn
- PowerBI
- SQL

## Pasos realizados:

- **Carga de datos y EDA:** Comence mi proyecto cargando los datos que tenia en el archivo "AccidentesAviones.csv" a un tipo de archivo dataframe para poder manejarlo con **Python**, luego de cargarlos realice una traducción a las columnas para solo manejar un idioma, luego definí cada una de las columnas del dataset, luego con **Pandas_profiling** realice una analisis en busca de datos nulos y repetidos y luego hice una serie de comentarios acerca de los resultados de tal analisis, despues hice un analisis en busca de valores atipicos en las columnas cuantitativas-continuas usando un **grafico de cajas(boxplot)** y por ultimo cargue mi dataframe a un nuevo csv.

- **PowerBI y Arreglos de columnas:** Luego de el EDA, cargue mi nuevo csv a **PowerBI** y comence una serie de arreglos en las columnas:
  - **Fecha:** Solo modifique el formato, cambiandolo a uno de tipo DD-MM-YY.
  - **Hora Declarada:** En esta columna hice varias modificaciones, comence por quitar las letras que habian en varias filas para solo quedarme con los numeros utilizando la funcion Text.Select(), luego cambie el formato a hora y luego lo volvi a cambia a texto para poder declarar los valores nulos como "Sin Declarar".
  - **Ruta:** Es una columna la cual contiene pocos valores nulos, asi que solo declare los valores nulos como "Sin Definir".
  - **Operador:** Al igual que la anterior columna tiene pocos nulos  y cambie esos nulos por "Sin Registrar".
  - **Motivos:** Esta es una columna con muchos valores nulos y procedimiento fue igual que las anteriores cambie los valores nulos como "Sin Registrar".
  - **Tipo de Aeronave:** Realice el mismo proceso que las 3 anteriores, reemplazando los valores nulos por "Sin Registrar".
  - **Total a Bordo:** Para esta columna hice una serie de modificaciones, primero cambie los nulos por 0, luego cree una columna condicional tal que **si** la columa **Total a Bordo** es mayor a 1 devuelva el mismo valor de la columna **pero si** **Total a Bordo** es menor que 1 tome el valor de **Pasajeros a Bordo** y si **Pasajeros a Bordo** fuera menor que **Total Fallecidos** tome el valor de **Total Fallecidos** y si no que sea 1.
  - **Pasajeros a Bordo:** Lo primero que hice es reemplazar todos los valores nulos por 10000, luego haré una columna condicional de tal que si **Pasajeros a Bordo** fuera **menor** que 10000 tome el valor de **Pasajeros a Bordo**, o si **Pasajeros a Bordo** es 10000 tome el valor de **Pasajeros Fallecidos** y si no que sea 0.
  - **Tripulacion a Bordo:** Comenzare reemplazando todos los nulos por 10000, luego creare una columna condicional de tal que si **Tripulacion a Bordo** sea menor que 10000 mantenga los datos, o si tripulacion es igual a 10000 introduzca el valor de **Total a Bordo**.
  - **Total Fallecidos:** En esta columna reemplazaré los valores nulos por 0, esto lo hago porque al investigar usando un filtro, veo que estos accidentes suelen tener un promedio de 1 **Pasajero a Bordo** y tienen las **Rutas** sin registro.
  - **Pasajeros Fallecidos:** El primer condicional que haremos será, que si **Pasajeros a Bordo** es 0, retorne el valor 0 y a este llamaremos aux. luego invocaremos otra columna condicional, con las condiciones que si el valor no es igual a null retorne el mismo valor pero si es null que retorne el valor de la columna aux que hemos creado antes.
  - **Fallecidos Tripulacion:** Lo primero que hice fue que si en **Pasajeros Fallecidos** es igual a 0 que me retorne el valor de la columna **Total Fallecidos** asi tendriamos nuestro primer condicional. Luego realice una columna personalizada para que restara **Total Fallecidos** y **Pasajeros Fallecidos**. Al final quedaria realizar una columna condicional para que en los valores nulos de la primera columna condicional hecha se incluyan los valores de la columna personalizada y al final eliminamos las columnas que usamos para el resultado.
  - **Fallecidos en Tierra:** Al ser una columna independiente, lo que hice fue rellenar los valores nulos con 0.
  - **Sumario:** Esta columna podria ser util para realizar un **NPL** pero para el objetivo de este analisis la veo irrelevante, asi que procederé a eliminarla.
  - **Creacion de nueva columnas:** En este aparto creare 2 nuevas columnas las cuales me seran utiles mas a delante, estas columnas son **Totales Afectados**(esta columna es la suma de **Total Fallecidos y Fallecidos en Tierra**), **Sobrevivientes**(esta columna es la resta de **Total a Bordo y Total Fallecidos**) y **Rango de Horas**(esta columna se separa en 3 partes mañana(00:00 - 08:00),tarde(09:01 - 16:00) y noche(16:01 - 23:59)).

- **Storytelling:** El objetivo de mi storytelling es concientizar acerca de estos sucesos atravez de una historia y datos hostoricos.
  
- **KPIs:** Estos son los 3 KPIs que estare utilizando en mi proyecto.
  - 

  
