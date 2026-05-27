**Convolutional Neural Networks translation** [[webpage]](https://stanford.edu/~shervine/teaching/cs-230/cheatsheet-convolutional-neural-networks)

<br>


**1. Convolutional Neural Networks cheatsheet**

⟶ Шпаргалка по свёрточным нейронным сетям

<br>


**2. CS 230 - Deep Learning**

⟶ CS 230 — Глубокое обучение

<br>


**3. [Overview, Architecture structure]**

⟶ [Обзор, Структура архитектуры]

<br>


**4. [Types of layer, Convolution, Pooling, Fully connected]**

⟶ [Типы слоёв, Свёрточный, Подвыборки, Полносвязный]

<br>


**5. [Filter hyperparameters, Dimensions, Stride, Padding]**

⟶ [Гиперпараметры фильтра, Размерности, Шаг свёртки, Дополнение]

<br>


**6. [Tuning hyperparameters, Parameter compatibility, Model complexity, Receptive field]**

⟶ [Настройка гиперпараметров, Совместимость параметров, Сложность модели, Рецептивное поле]

<br>


**7. [Activation functions, Rectified Linear Unit, Softmax]**

⟶ [Функции активации, Линейный выпрямитель (ReLU), Softmax]

<br>


**8. [Object detection, Types of models, Detection, Intersection over Union, Non-max suppression, YOLO, R-CNN]**

⟶ [Детекция объектов, Типы моделей, Обнаружение, Пересечение к объединению (IoU), Подавление немаксимумов, YOLO, R-CNN]

<br>


**9. [Face verification/recognition, One shot learning, Siamese network, Triplet loss]**

⟶ [Верификация и распознавание лиц, Однократное обучение, Сиамская сеть, Триплетная функция потерь]

<br>


**10. [Neural style transfer, Activation, Style matrix, Style/content cost function]**

⟶ [Нейронный перенос стиля, Активация, Матрица стиля, Функция стоимости стиля/содержимого]

<br>


**11. [Computational trick architectures, Generative Adversarial Net, ResNet, Inception Network]**

⟶ [Архитектуры с вычислительными приёмами, Генеративно-состязательная сеть (GAN), ResNet, Inception Network]

<br>


**12. Overview**

⟶ Обзор

<br>


**13. Architecture of a traditional CNN ― Convolutional neural networks, also known as CNNs, are a specific type of neural networks that are generally composed of the following layers:**

⟶ Архитектура классической СНС ― Свёрточные нейронные сети (СНС, англ. CNN) — это особый тип нейронных сетей, обычно состоящих из следующих слоёв:

<br>


**14. The convolution layer and the pooling layer can be fine-tuned with respect to hyperparameters that are described in the next sections.**

⟶ Свёрточный слой и слой подвыборки могут быть тонко настроены по отношению к гиперпараметрам, которые описаны в следующих разделах.

<br>


**15. Types of layer**

⟶ Типы слоёв

<br>


**16. Convolution layer (CONV) ― The convolution layer (CONV) uses filters that perform convolution operations as it is scanning the input I with respect to its dimensions. Its hyperparameters include the filter size F and stride S. The resulting output O is called feature map or activation map.**

⟶ Свёрточный слой (CONV) ― Свёрточный слой (CONV) использует фильтры, которые выполняют операции свёртки при сканировании входа I по его размерностям. Его гиперпараметры включают размер фильтра F и шаг свёртки S. Получаемый на выходе результат O называется картой признаков (feature map) или картой активации (activation map).

<br>


**17. Remark: the convolution step can be generalized to the 1D and 3D cases as well.**

⟶ Замечание: операция свёртки может быть обобщена также на одномерный (1D) и трёхмерный (3D) случаи.

<br>


**18. Pooling (POOL) ― The pooling layer (POOL) is a downsampling operation, typically applied after a convolution layer, which does some spatial invariance. In particular, max and average pooling are special kinds of pooling where the maximum and average value is taken, respectively.**

⟶ Слой подвыборки (POOL) ― Слой подвыборки (POOL) — это операция понижения размерности, обычно применяемая после свёрточного слоя и обеспечивающая определённую пространственную инвариантность. В частности, max-pooling и average-pooling — это специальные виды подвыборки, при которых берётся соответственно максимальное и среднее значение.

<br>


**19. [Type, Purpose, Illustration, Comments]**

⟶ [Тип, Назначение, Иллюстрация, Комментарии]

<br>


**20. [Max pooling, Average pooling, Each pooling operation selects the maximum value of the current view, Each pooling operation averages the values of the current view]**

⟶ [Max-pooling (по максимуму), Average-pooling (по среднему), Каждая операция выбирает максимальное значение из текущего окна, Каждая операция усредняет значения в текущем окне]

<br>


**21. [Preserves detected features, Most commonly used, Downsamples feature map, Used in LeNet]**

⟶ [Сохраняет обнаруженные признаки, Наиболее часто используется, Понижает размерность карты признаков, Используется в LeNet]

<br>


**22. Fully Connected (FC) ― The fully connected layer (FC) operates on a flattened input where each input is connected to all neurons. If present, FC layers are usually found towards the end of CNN architectures and can be used to optimize objectives such as class scores.**

⟶ Полносвязный слой (FC) ― Полносвязный слой (FC) работает с развёрнутым в вектор входом, при этом каждый вход соединён со всеми нейронами. Если полносвязные слои присутствуют, то обычно они располагаются в конце архитектуры СНС и могут использоваться для оптимизации таких целевых величин, как оценки классов.

<br>


**23. Filter hyperparameters**

⟶ Гиперпараметры фильтра

<br>


**24. The convolution layer contains filters for which it is important to know the meaning behind its hyperparameters.**

⟶ Свёрточный слой содержит фильтры, для которых важно понимать смысл их гиперпараметров.

<br>


**25. Dimensions of a filter ― A filter of size F×F applied to an input containing C channels is a F×F×C volume that performs convolutions on an input of size I×I×C and produces an output feature map (also called activation map) of size O×O×1.**

⟶ Размерности фильтра ― Фильтр размера F×F, применяемый ко входу с C каналами, представляет собой объём F×F×C, выполняющий свёртки над входом размера I×I×C и порождающий выходную карту признаков (также называемую картой активации) размера O×O×1.

<br>


**26. Filter**

⟶ Фильтр

<br>


**27. Remark: the application of K filters of size F×F results in an output feature map of size O×O×K.**

⟶ Замечание: применение K фильтров размера F×F даёт на выходе карту признаков размера O×O×K.

<br>


**28. Stride ― For a convolutional or a pooling operation, the stride S denotes the number of pixels by which the window moves after each operation.**

⟶ Шаг свёртки ― Для операции свёртки или подвыборки шаг S обозначает количество пикселей, на которое смещается окно после каждой операции.

<br>


**29. Zero-padding ― Zero-padding denotes the process of adding P zeroes to each side of the boundaries of the input. This value can either be manually specified or automatically set through one of the three modes detailed below:**

⟶ Нулевое дополнение (zero-padding) ― Нулевое дополнение обозначает процесс добавления P нулей по каждой стороне границ входа. Это значение можно задать вручную или установить автоматически с помощью одного из трёх режимов, описанных ниже:

<br>


**30. [Mode, Value, Illustration, Purpose, Valid, Same, Full]**

⟶ [Режим, Значение, Иллюстрация, Назначение, Valid, Same, Full]

<br>


**31. [No padding, Drops last convolution if dimensions do not match, Padding such that feature map size has size ⌈IS⌉, Output size is mathematically convenient, Also called 'half' padding, Maximum padding such that end convolutions are applied on the limits of the input, Filter 'sees' the input end-to-end]**

⟶ [Без дополнения, Отбрасывает последнюю свёртку, если размерности не совпадают, Дополнение такое, чтобы размер карты признаков был равен ⌈IS⌉, Размер выхода математически удобный, Также называется «половинным» (half) дополнением, Максимальное дополнение, при котором крайние свёртки применяются на границах входа, Фильтр «видит» вход целиком]

<br>


**32. Tuning hyperparameters**

⟶ Настройка гиперпараметров

<br>


**33. Parameter compatibility in convolution layer ― By noting I the length of the input volume size, F the length of the filter, P the amount of zero padding, S the stride, then the output size O of the feature map along that dimension is given by:**

⟶ Совместимость параметров в свёрточном слое ― Обозначив I как длину входного объёма, F — длину фильтра, P — величину нулевого дополнения, S — шаг свёртки, выходной размер O карты признаков вдоль этой размерности задаётся формулой:

<br>


**34. [Input, Filter, Output]**

⟶ [Вход, Фильтр, Выход]

<br>


**35. Remark: often times, Pstart=Pend≜P, in which case we can replace Pstart+Pend by 2P in the formula above.**

⟶ Замечание: часто Pstart=Pend≜P, в этом случае в формуле выше Pstart+Pend можно заменить на 2P.

<br>


**36. Understanding the complexity of the model ― In order to assess the complexity of a model, it is often useful to determine the number of parameters that its architecture will have. In a given layer of a convolutional neural network, it is done as follows:**

⟶ Понимание сложности модели ― Для оценки сложности модели часто полезно определить количество параметров, которые будет содержать её архитектура. В каждом слое свёрточной нейронной сети это делается следующим образом:

<br>


**37. [Illustration, Input size, Output size, Number of parameters, Remarks]**

⟶ [Иллюстрация, Размер входа, Размер выхода, Количество параметров, Замечания]

<br>


**38. [One bias parameter per filter, In most cases, S<F, A common choice for K is 2C]**

⟶ [Один параметр смещения на каждый фильтр, В большинстве случаев S<F, Часто K выбирают равным 2C]

<br>


**39. [Pooling operation done channel-wise, In most cases, S=F]**

⟶ [Операция подвыборки выполняется поканально, В большинстве случаев S=F]

<br>


**40. [Input is flattened, One bias parameter per neuron, The number of FC neurons is free of structural constraints]**

⟶ [Вход разворачивается в вектор, Один параметр смещения на каждый нейрон, Число нейронов полносвязного слоя не имеет структурных ограничений]

<br>


**41. Receptive field ― The receptive field at layer k is the area denoted Rk×Rk of the input that each pixel of the k-th activation map can 'see'. By calling Fj the filter size of layer j and Si the stride value of layer i and with the convention S0=1, the receptive field at layer k can be computed with the formula:**

⟶ Рецептивное поле ― Рецептивное поле на слое k — это область входа размера Rk×Rk, которую каждый пиксель k-й карты активации может «видеть». Обозначив через Fj размер фильтра слоя j и через Si значение шага свёртки слоя i, а также положив по соглашению S0=1, рецептивное поле на слое k можно вычислить по формуле:

<br>


**42. In the example below, we have F1=F2=3 and S1=S2=1, which gives R2=1+2⋅1+2⋅1=5.**

⟶ В примере ниже F1=F2=3 и S1=S2=1, что даёт R2=1+2⋅1+2⋅1=5.

<br>


**43. Commonly used activation functions**

⟶ Часто используемые функции активации

<br>


**44. Rectified Linear Unit ― The rectified linear unit layer (ReLU) is an activation function g that is used on all elements of the volume. It aims at introducing non-linearities to the network. Its variants are summarized in the table below:**

⟶ Линейный выпрямитель ― Слой линейного выпрямителя (ReLU) — это функция активации g, применяемая ко всем элементам объёма. Её цель — внести нелинейности в сеть. Варианты ReLU приведены в таблице ниже:

<br>


**45. [ReLU, Leaky ReLU, ELU, with]**

⟶ [ReLU, Leaky ReLU, ELU, где]

<br>


**46. [Non-linearity complexities biologically interpretable, Addresses dying ReLU issue for negative values, Differentiable everywhere]**

⟶ [Нелинейные сложности, биологически интерпретируема, Решает проблему «умирания» ReLU при отрицательных значениях, Дифференцируема всюду]

<br>


**47. Softmax ― The softmax step can be seen as a generalized logistic function that takes as input a vector of scores x∈Rn and outputs a vector of output probability p∈Rn through a softmax function at the end of the architecture. It is defined as follows:**

⟶ Softmax ― Шаг softmax можно рассматривать как обобщённую логистическую функцию, которая принимает на вход вектор оценок x∈Rn и через применяемую в конце архитектуры функцию softmax выдаёт вектор выходных вероятностей p∈Rn. Она определяется следующим образом:

<br>


**48. where**

⟶ где

<br>


**49. Object detection**

⟶ Детекция объектов

<br>


**50. Types of models ― There are 3 main types of object recognition algorithms, for which the nature of what is predicted is different. They are described in the table below:**

⟶ Типы моделей ― Существует 3 основных типа алгоритмов распознавания объектов, различающихся тем, что именно они предсказывают. Они описаны в таблице ниже:

<br>


**51. [Image classification, Classification w. localization, Detection]**

⟶ [Классификация изображений, Классификация с локализацией, Детекция]

<br>


**52. [Teddy bear, Book]**

⟶ [Плюшевый мишка, Книга]

<br>


**53. [Classifies a picture, Predicts probability of object, Detects an object in a picture, Predicts probability of object and where it is located, Detects up to several objects in a picture, Predicts probabilities of objects and where they are located]**

⟶ [Классифицирует изображение, Предсказывает вероятность объекта, Обнаруживает объект на изображении, Предсказывает вероятность объекта и его местоположение, Обнаруживает до нескольких объектов на изображении, Предсказывает вероятности объектов и их местоположения]

<br>


**54. [Traditional CNN, Simplified YOLO, R-CNN, YOLO, R-CNN]**

⟶ [Классическая СНС, Упрощённый YOLO, R-CNN, YOLO, R-CNN]

<br>


**55. Detection ― In the context of object detection, different methods are used depending on whether we just want to locate the object or detect a more complex shape in the image. The two main ones are summed up in the table below:**

⟶ Обнаружение ― В контексте детекции объектов используются разные методы в зависимости от того, хотим ли мы просто локализовать объект или обнаружить более сложную форму на изображении. Два основных подхода приведены в таблице ниже:

<br>


**56. [Bounding box detection, Landmark detection]**

⟶ [Детекция ограничивающего прямоугольника, Детекция опорных точек]

<br>


**57. [Detects the part of the image where the object is located, Detects a shape or characteristics of an object (e.g. eyes), More granular]**

⟶ [Обнаруживает часть изображения, где находится объект, Обнаруживает форму или характеристики объекта (например, глаза), Более детальный подход]

<br>


**58. [Box of center (bx,by), height bh and width bw, Reference points (l1x,l1y), ..., (lnx,lny)]**

⟶ [Прямоугольник с центром (bx,by), высотой bh и шириной bw, Опорные точки (l1x,l1y), ..., (lnx,lny)]

<br>


**59. Intersection over Union ― Intersection over Union, also known as IoU, is a function that quantifies how correctly positioned a predicted bounding box Bp is over the actual bounding box Ba. It is defined as:**

⟶ Пересечение к объединению ― Пересечение к объединению (англ. Intersection over Union, IoU) — это функция, количественно оценивающая, насколько корректно расположен предсказанный ограничивающий прямоугольник Bp относительно фактического ограничивающего прямоугольника Ba. Она определяется как:

<br>


**60. Remark: we always have IoU∈[0,1]. By convention, a predicted bounding box Bp is considered as being reasonably good if IoU(Bp,Ba)⩾0.5.**

⟶ Замечание: всегда выполняется IoU∈[0,1]. По соглашению, предсказанный ограничивающий прямоугольник Bp считается достаточно хорошим, если IoU(Bp,Ba)⩾0,5.

<br>


**61. Anchor boxes ― Anchor boxing is a technique used to predict overlapping bounding boxes. In practice, the network is allowed to predict more than one box simultaneously, where each box prediction is constrained to have a given set of geometrical properties. For instance, the first prediction can potentially be a rectangular box of a given form, while the second will be another rectangular box of a different geometrical form.**

⟶ Якорные прямоугольники ― Техника якорных прямоугольников (anchor boxing) применяется для предсказания пересекающихся ограничивающих прямоугольников. На практике сети разрешается предсказывать одновременно несколько прямоугольников, при этом каждое предсказание ограничено заданным набором геометрических свойств. Например, первое предсказание может потенциально быть прямоугольником заданной формы, а второе — прямоугольником другой геометрической формы.

<br>


**62. Non-max suppression ― The non-max suppression technique aims at removing duplicate overlapping bounding boxes of a same object by selecting the most representative ones. After having removed all boxes having a probability prediction lower than 0.6, the following steps are repeated while there are boxes remaining:**

⟶ Подавление немаксимумов ― Техника подавления немаксимумов (non-max suppression) предназначена для устранения дублирующихся пересекающихся ограничивающих прямоугольников одного и того же объекта путём выбора наиболее репрезентативных. После удаления всех прямоугольников с предсказанной вероятностью ниже 0,6 следующие шаги повторяются, пока остаются прямоугольники:

<br>


**63. [For a given class, Step 1: Pick the box with the largest prediction probability., Step 2: Discard any box having an IoU⩾0.5 with the previous box.]**

⟶ [Для заданного класса, Шаг 1: Выбрать прямоугольник с наибольшей предсказанной вероятностью. Шаг 2: Отбросить все прямоугольники, имеющие IoU⩾0,5 с предыдущим прямоугольником.]

<br>


**64. [Box predictions, Box selection of maximum probability, Overlap removal of same class, Final bounding boxes]**

⟶ [Предсказания прямоугольников, Выбор прямоугольника максимальной вероятности, Удаление перекрытий в пределах одного класса, Финальные ограничивающие прямоугольники]

<br>


**65. YOLO ― You Only Look Once (YOLO) is an object detection algorithm that performs the following steps:**

⟶ YOLO ― You Only Look Once (YOLO, «Смотри только один раз») — это алгоритм детекции объектов, выполняющий следующие шаги:

<br>


**66. [Step 1: Divide the input image into a G×G grid., Step 2: For each grid cell, run a CNN that predicts y of the following form:, repeated k times]**

⟶ [Шаг 1: Разделить входное изображение на сетку G×G. Шаг 2: Для каждой ячейки сетки запустить СНС, предсказывающую y следующего вида:, повторяется k раз]

<br>


**67. where pc is the probability of detecting an object, bx,by,bh,bw are the properties of the detected bouding box, c1,...,cp is a one-hot representation of which of the p classes were detected, and k is the number of anchor boxes.**

⟶ где pc — вероятность обнаружения объекта, bx, by, bh, bw — свойства обнаруженного ограничивающего прямоугольника, c1, ..., cp — one-hot представление того, какой из p классов был обнаружен, а k — количество якорных прямоугольников.

<br>


**68. Step 3: Run the non-max suppression algorithm to remove any potential duplicate overlapping bounding boxes.**

⟶ Шаг 3: Запустить алгоритм подавления немаксимумов для удаления возможных дублирующихся пересекающихся ограничивающих прямоугольников.

<br>


**69. [Original image, Division in GxG grid, Bounding box prediction, Non-max suppression]**

⟶ [Исходное изображение, Разбиение на сетку G×G, Предсказание ограничивающих прямоугольников, Подавление немаксимумов]

<br>


**70. Remark: when pc=0, then the network does not detect any object. In that case, the corresponding predictions bx,...,cp have to be ignored.**

⟶ Замечание: когда pc=0, сеть не обнаруживает ни одного объекта. В этом случае соответствующие предсказания bx, ..., cp следует игнорировать.

<br>


**71. R-CNN ― Region with Convolutional Neural Networks (R-CNN) is an object detection algorithm that first segments the image to find potential relevant bounding boxes and then run the detection algorithm to find most probable objects in those bounding boxes.**

⟶ R-CNN ― Region with Convolutional Neural Networks (R-CNN, «Свёрточные нейронные сети по областям») — это алгоритм детекции объектов, который сначала сегментирует изображение, чтобы найти потенциально релевантные ограничивающие прямоугольники, а затем запускает алгоритм детекции для поиска наиболее вероятных объектов в этих прямоугольниках.

<br>


**72. [Original image, Segmentation, Bounding box prediction, Non-max suppression]**

⟶ [Исходное изображение, Сегментация, Предсказание ограничивающих прямоугольников, Подавление немаксимумов]

<br>


**73. Remark: although the original algorithm is computationally expensive and slow, newer architectures enabled the algorithm to run faster, such as Fast R-CNN and Faster R-CNN.**

⟶ Замечание: хотя исходный алгоритм является вычислительно затратным и медленным, более новые архитектуры позволили алгоритму работать быстрее — например, Fast R-CNN и Faster R-CNN.

<br>


**74. Face verification and recognition**

⟶ Верификация и распознавание лиц

<br>


**75. Types of models ― Two main types of model are summed up in table below:**

⟶ Типы моделей ― Два основных типа моделей приведены в таблице ниже:

<br>


**76. [Face verification, Face recognition, Query, Reference, Database]**

⟶ [Верификация лица, Распознавание лица, Запрос, Эталон, База данных]

<br>


**77. [Is this the correct person?, One-to-one lookup, Is this one of the K persons in the database?, One-to-many lookup]**

⟶ [Это правильный человек?, Поиск «один к одному», Это один из K человек в базе данных?, Поиск «один ко многим»]

<br>


**78. One Shot Learning ― One Shot Learning is a face verification algorithm that uses a limited training set to learn a similarity function that quantifies how different two given images are. The similarity function applied to two images is often noted d(image 1,image 2).**

⟶ Однократное обучение (One Shot Learning) ― Однократное обучение — это алгоритм верификации лиц, использующий ограниченную обучающую выборку для построения функции сходства, количественно оценивающей, насколько различаются два заданных изображения. Функция сходства, применяемая к двум изображениям, часто обозначается d(image 1, image 2).

<br>


**79. Siamese Network ― Siamese Networks aim at learning how to encode images to then quantify how different two images are. For a given input image x(i), the encoded output is often noted as f(x(i)).**

⟶ Сиамская сеть ― Сиамские сети предназначены для обучения кодированию изображений с последующей количественной оценкой того, насколько различаются два изображения. Для заданного входного изображения x(i) закодированный выход часто обозначается f(x(i)).

<br>


**80. Triplet loss ― The triplet loss ℓ is a loss function computed on the embedding representation of a triplet of images A (anchor), P (positive) and N (negative). The anchor and the positive example belong to a same class, while the negative example to another one. By calling α∈R+ the margin parameter, this loss is defined as follows:**

⟶ Триплетная функция потерь ― Триплетная функция потерь ℓ — это функция потерь, вычисляемая на векторных представлениях (эмбеддингах) триплета изображений A (anchor — якорь), P (positive — позитивный) и N (negative — негативный). Якорь и позитивный пример принадлежат одному классу, тогда как негативный пример — другому. Обозначив через α∈R+ параметр отступа (margin), эта функция потерь определяется следующим образом:

<br>


**81. Neural style transfer**

⟶ Нейронный перенос стиля

<br>


**82. Motivation ― The goal of neural style transfer is to generate an image G based on a given content C and a given style S.**

⟶ Мотивация ― Цель нейронного переноса стиля — сгенерировать изображение G на основе заданного содержимого C и заданного стиля S.

<br>


**83. [Content C, Style S, Generated image G]**

⟶ [Содержимое C, Стиль S, Сгенерированное изображение G]

<br>


**84. Activation ― In a given layer l, the activation is noted a[l] and is of dimensions nH×nw×nc**

⟶ Активация ― В заданном слое l активация обозначается a[l] и имеет размерности nH×nw×nc

<br>


**85. Content cost function ― The content cost function Jcontent(C,G) is used to determine how the generated image G differs from the original content image C. It is defined as follows:**

⟶ Функция стоимости содержимого ― Функция стоимости содержимого Jcontent(C,G) используется для определения того, насколько сгенерированное изображение G отличается от исходного изображения-содержимого C. Она определяется следующим образом:

<br>


**86. Style matrix ― The style matrix G[l] of a given layer l is a Gram matrix where each of its elements G[l]kk′ quantifies how correlated the channels k and k′ are. It is defined with respect to activations a[l] as follows:**

⟶ Матрица стиля ― Матрица стиля G[l] заданного слоя l — это матрица Грама, каждый элемент G[l]kk′ которой количественно оценивает, насколько коррелированы каналы k и k′. Она определяется по отношению к активациям a[l] следующим образом:

<br>


**87. Remark: the style matrix for the style image and the generated image are noted G[l] (S) and G[l] (G) respectively.**

⟶ Замечание: матрицы стиля для изображения-стиля и сгенерированного изображения обозначаются соответственно G[l] (S) и G[l] (G).

<br>


**88. Style cost function ― The style cost function Jstyle(S,G) is used to determine how the generated image G differs from the style S. It is defined as follows:**

⟶ Функция стоимости стиля ― Функция стоимости стиля Jstyle(S,G) используется для определения того, насколько сгенерированное изображение G отличается от стиля S. Она определяется следующим образом:

<br>


**89. Overall cost function ― The overall cost function is defined as being a combination of the content and style cost functions, weighted by parameters α,β, as follows:**

⟶ Общая функция стоимости ― Общая функция стоимости определяется как комбинация функций стоимости содержимого и стиля, взвешенных параметрами α и β, следующим образом:

<br>


**90. Remark: a higher value of α will make the model care more about the content while a higher value of β will make it care more about the style.**

⟶ Замечание: большее значение α заставит модель больше внимания уделять содержимому, тогда как большее значение β заставит её больше внимания уделять стилю.

<br>


**91. Architectures using computational tricks**

⟶ Архитектуры с вычислительными приёмами

<br>


**92. Generative Adversarial Network ― Generative adversarial networks, also known as GANs, are composed of a generative and a discriminative model, where the generative model aims at generating the most truthful output that will be fed into the discriminative which aims at differentiating the generated and true image.**

⟶ Генеративно-состязательная сеть ― Генеративно-состязательные сети (англ. Generative Adversarial Network, GAN) состоят из генеративной и дискриминативной моделей, где генеративная модель стремится сгенерировать максимально правдоподобный выход, который подаётся в дискриминативную модель, призванную отличать сгенерированное изображение от настоящего.

<br>


**93. [Training, Noise, Real-world image, Generator, Discriminator, Real Fake]**

⟶ [Обучение, Шум, Реальное изображение, Генератор, Дискриминатор, Настоящее / Поддельное]

<br>


**94. Remark: use cases using variants of GANs include text to image, music generation and synthesis.**

⟶ Замечание: примеры применения вариантов GAN включают генерацию изображений по тексту, генерацию музыки и синтез.

<br>


**95. ResNet ― The Residual Network architecture (also called ResNet) uses residual blocks with a high number of layers meant to decrease the training error. The residual block has the following characterizing equation:**

⟶ ResNet ― Архитектура остаточной сети (англ. Residual Network, ResNet) использует остаточные блоки с большим количеством слоёв, предназначенные для уменьшения ошибки обучения. Остаточный блок задаётся следующим характеризующим уравнением:

<br>


**96. Inception Network ― This architecture uses inception modules and aims at giving a try at different convolutions in order to increase its performance through features diversification. In particular, it uses the 1×1 convolution trick to limit the computational burden.**

⟶ Inception Network ― Эта архитектура использует inception-модули и преследует цель опробовать различные свёртки, чтобы повысить качество за счёт диверсификации признаков. В частности, она использует приём свёртки 1×1 для ограничения вычислительной нагрузки.

<br>


**97. The Deep Learning cheatsheets are now available in [target language].**

⟶ Шпаргалки по глубокому обучению теперь доступны на русском языке.

<br>


**98. Original authors**

⟶ Оригинальные авторы

<br>


**99. Translated by X, Y and Z**

⟶ Перевод: Виктор Зайцев

<br>


**100. Reviewed by X, Y and Z**

⟶ Проверка: ―

<br>


**101. View PDF version on GitHub**

⟶ Просмотреть PDF-версию на GitHub

<br>


**102. By X and Y**

⟶ Авторы: Afshine Amidi и Shervine Amidi
