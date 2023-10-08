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
  - **Columnas de Fallecidos:** En las columnas de fallecidos llegue a la conclucion de no alterar los datos nulos, me parece presipitado alterar o manejar datos nulos de fallecidos en tales accidentes sin llevar una investigación acabo.
  - **Sumario:** Esta columna podria ser util para realizar un **NPL** pero para el objetivo de este analisis la veo irrelevante, asi que procederé a eliminarla.
- **KPIs:**
