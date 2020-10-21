---
title: ¿Qué es un histograma?
lang: es
ref: histogram1
category: Visualización de datos
tags:
  - histograma
  - Rayuela
  - Cien años de soledad
  - Julio Cortázar
  - Gabriel García Márquez
---

Una vez hemos obtenido datos sobre algún tema o pregunta que nos interesa, ¿por dónde empezamos a analizarlos?

La mejor forma de familiarizarnos con nuestros datos es representarlos gráficamente. El **histograma**, tema de esta entrada, es un tipo de gráfico que nos permite observar **cómo se distribuye** una variable, ya que responde a la pregunta **¿cuántos hay de cada clase?**

Vamos a utilizar las novelas *Rayuela* y *Cien años de soledad* para ilustrar este concepto. Analizaremos un aspecto del estilo de sus autores: la longitud de sus frases.<!--excerpt-->

# Los datos

He recopilado en una tabla todas las oraciones de cada una de estas novelas y he registrado su longitud[^spacy]. He aquí las primeras filas de la tabla: 

|Sentence                                                                                                                                                                                                                                                                                                                                                                           | Sent.Length|Work    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------:|:-------|
|¿Encontraría a la Maga?                                                                                                                                                                                                                                                                                                                                                            |           4|Rayuela |
|Tantas veces me había bastado asomarme, viniendo por la rue de Seine, al arco que da al Quai de Conti, y apenas la luz de ceniza y olivo que flota sobre el río me dejaba distinguir las formas, ya su silueta delgada se inscribía en el Pont des Arts, a veces andando de un lado a otro, a veces detenida en el pretil de hierro, inclinada sobre el agua.                      |          69|Rayuela |
|Y era tan natural cruzar la calle, subir los peldaños del puente, entrar en su delgada cintura y acercarme a la Maga que sonreía sin sorpresa, convencida como yo de que un encuentro casual era lo menos casual en nuestras vidas, y que la gente que se da citas precisas es la misma que necesita papel rayado para escribirse o que aprieta desde abajo el tubo de dentífrico. |          68|Rayuela |
|Pero ella no estaría ahora en el puente.                                                                                                                                                                                                                                                                                                                                           |           8|Rayuela |
|Su fina cara de translúcida piel se asomaría a viejos portales en el ghetto del Marais, quizá estuviera charlando con una vendedora de papas fritas o comiendo una salchicha caliente en el boulevard de Sébastopol.                                                                                                                                                               |          35|Rayuela |
|De todas maneras subí hasta el puente, y la Maga no estaba.                                                                                                                                                                                                                                                                                                                        |          12|Rayuela |


# El histograma

El siguiente histograma muestra la distribución de la longitud de las oraciones en Rayuela[^oraciones_largas] (la columna `Sent.Length`). En el eje horizontal (el eje de abcisas) encontramos la categoría «número de palabras de la oración», mientras que el eje de ordeandas (la altura de cada barra) nos indica cuántas oraciones de cada longitud encontramos en la novela.

![histograma de Rayuela]({{ "assets/img/histogram1/1_es.png" | absolute_url }})


Para variables discretas[^datos_discretos], como en este caso, suele convenir conviene crear categorías agrupadas para hacerse una mejor idea de la distribución de los datos. Así, el siguiente histograma representa lo mismo que el anterior, pero cada barra corresponde a un intervalo de longitudes: [0,5), [5,10), [10,15), etcétera[^intervalos].

![histograma de Rayuela]({{ "assets/img/histogram1/2_es.png" | absolute_url }})

Podemos describir este gráfico explicando que tiene un **pico** en torno a la categoría 5-10, con una **cola** a la derecha.

Veamos ahora el caso de *Cien años de soledad* con los mismos diagramas.

![histograma de Cien años de soledad]({{ "assets/img/histogram1/3_es.png" | absolute_url }})

![histograma de Cien años de soledad]({{ "assets/img/histogram1/4_es.png" | absolute_url }})

En el caso de *Rayuela*, las oraciones están muy concentradas en torno a longitudes cortas, la gran mayoría con menos de 20 palabras. Sin embargo, aunque en la obra de García Márquez la categoría más frecuente también es 5-10, el pico no es tan agudo y vemos que las oraciones en el rango 20-40 palabras también son muy frecuentes.

Para observar mejor la diferencia, podemos representar ambos histogramas juntos. Pero antes, fijémonos bien en el eje vertical de ambos gráficos. Las frecuencias en *Rayuela* son mayores, simplemente porque la novela es más larga. Los histogramas como los de arriba se denominan **de frecuencias absolutas** y muestran el número de ocurrencias sin ninguna transformación.

Para comparar las dos distribuciones de interés, es mejor que utilicemos un histograma **de frecuencias relativas** que nos muestre la proporción de cada clase con relación al total de observaciones. En un histograma de frecuencias relativas, la altura de la barra se obtiene dividiendo el número de observaciones de cada clase por el total; en este caso, el número de oraciones de cierta longitud dividido entre el número total de oraciones de cada novela. Esto significa que los histogramas de frecuencias relativas tienen exactamente la misma forma que los de frecuencias absolutas.

![histograma de Rayuela frente a Cien años de soledad]({{ "assets/img/histogram1/6_es.png" | absolute_url }})


En primer lugar, debemos saber que la suma de las alturas de las barras de estos histogramas es la misma para *Rayuela* y para *Cien años*. ¿Puedes ver por qué?[^area]

En *Rayuela*, las oraciones de entre 5 y 20 palabras constituyen aproximadamente el 20% del total, y las oraciones más cortas son las más abundantes. En cambio, este mismo porcentaje en *Cien años de soledad* se distribuye entre 5 y 40 palabras, y todas las longitudes son aproximadamente igual de frecuentes. 

Me parece que esto se traduciría en una estilo más fluido para el autor argentino, y una prosa más pesada para el colombiano. ¿Se percibe esta diferencia al leer a Cortázar y a García Márquez?

# En resumen...
## ¿Qué es un histograma?
Un histograma es un gráfico que permite visualizar la **distribución** de los datos.

## ¿Con qué tipos de datos se utiliza?
Con datos **numéricos**, tanto discretos --número de hermanos, número de palabras-- o continuos --altura, temperatura--. Si trabajamos con variables continuas, las categorías son agrupadas por defecto.

## ¿Qué forma tiene?
Diagrama de barras **sin espacio entre las barras**. Un diagrama de barras con espacio entre las barras se usa para datos categóricos (es decir, para categorías no numéricas como colores, países, tipos de pájaros, etc.)

![ejemplo de diagrama de barras]({{ "assets/img/histogram1/barplot_es.png" | absolute_url }})

---

[^spacy]: Para segmentar los textos en oraciones he usado la biblioteca de NLP [Spacy](http://spacy.io){:target="_blank" rel="noopener"}. El código está disponible en: xxx.]
[^oraciones_largas]: He eliminado las oraciones de más de 200 palabras de ambas novelas, ya que eran muy escasas.
[^datos_discretos]: Los datos numéricos pueden ser **discretos** o **continuos**. El número de hijos de una familia, el número de empleados de una empresa o el número de habitaciones de una casa son ejemplos de datos discretos. La altura, el peso o la temperatura son ejemplos de datos continuos.
[^intervalos]: En matemáticas existe una convención respecto a los paréntesis: los paréntesis cuadrados `[` son inclusivos, y los redondos `(`, exclusivos. Así, [0,5) quiere decir [0, 1, 2, 3, 4].
[^area]: Pista: la suma de las alturas de las barras debe ser 1.
