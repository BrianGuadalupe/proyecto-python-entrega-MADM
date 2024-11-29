# Proyecto 1. Pandas
Con el fichero Fichero `sample_NYC_parking_issues.csv`


**Importante:** los cambios se arrastran en las siguientes preguntas.


### Crea un proyecto en Github para esta entrega e incluye un fichero Readme.md
Asegurate que es público ya que solo se puede entregar la URL del proyecto en github.
<hr/>


```python
!pip install pandas
```

    Requirement already satisfied: pandas in c:\users\asus\desktop\python_1\venv\lib\site-packages (2.2.3)
    Requirement already satisfied: numpy>=1.26.0 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2.1.3)
    Requirement already satisfied: python-dateutil>=2.8.2 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2.9.0.post0)
    Requirement already satisfied: pytz>=2020.1 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2024.2)
    Requirement already satisfied: tzdata>=2022.7 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2024.2)
    Requirement already satisfied: six>=1.5 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from python-dateutil>=2.8.2->pandas) (1.16.0)
    

    
    [notice] A new release of pip is available: 24.2 -> 24.3.1
    [notice] To update, run: python.exe -m pip install --upgrade pip
    


```python
%pip install pandas
```

    Requirement already satisfied: pandas in c:\users\asus\desktop\python_1\venv\lib\site-packages (2.2.3)
    Requirement already satisfied: numpy>=1.26.0 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2.1.3)
    Requirement already satisfied: python-dateutil>=2.8.2 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2.9.0.post0)
    Requirement already satisfied: pytz>=2020.1 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2024.2)
    Requirement already satisfied: tzdata>=2022.7 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from pandas) (2024.2)
    Requirement already satisfied: six>=1.5 in c:\users\asus\desktop\python_1\venv\lib\site-packages (from python-dateutil>=2.8.2->pandas) (1.16.0)
    Note: you may need to restart the kernel to use updated packages.
    

    
    [notice] A new release of pip is available: 24.2 -> 24.3.1
    [notice] To update, run: python.exe -m pip install --upgrade pip
    


```python
import pandas as pd
```


```python
# Cargar el archivo CSV
df = pd.read_csv('sample_NYC_parking_issues.csv', delimiter=';')
```

### A) Limpia el dataframe de aquellas columnas con todos sus campos a NAN


```python
df_limpio = df.dropna(axis=1, how='all')
print(df_limpio)

```

          Unnamed: 0  Summons Number    Plate ID Registration State Plate Type  \
    0        7192124      7684215310     24824MD                 NY        COM   
    1        1399831      5070680213    9TOPCLAS                 NY        OMT   
    2        5369188      1356951855     GEL1573                 NY        PAS   
    3        6338606      7713806271     EDU1026                 NY        PAS   
    4        2823881      7645478044     DXX6460                 NY        PAS   
    ...          ...             ...         ...                ...        ...   
    9995       51871      1359994981     42799JW                 NY        COM   
    9996     2178598      7531580299  BLANKPLATE                 99        999   
    9997     5536586      1353773541     FXW2962                 NY        PAS   
    9998     1127482      7207594008     CLR2162                 NY        PAS   
    9999     2822344      7536561775     DJG9703                 NY        PAS   
    
          Issue Date  Violation Code Vehicle Body Type Vehicle Make  \
    0     04/23/2014              71               VAN         FRIG   
    1     09/14/2013               7              4DSD        DODGE   
    2     02/13/2014              71              SUBN        HONDA   
    3     03/20/2014              21              SUBN        TOYOT   
    4     11/01/2013              20              4DSD        HONDA   
    ...          ...             ...               ...          ...   
    9995  07/24/2013              14               VAN          FRG   
    9996  10/10/2013              21               MCY        TRIUM   
    9997  02/21/2014              16               SDN        MAZDA   
    9998  09/05/2013              37              4DSD        HONDA   
    9999  11/01/2013              46              SUBN        HONDA   
    
         Issuing Agency  ...  Days Parking In Effect      From Hours In Effect  \
    0                 T  ...                     YYYYYYY                   NaN   
    1                 V  ...                         NaN                   NaN   
    2                 P  ...                     BBBBBBB                   ALL   
    3                 T  ...                        Y  Y                 1130A   
    4                 T  ...                       YYYYY                 0800A   
    ...             ...  ...                         ...                   ...   
    9995              P  ...                     BBBBBBB                   ALL   
    9996              T  ...                           Y                 1130A   
    9997              T  ...                     BBBBBBB                  0  :   
    9998              T  ...                           Y                 0800A   
    9999              T  ...                         NaN                   NaN   
    
          To Hours In Effect  Vehicle Color  Unregistered Vehicle?  Vehicle Year  \
    0                    NaN             WH                    NaN        2004.0   
    1                    NaN             BK                    NaN        2008.0   
    2                    ALL            NaN                    0.0        2006.0   
    3                  0100P             GY                    NaN        2008.0   
    4                  0600P             MR                    NaN        1996.0   
    ...                  ...            ...                    ...           ...   
    9995                 ALL           WHIT                    0.0        2007.0   
    9996               0100P          BLACK                    NaN           0.0   
    9997                0  :             GR                    0.0        1996.0   
    9998               1000P          SILVE                    NaN        2006.0   
    9999                 NaN          BLACK                    NaN        2005.0   
    
          Meter Number  Feet From Curb Violation Post Code  \
    0              NaN             0.0                01 4   
    1              NaN             0.0                 NaN   
    2                -             0.0                 NaN   
    3              NaN             0.0                14 4   
    4              NaN             0.0                03-A   
    ...            ...             ...                 ...   
    9995             -             0.0                 NaN   
    9996           NaN             0.0                01 -   
    9997             -             0.0                 NaN   
    9998      495-0067             0.0                52-P   
    9999           NaN             0.0                06 -   
    
                   Violation Description  
    0     71A-Insp Sticker Expired (NYS)  
    1       FAILURE TO STOP AT RED LIGHT  
    2                                NaN  
    3       21-No Parking (street clean)  
    4           20A-No Parking (Non-COM)  
    ...                              ...  
    9995                             NaN  
    9996    21-No Parking (street clean)  
    9997                             NaN  
    9998           37-Expired Muni Meter  
    9999    46A-Double Parking (Non-COM)  
    
    [10000 rows x 41 columns]
    

### B) Elimina todas las muestras donde la fecha no tenga coherencia: `Vehicle Year`, además transformalas a enteros (2024,2012,2006,etc.)


```python
from datetime import datetime

# Obtener el año actual
año_actual = datetime.now().year
print(año_actual)

```

    2024
    


```python
# Convertir la columna 'Vehicle Year' a numérico de manera segura utilizando loc
df_limpio.loc[:, 'Vehicle Year'] = pd.to_numeric(df_limpio['Vehicle Year'], errors='coerce')
```


```python

# Filtrar el DataFrame para mantener solo las filas con 'Vehicle Year' coherente (entre 1900 y el año actual)
df_filtrado = df_limpio[df_limpio['Vehicle Year'].between(1900, año_actual, inclusive=True)]

# Convertir 'Vehicle Year' a enteros
df_filtrado['Vehicle Year'] = df_filtrado['Vehicle Year'].astype(int)

# Mostrar el resultado
print(df_filtrado)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[22], line 2
          1 # Filtrar el DataFrame para mantener solo las filas con 'Vehicle Year' coherente (entre 1900 y el año actual)
    ----> 2 df_filtrado = df_limpio[df_limpio['Vehicle Year'].between(1900, año_actual, inclusive=True)]
          4 # Convertir 'Vehicle Year' a enteros
          5 df_filtrado['Vehicle Year'] = df_filtrado['Vehicle Year'].astype(int)
    

    File ~\Desktop\Python_1\venv\Lib\site-packages\pandas\core\series.py:5650, in Series.between(self, left, right, inclusive)
       5648     rmask = self < right
       5649 else:
    -> 5650     raise ValueError(
       5651         "Inclusive has to be either string of 'both',"
       5652         "'left', 'right', or 'neither'."
       5653     )
       5655 return lmask & rmask
    

    ValueError: Inclusive has to be either string of 'both','left', 'right', or 'neither'.


### C) Hay marcas de vehículos que no guardan sentido con ninguna marca real (`Vehicle Make`) elimina dichas muestras. Deja constancia de cuantas has borrado.


```python

```

### D) Representa en un grafíco de barras la cantidad de vehículos (por marca `Vehicle Make`) 


```python

```

### E) Unifica lo máximo que puedas la terminología de colores. Por ejemplo, valores como `WH` y `wh`y `wh\`hacen referencia al `white`


```python

```

### F) Representa en un gráfico de barras las marca de vehículo segmentadas por colores de vehículos.


```python

```

### H) Subé este código a tu repositorio. Incluye un documento Readme.md Indicando tan solo: "H"

### I) Convierte la serie `Issue Date` en una serie temporal y contabiliza las multas por `Violation Code[] y més del Issue Date.


```python

```

### J) Visualiza la anterior cuestión (I)



### K) Subé este código a tu repositorio. Sustituye la 'H' del readme.md por un 'end'


