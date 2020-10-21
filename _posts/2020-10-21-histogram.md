---
title: What is a histogram?
lang: en
ref: histogram1
category: Data visualization

tags:
  - histogram
  - plots
  - Rayuela
  - Cien años de soledad
  - Julio Cortázar
  - Gabriel García Márquez
---

Once we have gathered data on a topic or question we are interested about, where do we start?

The best way to get to know our data is to represent them graphically. The histogram is a type of plot that shows **how a numerical variable is distributed** over its different values by replying to the question **how many are there in each class?** 

I will use the novels *Rayuela* and *Cien años de soledad* (*One Hundred Years of Solitude*) to illustrate this concept. I will focus on one aspect of the writing style of their authors: the length of sentences.<!--excerpt-->

# The data

I have created a table that contains every sentence of the two novels and their corresponding length[^spacy]. You can check its first rows here:

|Sentence                                                                                                                                                                                                                                                                                                                                                                           | Sent.Length|Work    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------:|:-------|
|¿Encontraría a la Maga?                                                                                                                                                                                                                                                                                                                                                            |           4|Rayuela |
|Tantas veces me había bastado asomarme, viniendo por la rue de Seine, al arco que da al Quai de Conti, y apenas la luz de ceniza y olivo que flota sobre el río me dejaba distinguir las formas, ya su silueta delgada se inscribía en el Pont des Arts, a veces andando de un lado a otro, a veces detenida en el pretil de hierro, inclinada sobre el agua.                      |          69|Rayuela |
|Y era tan natural cruzar la calle, subir los peldaños del puente, entrar en su delgada cintura y acercarme a la Maga que sonreía sin sorpresa, convencida como yo de que un encuentro casual era lo menos casual en nuestras vidas, y que la gente que se da citas precisas es la misma que necesita papel rayado para escribirse o que aprieta desde abajo el tubo de dentífrico. |          68|Rayuela |
|Pero ella no estaría ahora en el puente.                                                                                                                                                                                                                                                                                                                                           |           8|Rayuela |
|Su fina cara de translúcida piel se asomaría a viejos portales en el ghetto del Marais, quizá estuviera charlando con una vendedora de papas fritas o comiendo una salchicha caliente en el boulevard de Sébastopol.                                                                                                                                                               |          35|Rayuela |
|De todas maneras subí hasta el puente, y la Maga no estaba.                                                                                                                                                                                                                                                                                                                        |          12|Rayuela |


# The histogram


The following histogram shows the distribution of *Rayuela*'s sentence lengths[^long_sentences] (column  `Sent.Length`). In the horizontal axis we find the category "number of words in sentence"; the vertical axis (the height of the bars) tells us how many sentences of each length we find in the novel.

![Rayuela's histogram]({{ "assets/img/histogram1/1_en.png" | absolute_url }})


When we're dealing with discrete variables[^discrete_data], as is the case, creating grouped categories can give a clearer --less noisy-- picture of tt distribution of the data. For instance, the next histogram depicts exactly the same data as the previous one, but each bar represents an interval instead of a single length: [0,5), [5,10), [10,15), etcetera[^intervals].

![Rayuela's histogram]({{ "assets/img/histogram1/2_en.png" | absolute_url }})

To describe this plot, we can say that it has a **peak** around category 5-10, and that it is **skewed to the right**.

Now, let us turn to *One Hundred Years of Solitude* and look at the same two plots.

![Cien años de soledad's histogram]({{ "assets/img/histogram1/3_en.png" | absolute_url }})

![Cien años de soledad's histogram]({{ "assets/img/histogram1/4_en.png" | absolute_url }})

In *Rayuela*'s case, sentences cluster around short lengths and most of them have less than 20 words. Although in García Márquez's work the most common category is also 5-10, the peak is not so sharp and longer sentences (20-40) seem very frequent as well.

In order to appreciate the difference better, we could represent both histograms on the same graph. But before that, let us have a closer look at the vertical axes: frequencies are higher for *Rayuela*, simply because it is longer. Histograms like the ones above are called **absolute frequency histograms** and they show the raw number of occurrences.

In order to compare two distributions, it would be better to use a **relative frequency histogram**. This type of histogram shows the proportion of each class, relative to the total number of observations. In a relative frequency histogram, the height of the bars is calculated by dividing the number of observations in a class by the total; in our case, the number of sentences of a given group divided by the total number of sentences for each novel. This means that relative frequency histograms have the exact same shape as their absolute frequency counterparts


![Histogram of Rayuela vs. Cien años de soledad]({{ "assets/img/histogram1/6_en.png" | absolute_url }})

First, notice that the sum of the heights of the bars of these histograms is the same for both novels. Can you see why?[^area].

The relative frequency histogram tells us that, in *Rayuela*, sentences that are from 5 to 20 words long make up about 20% of the text, with shorter sentences being more common. This same percentage is distributed among sentences that are 5 to 40 words long in *Cien años de soledad*, with all lengths being approximately equally frequent.

I think this would translate in a more agile style in the case of the Argentinian author, and a heavier prose in the work of the Colombian. Have you noticed this difference when reading Cortázar and García Márquez?

# In summary...
## What is a histogram?
A histogram is a plot that shows the **distribution** of the data.

## What kind of data can it be used with?
Numerical data, either discrete --number of siblings, number of words-- or continuous --height, temperature. In the case of continuous variables, categories are grouped by default.

## How does it look like?
It's a bar plot with **no space between bars**. A bar plot with space between bars is used with categorical data (that is, non-numerical categories such as colors, countries, types of birds, etcetera.)

![barplot example]({{ "assets/img/histogram1/barplot_en.png" | absolute_url }})

---

[^spacy]: I used the NLP library [Spacy](http://spacy.io){:target="_blank" rel="noopener"} in order to segment the texts in sentences. The code is available [here](working_link).]
[^long_sentences]: I've removed sentences longer than 200 words from both works, since there were extremely few.
[^discrete_data]: Numerical data can be **discrete** or **continuous**. Count data such as the number of children in a family, the number of employees in a company, or the number of bedrooms in a house are examples of discrete data. Height, weight and temperature are examples of continuous data.
[^intervals]: There is a convention in Math regarding parentheses: square brackets `[` are inclusive, round brackets `(`, exclusive. Therefore, [0,5) means [0, 1, 2, 3, 4].
[^area]: Hint: the sum is 1.
