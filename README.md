![portada](hhttps://github.com/monicaclaros/ETL_P4/blob/main/images/spain.jpeg)

# ETL_P4 CHALLENGE
Extraer, Transformar, Cargar (Loud) 

Extracción de data:
+ from ine Migraciones interiores, Resultados por comunidad autónoma, CSV
+ from Ayuntamiento de Madrid, Panel de indicadores de distritos y barrios de Madrid. Estudio sociodemográfico CSV
+ from web scrapping https://datos.gob_ en: https://datos.gob.es/es/catalogo/l01280796-inmigrantes-personas-atendidas-en-el-servicio-de-informacion-y-orientacion

Con este análisis intento conocer la cantidad de registros de personas extranjeras en España residentes en situación administrativa irregular y el género más vulnerable de esta población.

Transformación, proceso:
Help on function escaleta in module __main__:

escaleta()
    1. #Importar Librerías
    2. #explorar la web de INE y descargar csv migration_spain
    3. #Verificacion nulos y tamaños
    4. #Encabezados separar comunidades de códigos
    5. #Convertir a valores absolutos, habían datos con signo negativo
    6. #Encabezados separar año de semestre   
    7. #Tabla agrupada por comunidades autónomas y año
    8. #Análsis gráfico por CCAA
OBS: Las comunidades con mayor flujo de inmigración son Cataluña, Madrid y Com. Valenciana desde el año 2008 al 2022
    9. ##seleccionar el año 2022 (la última columna)
    10. #Elegimos a la CCAA de Madrid
    
OBS: se extraen los datos de Madrid y solamente datos del 2022 con 57461 registros de personas que llegaron ese año
    
    11. #api ayuntamiento de madrid 
    12. #Se conecta, más no envía los datos
OBS: He logrado descargar información en Json, pero no la logro cargar al archivo, así que continúo con CSV.
    13. #Descargamos ese estudio de la caaa de Madrid en CSV
    14. #LImpiar duplicados y eliminar nulos
    15. #Seleccionar año 2022 en barrios
    
OBS: Aquí hice el MERGE con las tablas del INE y con la del AYUNTAMIENTO DE MADRID usando la columna año 2022;
    16. #gráfico de barrios
    17. #Pivot de género y personas extranjeras
   
OBS: hice un análisis exploratorio y en madrid se han distribuido 57 461 personas con un 55% de ellas, mujeres

    18 #Web Scrapping datos.gob.es
    19. #Request, conctada
    20. #print(data) 
    21. #Importando beautiful Soup
    22. #encontramos links que tengan coincidencias con el contenido de "csv"
    23. #Descargamos el link del año 2022 para obtener datos
    24. #Análisis exploratorio
OBS: esta tabla es de MADRID; del servicio de atención ciudadana, he eliminado turistas, y datos en blanco
    25. #Elimino las 291 últimas filas porque estabana en Blanco, "nan"
    26. #Top 5 nacionalidades
OBS: el 2022 ha llegado un flujo más alto de personas con nacionalidad Peruana

    27. #histograma general
    28. #Tabla cruzada de situación administrativa y género
 OBS: con esta tabla pude entender que por cada hombre con situacion administrativa irregular en España hay dos mujeres en la misma situación. 
    29. #exportar a csv

