# Obtención y limpieza de datos-Curso-Proyecto-DB COURSERA

Una de las áreas más emocionantes de toda la ciencia de datos en este momento es la computación portátil. Consulte, por ejemplo, [ este artículo ] (http://www.insideactivitytracking.com/data-science-activity-tracking-and-the-battle-for -la-mundo-top-marca-deportiva /). Compañías como Fitbit, Nike y Jawbone Up están compitiendo para desarrollar los algoritmos más avanzados para atraer nuevos usuarios.

En este proyecto, los datos recopilados del acelerómetro y el giroscopio del teléfono inteligente Samsung Galaxy S se recuperaron, trabajaron y limpiaron para preparar datos ordenados que se pueden usar para un análisis posterior.

Este repositorio contiene los siguientes archivos:

-  `README.md` , este archivo, que proporciona una visión general del conjunto de datos y cómo se creó.
-  `tidy_data.txt` , que contiene el conjunto de datos.
-  `CodeBook.md` , el libro de códigos, que describe el contenido del conjunto de datos (datos, variables y transformaciones utilizadas para generar los datos).
-  `run_analysis.R` , la secuencia de comandos R que se usó para crear el conjunto de datos (consulte la sección [ Creación del conjunto de datos ] (# creación del conjunto de datos) a continuación)

##  Diseño del estudio <a name="study-design"> </a>

El conjunto de datos de origen en el que se basó este proyecto se obtuvo del [ Reconocimiento de actividad humana utilizando el conjunto de datos de teléfonos inteligentes ] (http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones# ), que describe cómo los datos se recopilaron inicialmente de la siguiente manera:

> Los experimentos se han llevado a cabo con un grupo de 30 voluntarios en un rango de edad de 19-48 años. Cada persona realizó seis actividades (CAMINANDO, CAMINANDO \ _ MATERIALES, CAMINANDO \ _ CUENTAS DE AISLAMIENTO, SENTANDO, COLOCANDO, PONIENDO) usando un teléfono inteligente (Samsung Galaxy S II) en la cintura. Usando su acelerómetro y giroscopio integrados, capturamos la aceleración lineal 3-axial y la velocidad angular 3-axial a una velocidad constante de 50Hz. Los experimentos se han grabado en video para etiquetar los datos manualmente. El conjunto de datos obtenido se ha dividido aleatoriamente en dos conjuntos, donde se seleccionó el 70% de los voluntarios para generar los datos de entrenamiento y el 30% de los datos de prueba.
> 
> Las señales de los sensores (acelerómetro y giroscopio) se procesaron previamente mediante la aplicación de filtros de ruido y luego se tomaron muestras en ventanas deslizantes de ancho fijo de 2.56 segundos y superposición del 50% (128 lecturas / ventana). La señal de aceleración del sensor, que tiene componentes de movimiento gravitacional y corporal, se separó utilizando un filtro de paso bajo Butterworth en la aceleración y la gravedad del cuerpo. Se supone que la fuerza gravitacional tiene solo componentes de baja frecuencia, por lo tanto, se utilizó un filtro con una frecuencia de corte de 0,3 Hz. Desde cada ventana, se obtuvo un vector de características calculando variables del dominio del tiempo y la frecuencia.
Los datos de entrenamiento y prueba se combinaron primero para crear un conjunto de datos, luego se extrajeron las mediciones sobre la media y la desviación estándar para cada medición (79 variables extraídas del original 561), y luego se promediaron las mediciones para cada sujeto y actividad. dando como resultado el conjunto de datos final.

##  Creando el conjunto de datos <a name="creating-data-set"> </a>

El script R `run_analysis.R` puede usarse para crear el conjunto de datos. Recupera el conjunto de datos de origen y lo transforma para producir el conjunto de datos final mediante la implementación de los siguientes pasos (consulte el libro de códigos para obtener detalles, así como los comentarios en el propio script):

- Descargar y descomprimir los datos de origen si no existe.
- Leer datos.
- Combinar la formación y los conjuntos de prueba para crear un conjunto de datos.
- Extraiga solo las mediciones de la media y la desviación estándar para cada medición.
- Utilice nombres de actividades descriptivas para nombrar las actividades en el conjunto de datos.
- Etiquetar adecuadamente el conjunto de datos con nombres de variables descriptivos.
- Cree un segundo conjunto ordenado independiente con el promedio de cada variable para cada actividad y cada tema.
- Escribe el conjunto de datos en el archivo `tidy_data.txt` .

El `tidy_data.txt` en este repositorio se creó ejecutando el script` run_analysis.R` usando R versión 3.2.2 (2015-08-14) en la edición de Windows 8.1 de 64 bits.

Este script requiere el paquete `dplyr` (se utilizó la versión 0.4.3).
