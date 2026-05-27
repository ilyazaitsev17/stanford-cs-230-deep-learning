**Recurrent Neural Networks translation** [[webpage]](https://stanford.edu/~shervine/teaching/cs-230/cheatsheet-recurrent-neural-networks)

<br>


**1. Recurrent Neural Networks cheatsheet**

⟶ Шпаргалка по рекуррентным нейронным сетям

<br>


**2. CS 230 - Deep Learning**

⟶ CS 230 — Глубокое обучение

<br>


**3. [Overview, Architecture structure, Applications of RNNs, Loss function, Backpropagation]**

⟶ [Обзор, Структура архитектуры, Применение РНС, Функция потерь, Обратное распространение ошибки]

<br>


**4. [Handling long term dependencies, Common activation functions, Vanishing/exploding gradient, Gradient clipping, GRU/LSTM, Types of gates, Bidirectional RNN, Deep RNN]**

⟶ [Работа с долгосрочными зависимостями, Часто используемые функции активации, Затухающий/взрывной градиент, Отсечение градиента, GRU/LSTM, Типы гейтов, Двунаправленные РНС, Глубокие РНС]

<br>


**5. [Learning word representation, Notations, Embedding matrix, Word2vec, Skip-gram, Negative sampling, GloVe]**

⟶ [Обучение векторного представления слов, Обозначения, Матрица эмбеддингов, Word2vec, Skip-gram, Негативное сэмплирование, GloVe]

<br>


**6. [Comparing words, Cosine similarity, t-SNE]**

⟶ [Сравнение слов, Косинусное сходство, t-SNE]

<br>


**7. [Language model, n-gram, Perplexity]**

⟶ [Языковая модель, n-грамма, Перплексия]

<br>


**8. [Machine translation, Beam search, Length normalization, Error analysis, Bleu score]**

⟶ [Машинный перевод, Лучевой поиск, Нормализация длины, Анализ ошибок, Метрика BLEU]

<br>


**9. [Attention, Attention model, Attention weights]**

⟶ [Внимание, Модель внимания, Веса внимания]

<br>


**10. Overview**

⟶ Обзор

<br>


**11. Architecture of a traditional RNN ― Recurrent neural networks, also known as RNNs, are a class of neural networks that allow previous outputs to be used as inputs while having hidden states. They are typically as follows:**

⟶ Архитектура классической РНС ― Рекуррентные нейронные сети (РНС, англ. RNN) — это класс нейронных сетей, в которых предыдущие выходы могут использоваться в качестве входов при наличии скрытых состояний. Обычно они имеют следующий вид:

<br>


**12. For each timestep t, the activation a and the output y are expressed as follows:**

⟶ Для каждого момента времени t активация a и выход y выражаются следующим образом:

<br>


**13. and**

⟶ и

<br>


**14. where Wax,Waa,Wya,ba,by are coefficients that are shared temporally and g1,g2 activation functions.**

⟶ где Wax, Waa, Wya, ba, by — коэффициенты, общие для всех временных шагов, а g1, g2 — функции активации.

<br>


**15. The pros and cons of a typical RNN architecture are summed up in the table below:**

⟶ Достоинства и недостатки типичной архитектуры РНС приведены в таблице ниже:

<br>


**16. [Advantages, Possibility of processing input of any length, Model size not increasing with size of input, Computation takes into account historical information, Weights are shared across time]**

⟶ [Достоинства, Возможность обработки входа любой длины, Размер модели не растёт с увеличением размера входа, Вычисления учитывают историческую информацию, Веса общие для всех временных шагов]

<br>


**17. [Drawbacks, Computation being slow, Difficulty of accessing information from a long time ago, Cannot consider any future input for the current state]**

⟶ [Недостатки, Медленные вычисления, Сложность доступа к давней информации, Невозможность учитывать будущие входы для текущего состояния]

<br>


**18. Applications of RNNs ― RNN models are mostly used in the fields of natural language processing and speech recognition. The different applications are summed up in the table below:**

⟶ Применение РНС ― Модели РНС в основном используются в области обработки естественного языка и распознавания речи. Различные применения приведены в таблице ниже:

<br>


**19. [Type of RNN, Illustration, Example]**

⟶ [Тип РНС, Иллюстрация, Пример]

<br>


**20. [One-to-one, One-to-many, Many-to-one, Many-to-many]**

⟶ [Один-к-одному, Один-ко-многим, Многие-к-одному, Многие-ко-многим]

<br>


**21. [Traditional neural network, Music generation, Sentiment classification, Name entity recognition, Machine translation]**

⟶ [Классическая нейронная сеть, Генерация музыки, Классификация тональности, Распознавание именованных сущностей, Машинный перевод]

<br>


**22. Loss function ― In the case of a recurrent neural network, the loss function L of all time steps is defined based on the loss at every time step as follows:**

⟶ Функция потерь ― В случае рекуррентной нейронной сети функция потерь L по всем временным шагам определяется на основе потерь на каждом временном шаге следующим образом:

<br>


**23. Backpropagation through time ― Backpropagation is done at each point in time. At timestep T, the derivative of the loss L with respect to weight matrix W is expressed as follows:**

⟶ Обратное распространение ошибки во времени (BPTT) ― Обратное распространение производится в каждый момент времени. На временном шаге T производная функции потерь L по матрице весов W выражается следующим образом:

<br>


**24. Handling long term dependencies**

⟶ Работа с долгосрочными зависимостями

<br>


**25. Commonly used activation functions ― The most common activation functions used in RNN modules are described below:**

⟶ Часто используемые функции активации ― Наиболее распространённые функции активации, применяемые в модулях РНС, описаны ниже:

<br>


**26. [Sigmoid, Tanh, RELU]**

⟶ [Сигмоида, Гиперболический тангенс, ReLU]

<br>


**27. Vanishing/exploding gradient ― The vanishing and exploding gradient phenomena are often encountered in the context of RNNs. The reason why they happen is that it is difficult to capture long term dependencies because of multiplicative gradient that can be exponentially decreasing/increasing with respect to the number of layers.**

⟶ Затухающий/взрывной градиент ― Явления затухающего и взрывного градиента часто встречаются в контексте РНС. Причина их возникновения в том, что сложно уловить долгосрочные зависимости из-за мультипликативного градиента, который может экспоненциально уменьшаться или возрастать в зависимости от числа слоёв.

<br>


**28. Gradient clipping ― It is a technique used to cope with the exploding gradient problem sometimes encountered when performing backpropagation. By capping the maximum value for the gradient, this phenomenon is controlled in practice.**

⟶ Отсечение градиента ― Это приём, используемый для борьбы с проблемой взрывного градиента, которая иногда возникает при обратном распространении ошибки. Путём ограничения максимального значения градиента это явление контролируется на практике.

<br>


**29. clipped**

⟶ отсечённый

<br>


**30. Types of gates ― In order to remedy the vanishing gradient problem, specific gates are used in some types of RNNs and usually have a well-defined purpose. They are usually noted Γ and are equal to:**

⟶ Типы гейтов ― Для решения проблемы затухающего градиента в некоторых типах РНС используются специальные гейты, каждый из которых имеет чётко определённое назначение. Обычно они обозначаются Γ и равны:

<br>


**31. where W,U,b are coefficients specific to the gate and σ is the sigmoid function. The main ones are summed up in the table below:**

⟶ где W, U, b — коэффициенты, специфичные для данного гейта, а σ — сигмоидная функция. Основные гейты приведены в таблице ниже:

<br>


**32. [Type of gate, Role, Used in]**

⟶ [Тип гейта, Роль, Используется в]

<br>


**33. [Update gate, Relevance gate, Forget gate, Output gate]**

⟶ [Гейт обновления, Гейт релевантности, Гейт забывания, Выходной гейт]

<br>


**34. [How much past should matter now?, Drop previous information?, Erase a cell or not?, How much to reveal of a cell?]**

⟶ [Насколько важно прошлое сейчас?, Отбросить предыдущую информацию?, Стирать ячейку или нет?, Насколько раскрыть содержимое ячейки?]

<br>


**35. [LSTM, GRU]**

⟶ [LSTM, GRU]

<br>


**36. GRU/LSTM ― Gated Recurrent Unit (GRU) and Long Short-Term Memory units (LSTM) deal with the vanishing gradient problem encountered by traditional RNNs, with LSTM being a generalization of GRU. Below is a table summing up the characterizing equations of each architecture:**

⟶ GRU/LSTM ― Управляемые рекуррентные блоки (GRU, англ. Gated Recurrent Unit) и блоки долгой краткосрочной памяти (LSTM, англ. Long Short-Term Memory) решают проблему затухающего градиента, с которой сталкиваются классические РНС, причём LSTM является обобщением GRU. В таблице ниже приведены характеризующие уравнения для каждой архитектуры:

<br>


**37. [Characterization, Gated Recurrent Unit (GRU), Long Short-Term Memory (LSTM), Dependencies]**

⟶ [Характеризация, Управляемый рекуррентный блок (GRU), Долгая краткосрочная память (LSTM), Зависимости]

<br>


**38. Remark: the sign ⋆ denotes the element-wise multiplication between two vectors.**

⟶ Замечание: знак ⋆ обозначает поэлементное умножение двух векторов.

<br>


**39. Variants of RNNs ― The table below sums up the other commonly used RNN architectures:**

⟶ Варианты РНС ― В таблице ниже приведены другие часто используемые архитектуры РНС:

<br>


**40. [Bidirectional (BRNN), Deep (DRNN)]**

⟶ [Двунаправленная (BRNN), Глубокая (DRNN)]

<br>


**41. Learning word representation**

⟶ Обучение векторного представления слов

<br>


**42. In this section, we note V the vocabulary and |V| its size.**

⟶ В этом разделе V обозначает словарь, а |V| — его размер.

<br>


**43. Motivation and notations**

⟶ Мотивация и обозначения

<br>


**44. Representation techniques ― The two main ways of representing words are summed up in the table below:**

⟶ Способы представления ― Два основных способа представления слов приведены в таблице ниже:

<br>


**45. [1-hot representation, Word embedding]**

⟶ [One-hot представление, Векторное представление слов (эмбеддинг)]

<br>


**46. [teddy bear, book, soft]**

⟶ [плюшевый мишка, книга, мягкий]

<br>


**47. [Noted ow, Naive approach, no similarity information, Noted ew, Takes into account words similarity]**

⟶ [Обозначается ow, Наивный подход, не содержит информации о сходстве, Обозначается ew, Учитывает сходство слов]

<br>


**48. Embedding matrix ― For a given word w, the embedding matrix E is a matrix that maps its 1-hot representation ow to its embedding ew as follows:**

⟶ Матрица эмбеддингов ― Для заданного слова w матрица эмбеддингов E — это матрица, которая отображает его one-hot представление ow в его эмбеддинг ew следующим образом:

<br>


**49. Remark: learning the embedding matrix can be done using target/context likelihood models.**

⟶ Замечание: обучение матрицы эмбеддингов может выполняться с помощью моделей правдоподобия «целевое слово / контекст».

<br>


**50. Word embeddings**

⟶ Векторные представления слов

<br>


**51. Word2vec ― Word2vec is a framework aimed at learning word embeddings by estimating the likelihood that a given word is surrounded by other words. Popular models include skip-gram, negative sampling and CBOW.**

⟶ Word2vec ― Word2vec — это фреймворк, предназначенный для обучения векторных представлений слов путём оценки правдоподобия того, что данное слово окружено другими словами. Популярные модели включают skip-gram, негативное сэмплирование и CBOW.

<br>


**52. [A cute teddy bear is reading, teddy bear, soft, Persian poetry, art]**

⟶ [Милый плюшевый мишка читает, плюшевый мишка, мягкий, персидская поэзия, искусство]

<br>


**53. [Train network on proxy task, Extract high-level representation, Compute word embeddings]**

⟶ [Обучить сеть на вспомогательной задаче, Извлечь высокоуровневое представление, Вычислить векторные представления слов]

<br>


**54. Skip-gram ― The skip-gram word2vec model is a supervised learning task that learns word embeddings by assessing the likelihood of any given target word t happening with a context word c. By noting θt a parameter associated with t, the probability P(t|c) is given by:**

⟶ Skip-gram ― Модель skip-gram word2vec — это задача обучения с учителем, в которой векторные представления слов обучаются путём оценки правдоподобия того, что произвольное целевое слово t встречается с контекстным словом c. Обозначив через θt параметр, связанный с t, вероятность P(t|c) выражается так:

<br>


**55. Remark: summing over the whole vocabulary in the denominator of the softmax part makes this model computationally expensive. CBOW is another word2vec model using the surrounding words to predict a given word.**

⟶ Замечание: суммирование по всему словарю в знаменателе softmax делает эту модель вычислительно затратной. CBOW ― другая модель word2vec, использующая окружающие слова для предсказания заданного слова.

<br>


**56. Negative sampling ― It is a set of binary classifiers using logistic regressions that aim at assessing how a given context and a given target words are likely to appear simultaneously, with the models being trained on sets of k negative examples and 1 positive example. Given a context word c and a target word t, the prediction is expressed by:**

⟶ Негативное сэмплирование ― Это набор бинарных классификаторов на основе логистической регрессии, предназначенных для оценки того, насколько вероятно одновременное появление заданного контекстного слова и заданного целевого слова. Модели обучаются на наборах из k негативных примеров и 1 позитивного примера. Для контекстного слова c и целевого слова t предсказание выражается так:

<br>


**57. Remark: this method is less computationally expensive than the skip-gram model.**

⟶ Замечание: этот метод менее вычислительно затратен, чем модель skip-gram.

<br>


**57bis. GloVe ― The GloVe model, short for global vectors for word representation, is a word embedding technique that uses a co-occurence matrix X where each Xi,j denotes the number of times that a target i occurred with a context j. Its cost function J is as follows:**

⟶ GloVe ― Модель GloVe (от англ. Global Vectors for word representation — глобальные векторы для представления слов) — это техника векторного представления слов, использующая матрицу совместной встречаемости X, где каждый элемент Xi,j обозначает число раз, которое целевое слово i встретилось с контекстом j. Её функция стоимости J имеет следующий вид:

<br>


**58. where f is a weighting function such that Xi,j=0⟹f(Xi,j)=0.
Given the symmetry that e and θ play in this model, the final word embedding e(final)w is given by:**

⟶ где f — весовая функция, такая что Xi,j=0 ⟹ f(Xi,j)=0.
Учитывая симметричность ролей e и θ в этой модели, итоговое векторное представление слова e(final)w задаётся следующим образом:

<br>


**59. Remark: the individual components of the learned word embeddings are not necessarily interpretable.**

⟶ Замечание: отдельные компоненты обученных векторных представлений слов не обязательно интерпретируемы.

<br>


**60. Comparing words**

⟶ Сравнение слов

<br>


**61. Cosine similarity ― The cosine similarity between words w1 and w2 is expressed as follows:**

⟶ Косинусное сходство ― Косинусное сходство между словами w1 и w2 выражается следующим образом:

<br>


**62. Remark: θ is the angle between words w1 and w2.**

⟶ Замечание: θ — это угол между словами w1 и w2.

<br>


**63. t-SNE ― t-SNE (t-distributed Stochastic Neighbor Embedding) is a technique aimed at reducing high-dimensional embeddings into a lower dimensional space. In practice, it is commonly used to visualize word vectors in the 2D space.**

⟶ t-SNE ― t-SNE (от англ. t-distributed Stochastic Neighbor Embedding — стохастическое вложение соседей с t-распределением) — это техника, предназначенная для понижения размерности эмбеддингов высокой размерности до пространства меньшей размерности. На практике часто используется для визуализации векторов слов в двумерном пространстве.

<br>


**64. [literature, art, book, culture, poem, reading, knowledge, entertaining, loveable, childhood, kind, teddy bear, soft, hug, cute, adorable]**

⟶ [литература, искусство, книга, культура, стихотворение, чтение, знание, развлекательный, любимый, детство, добрый, плюшевый мишка, мягкий, объятие, милый, очаровательный]

<br>


**65. Language model**

⟶ Языковая модель

<br>


**66. Overview ― A language model aims at estimating the probability of a sentence P(y).**

⟶ Обзор ― Языковая модель предназначена для оценки вероятности предложения P(y).

<br>


**67. n-gram model ― This model is a naive approach aiming at quantifying the probability that an expression appears in a corpus by counting its number of appearance in the training data.**

⟶ Модель n-грамм ― Эта модель представляет собой наивный подход к количественной оценке вероятности появления выражения в корпусе путём подсчёта числа его появлений в обучающих данных.

<br>


**68. Perplexity ― Language models are commonly assessed using the perplexity metric, also known as PP, which can be interpreted as the inverse probability of the dataset normalized by the number of words T. The perplexity is such that the lower, the better and is defined as follows:**

⟶ Перплексия ― Языковые модели обычно оцениваются с помощью метрики перплексии, также известной как PP, которая может быть интерпретирована как обратная вероятность набора данных, нормализованная по числу слов T. Чем ниже перплексия, тем лучше модель. Она определяется следующим образом:

<br>


**69. Remark: PP is commonly used in t-SNE.**

⟶ Замечание: PP часто используется в t-SNE.

<br>


**70. Machine translation**

⟶ Машинный перевод

<br>


**71. Overview ― A machine translation model is similar to a language model except it has an encoder network placed before. For this reason, it is sometimes referred as a conditional language model. The goal is to find a sentence y such that:**

⟶ Обзор ― Модель машинного перевода похожа на языковую модель, за исключением того, что перед ней располагается сеть-кодировщик. По этой причине её иногда называют условной языковой моделью. Цель — найти такое предложение y, что:

<br>


**72. Beam search ― It is a heuristic search algorithm used in machine translation and speech recognition to find the likeliest sentence y given an input x.**

⟶ Лучевой поиск ― Это эвристический алгоритм поиска, используемый в машинном переводе и распознавании речи для нахождения наиболее вероятного предложения y при заданном входе x.

<br>


**73. [Step 1: Find top B likely words y<1>, Step 2: Compute conditional probabilities y|x,y<1>,...,y<k−1>, Step 3: Keep top B combinations x,y<1>,...,y, End process at a stop word]**

⟶ [Шаг 1: Найти B наиболее вероятных слов y<1>, Шаг 2: Вычислить условные вероятности y|x,y<1>,...,y<k−1>, Шаг 3: Сохранить B наиболее вероятных комбинаций x,y<1>,...,y, Завершить процесс на стоп-слове]

<br>


**74. Remark: if the beam width is set to 1, then this is equivalent to a naive greedy search.**

⟶ Замечание: если ширина луча равна 1, то это эквивалентно наивному жадному поиску.

<br>


**75. Beam width ― The beam width B is a parameter for beam search. Large values of B yield to better result but with slower performance and increased memory. Small values of B lead to worse results but is less computationally intensive. A standard value for B is around 10.**

⟶ Ширина луча ― Ширина луча B — это параметр лучевого поиска. Большие значения B дают лучшие результаты, но снижают скорость и увеличивают потребление памяти. Малые значения B приводят к худшим результатам, но требуют меньше вычислений. Стандартное значение B — около 10.

<br>


**76. Length normalization ― In order to improve numerical stability, beam search is usually applied on the following normalized objective, often called the normalized log-likelihood objective, defined as:**

⟶ Нормализация длины ― Для улучшения численной устойчивости лучевой поиск обычно применяется к следующему нормализованному целевому функционалу, часто называемому нормализованным функционалом логарифмического правдоподобия и определяемому как:

<br>


**77. Remark: the parameter α can be seen as a softener, and its value is usually between 0.5 and 1.**

⟶ Замечание: параметр α можно рассматривать как смягчающий коэффициент, и его значение обычно находится в диапазоне от 0,5 до 1.

<br>


**78. Error analysis ― When obtaining a predicted translation ˆy that is bad, one can wonder why we did not get a good translation y∗ by performing the following error analysis:**

⟶ Анализ ошибок ― При получении плохого предсказанного перевода ˆy можно задаться вопросом, почему не был получен хороший перевод y∗, выполнив следующий анализ ошибок:

<br>


**79. [Case, Root cause, Remedies]**

⟶ [Случай, Первопричина, Способы устранения]

<br>


**80. [Beam search faulty, RNN faulty, Increase beam width, Try different architecture, Regularize, Get more data]**

⟶ [Ошибка лучевого поиска, Ошибка РНС, Увеличить ширину луча, Попробовать другую архитектуру, Применить регуляризацию, Получить больше данных]

<br>


**81. Bleu score ― The bilingual evaluation understudy (bleu) score quantifies how good a machine translation is by computing a similarity score based on n-gram precision. It is defined as follows:**

⟶ Метрика BLEU ― Метрика BLEU (от англ. Bilingual Evaluation Understudy) количественно оценивает качество машинного перевода путём вычисления оценки сходства на основе точности по n-граммам. Она определяется следующим образом:

<br>


**82. where pn is the bleu score on n-gram only defined as follows:**

⟶ где pn — оценка BLEU только по n-граммам, определяемая следующим образом:

<br>


**83. Remark: a brevity penalty may be applied to short predicted translations to prevent an artificially inflated bleu score.**

⟶ Замечание: к коротким предсказанным переводам может применяться штраф за краткость, чтобы предотвратить искусственное завышение значения BLEU.

<br>


**84. Attention**

⟶ Внимание

<br>


**85. Attention model ― This model allows an RNN to pay attention to specific parts of the input that is considered as being important, which improves the performance of the resulting model in practice. By noting α<t,t′> the amount of attention that the output y should pay to the activation a<t′> and c the context at time t, we have:**

⟶ Модель внимания ― Эта модель позволяет РНС обращать внимание на определённые части входа, которые считаются важными, что на практике улучшает качество получаемой модели. Обозначив через α<t,t′> величину внимания, которое выход y должен уделить активации a<t′>, и через c контекст в момент времени t, получаем:

<br>


**86. with**

⟶ при

<br>


**87. Remark: the attention scores are commonly used in image captioning and machine translation.**

⟶ Замечание: оценки внимания часто используются в задачах генерации подписей к изображениям и машинного перевода.

<br>


**88. A cute teddy bear is reading Persian literature.**

⟶ Милый плюшевый мишка читает персидскую литературу.

<br>


**89. Attention weight ― The amount of attention that the output y should pay to the activation a<t′> is given by α<t,t′> computed as follows:**

⟶ Вес внимания ― Величина внимания, которую выход y должен уделить активации a<t′>, задаётся α<t,t′> и вычисляется следующим образом:

<br>


**90. Remark: computation complexity is quadratic with respect to Tx.**

⟶ Замечание: вычислительная сложность квадратична относительно Tx.

<br>


**91. The Deep Learning cheatsheets are now available in [target language].**

⟶ Шпаргалки по глубокому обучению теперь доступны на русском языке.

<br>


**92. Original authors**

⟶ Оригинальные авторы

<br>


**93. Translated by X, Y and Z**

⟶ Перевод: Виктор Зайцев

<br>


**94. Reviewed by X, Y and Z**

⟶ Проверка: ―

<br>


**95. View PDF version on GitHub**

⟶ Просмотреть PDF-версию на GitHub

<br>


**96. By X and Y**

⟶ Авторы: Afshine Amidi и Shervine Amidi
