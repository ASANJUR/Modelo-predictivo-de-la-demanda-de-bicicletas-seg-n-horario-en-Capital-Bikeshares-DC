# Modelo-predictivo-de-la-demanda-de-bicicletas-seg-n-horario-en-Capital-Bikeshares-DC
Documentación de proyecto final de materia modelos predictivos, presentando un análisis predictivo horario del comportamiento del sistema de bicicletas compartidas

## Introducción
<p align="justify">Capital Bikeshares es un sistema de renta de bicicletas en la ciudad de Washingtong D.C. inaugurada el 20 de septiembre del 2010 cuenta con al menos 700 estaciones y 5400 unidades disponibles para renta, es el segundo sistema más grande de renta de bicicletas de Estados Unidos.</p>
  
<p align="justify">Este sistema está orientado en ser una alternativa que reduzca la huella de carbono, interesado principalmente en reinventar la movilidad de los usuarios en grandes ciudades; es una realidad que el congestionamiento tráfico diario dificulta la movilidad en horas pico bajo ciertas condiciones, sin embargo, Capital Bikeshares DC en respuesta recurre a las bicicletas como la principal herramienta de transporte.</p>

<p align="justify">La tecnología actual permite facilitar la logística de un sistema con cientos de estaciones y miles de unidades con el fin de crear una red que abarque una gran área metropolitana; la principal característica de este sistema radica en su practicidad, el usuario puede llegar de un punto a otro sin necesidad de retornar la unidad a un punto de origen, esta flexibilidad lo hace altamente atractivo para uso casual ya que comparado a otros sistemas de transporte colectivo la transacción se hace prácticamente inmediata sin tiempo de espera u horarios.</p>

<p align="justify">Cada usuario puede comprar una membresía de 24 horas o 72 horas, esto le permite retirar una bicicleta de cualquier estación realizar un viaje de ida y devolverla a cualquier otra estación, en un periodo máximo de 30 minutos, al excederse de este tiempo se cobra la diferencia.</p>

<p align="justify">Los sistemas GPS permiten la trazabilidad de las unidades a lo largo de la ciudad, proporcionan la ubicación, hora de inicio del viaje, hora de finalización y junto con información del día de la semana e información histórica de las condiciones climáticas se procede con un estudio de las principales razones que influyen en el uso del sistema, al igual que proyecta información suficiente para pronosticar la demanda horaria del sistema.</p>


## Definición del problema
<p align="justify">De acuerdo con el funcionamiento de la red de bicicletas compartidas, un usuario puede iniciar su viaje en una estación particular y finalizar en otra en un radio cercano y permanecerá ahí hasta que otro usuario la utilice y finalice su viaje en otro nodo o regrese al punto de inicio, esto implica que durante horas pico del día algunas estaciones se verán saturadas en bicicletas mientras que otras pueden presentar escasez.</p>
  
<p align="justify">Es necesario poder predecir el volumen del uso de las bicicletas en horas pico para evitar que usuarios con membresías experimenten cuellos de botella frente el auge de la popularidad del sistema de bicicletas compartidas ante el público como medio de transporte diario alternativo.</p>
 
<p align="justify">La disponibilidad de las bicicletas está fuertemente ligada a su nivel de batería, es decir en hora pico la bicicleta puede cumplir un solo ciclo de 30 minutos y no estará disponible hasta que su carga esté nuevamente al 100% esto impacta directamente el inventario y el mantenimiento de los equipos con el fin de rotar las unidades en lotes que estén con suficiente carga.</p>

## Antecedentes
<p align="justify">El sistema de bicicletas compartidas no es una novedad reciente, inicialmente la ciudad de Ámsterdam en el año 1964 contaba con bicicletas gratuitas que se encontraban distribuidas por la ciudad, este programa llevó a que en un mes las 10 bicicletas de la red fueran robadas o dañadas.</p>

<p align="justify">En agosto del 2008 el distrito de Columbia se convirtió en la primera ciudad en lanzar un sistema de bicicletas compartidas, Smart Bike DC contaba con 10 estaciones y 120 bicicletas, en los primeros 2 años de operación al menos 1600 personas se inscribieron en el programa (capital bikeshares, 2025).</p>
  
<p align="justify">Para el año 2022 otros países han implementado este modelo de negocio, al menos 1590 ciudades en 92 países ampliamente popular en los continentes de Europa y Asia (The Meddin Bike-sharing World Map Report, 2022).</p>

<p align="justify">Tomando como referencia el artículo científico “Un enfoque de análisis predictivo para pronosticar la demanda de alquiler de bicicletas”,  se analiza la correlación de las variables entre las cuales destacan una correlación moderada de la cantidad de bicicletas alquiladas con la temperatura y seguido con una correlación moderada baja la hora del día, estudiando a detalle las variables también el autor destaca que existe una disminución en el conteo para días de vacaciones, feriados y domingos (Karunanithi, Chatasawapreeda, & Ali Khan, 2024).</p>
  
<p align="justify">Los datos utilizados en este estudio fueron encontrados en el repositorio de datos de Kaggle como Rental Bike Sharing Dataset, corresponden a un total de 17379 registros representativos a 2 años (2011-2012) desde la implementación del proyecto en la ciudad de Washington (Fanaee-T & Gama, 2013).</p>
  
<p align="justify">Los datos muestran la cantidad de rentas de totales, por usuarios casuales y por usuarios que son miembros y se sabe tienen correlación con las condiciones climáticas como humedad, temperatura y velocidad del viento a diferentes horas por día.</p>

## Justificación
<p align="justify">Es necesario conocer los patrones de comportamiento del sistema a lo largo del día y a lo largo de las semanas, se busca identificar los factores más influyentes en el incremento del volumen de rotación del inventario, es decir describir si el uso de las bicicletas se orienta a la recreación casual o al transporte diario, de igual manera agrega valor poder agrupar las principales horas de movimiento en bloques diarios que puedan hacer más practico el estudio, con esto se espera seleccionar un modelo predictivo que arrojen proyecciones del incremento del volumen de unidades que pueden estar simultáneamente viajando de una estación a otra para evitar escasez de inventario en momentos de alta demanda, la unidades de la flota cuentan con un factor de seguridad que contemple el tiempo que la unidad esté en uso y el tiempo que tarda en recargar.</p>
  
<p align="justify">Cabe destacar que la base de datos utilizada no cuenta con un nivel de granularidad que identifique los niveles de inventario de estaciones específicas en instantes durante el día por lo tanto el presente estudio se limitará principalmente en analizar el volumen bruto de la red y la influencia de los días de la semana, temporadas y diferentes horas del día.</p>
