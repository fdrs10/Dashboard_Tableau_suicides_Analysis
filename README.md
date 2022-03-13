# Dashboard_Tableau_suicides_Analysis
<!-- You have some errors, warnings, or alerts. If you are using reckless mode, turn it off to see inline alerts.
* ERRORs: 0
* WARNINGs: 0
* ALERTS: 19 -->

<h2>Práctica: Suicidios, sus causas objetivas</h2>


<h3>La conexión a la fuente de datos</h3>


La conexión a la fuente de datos fue realizada desde Tableau Prep.

Primero conseguí los dos dataset principales, uno del repositorio kaggle sobre los datos de suicidios relacionados con la renta, el índice de desarrollo humano y los países (algunos de ellos). El otro dataset tardé mucho en conseguir, pues quería buscar uno que proporcionara datos de horas de luz anuales medias por país.

El que conseguí proporcionaba un rango de horas por país y por continente, venía en formato Excel y no tenía todos los países, pero tenía los continentes. Tuve que crear tres agrupaciones, para sacar la media de mínimas, máximas y medias de horas al año de insolación. Las uní mediante una operación de _Inner Join_ entre ellas.

Estaba buscando poder ver la influencia de las horas de luz en los suicidios, pues siempre he creído que debe influir la luz solar en tu estado anímico y por ende en los suicidios.

Posteriormente hice un_ Inner Join_  con el dataset de suicidios de kaggle y conseguí el dataset que integraba los suicidios por país con la distribución por continentes y las horas de luz por país al año. Esta ha sido el dataset que ha servido para elaborar el dashboard.







<h2>Dashboard: objetivos, gráficos y filtros.</h2>


He querido mostrar que el número de suicidios entre mujeres y hombres son muy diferentes, siendo el género un aspecto fundamental en cuanto no sólo la cantidad de suicidios sino a cómo le afectan los agentes externos y los cambios, dado que las curvas de tendencia de unos y otros muestran claras divergencias. Mientras en los hombres claramente tienen derivadas acusadas en las mujeres son casi planas, de forma que hasta podría parecer que los casos de suicidios son casi una proporción fija.

Igualmente es interesante ver cómo esa comparación por género se hace mucho más acusada en unos continentes respecto a otros, dándose el caso por ejemplo de tener 4,65 veces más suicidios en hombres que en mujeres en Sudamérica, 3,82 en África, 4.47 en Europa, 4,9 en Norteamérica, y 2,56 en Asia, algo que merece un análisis más exhaustivo.




En principio este análisis entre continentes no deja de ser un intento, dado que los valores del dataset no eran demasiados y por ejemplo en áfrica únicamente hay un país, con lo que realmente no es representativo. No obstante, sí se aprecian diferencias entre otros continentes aunque sea en cómo se comportan las tendencias de ambos géneros. Podemos resaltar que mientras en Europa, Norteamérica, Asia y Oceanía los suicidios tienen una tendencia negativa, disminuyendo, en el caso de Sudamérica los suicidios incrementan año a año.





En el gráfico de suicidios por franja de edad y género es muy interesante ver cómo los suicidios en el caso de las mujeres se mantienen en tasas estables a partir de la adolescencia, mientras que en el caso de los hombres el comportamiento es absolutamente diferente, destacando que  a partir de los 75 años la tasa de suicidios se dispara hasta valores  que pueden ser hasta 8 veces más que las mujeres en Sudamérica y Norteamérica, mientras que en el caso de así, se reduce poco más de 2 veces más. Volvemos a encontrarnos con tendencias diferentes entre continentes.

Este filtro se aplica igualmente a continente y a país, si bien este debe ser seleccionado en el gráfico de suicidios frente a insolación.





Este filtro se aplica igualmente a continente y a país, si bien este debe ser seleccionado en el gráfico de suicidios frente a insolación. Se ve como en Asia el comportamiento entre géneros es mucho menos acusado que en otras regiones.




Además, en este filtro, al escoger en la leyenda o hombres o mujeres se resalta el escogido en el gráfico y en la leyenda.

El gráfico de valores de suicidios frente a insolación es muy relevante, pues pretende demostrar la idea de que a mayor insolación se favorecen menos los casos de suicidio. Efectivamente y en el caso de Europa con los datos se puede observar de forma más clara. Me ayudo de otro gráfico en el que represento una modelización mediante clúster que recoge la idea y geográficamente muestra que los países con mayor insolación, que son lo de color amarillo, presentan tasas de suicidio menores.





También es posible al posicionarse en las opciones de leyenda del clúster que se puedan resaltar cada uno de los clústeres.

Sobre este mismo asunto, el gráfico de barras ya tiene un detalle mayor, pues permite seleccionar por país y que en el resto de gráficos que tengan datos se muestren los valores ya de ese país, entrando al detalle más allá de lo que supone el continente.

Es un gráfico muy importante, pues integra el orden de países en función de las horas de luz y así ordenados y al mismo tiempo el valor de la tasa de suicidios por cada 100 habitantes.

Pensé en limitarlo a varios valores para evitar poner el scroll, pero es que sólo aparece en el caso de Europa, que es el continente con más datos. No me interesaba quitarlo de Europa ya que aparecen un dato curioso que quería resaltar, y es que partir de la media de horas de luz que tiene Europa ya no se dan los suicidios en tasas altas. Este efecto lo conseguí demostrar cambiando los clores de las barras en función de los suicidios y calculando la línea media y representándola.

Es curioso igualmente que dentro del grupo de países con menos horas de luz que la media, hay toda una serie de países donde los datos de suicidios están mal altos y otros que no, aun cuando la tasa de luz es gradualmente menor y esto yo quería que quedase patente. Yo creo que aparentemente podría deberse a causas diferentes, que no están en el dataset que estoy usando, pero la densidad de los núcleos urbanos, el nivel de desarrollo y de comunicaciones debe estar influyendo.





La leyenda del gráfico va cambiando por continente y por países si éste es seleccionado, con lo que se aprecia los valores máximo y mínimo de suicidios. Dato curioso el de mínimo, ya que establece una especie de línea base de suicidios que sí o sí se van a producir. 

El último gráfico, y no por ello menos importante, nos muestra cómo influye el índice de desarrollo humano en los suicidios. Para ello he vuelto a recurrir al clúster, para sí demostrar cómo influye  en los  suicidios. 

Con los datos del datset no permite sacar conclusiones claras, al menos de forma única, si bien, lo que sí se puede decir es que los valores más altos de suicidios se dan en valores altos de HDI y no necesariamente, al contrario. Esto debería poder analizar con datos de cómo viven las personas que se han suicidado, en qué tipo de ciudades, cómo se distribuyen esas ciudades, si en altura o en superficie, si hay buenas comunicaciones, qué densidad de población tienen las ciudades. Sólo de esta forma podremos acercarnos al análisis para responder a ese paradigma.





<h3>Dashboard</h3>


He colocado varios combos de filtros, que actúan sobre todos los gráficos con datos, para que siempre se puedan analizar los diferentes factores

