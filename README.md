# Конспект книги Николенко "Глубокое обучение"

[Николенко С.И. на wikipedia](https://ru.wikipedia.org/wiki/Николенко,_Сергей_Игоревич "Николенко Сергей Игоревич")

## Часть I. Как обучать нейронные сети

### Глава 1. От биологии к информатике, *или We need to go deeper*

> Первая глава — вводная. В ней мы:

- узнаем, что в машинном обучении недавно произошла революция и
революция эта все еще длится;
- вспомним историю искусственного интеллекта как науки;
- познакомимся с разными задачами машинного обучения, узнаем, как они
связаны и чем отличаются друг от друга;
- выясним, почему человеческий мозг может служить образцом для подражания
при создании искусственного интеллекта;
- придем к выводу, что нейробиология пока не слишком точная наука;
- закончим кратким обзором самых ярких примеров применения современных
нейронных сетей и областей, где им еще есть чему поучиться.

#### 1.1. Революция обучения глубоких сетей

> В 2005–2006 годах группы исследователей под руководством
> Джеффри Хинтона (Geoffrey Hinton) в университете Торонто и Йошуа Бенджи (Yoshua Bengio)
> в университете Монреаля научились обучать глубокие нейронные сети.

> Решение, предложенное группой Хинтона в середине 2000-х годов, пришло
> в виде предобучения без учителя, когда сеть сначала обучается на большом наборе
> данных без разметки, а потом уже дообучается на размеченных данных, используя
> это приближение. Например, если мы хотим распознавать человеческие лица, то
> давайте сначала пообучаем нейронную сеть на фотографиях с людьми вообще, без
> разметки (таких фотографий можно легко набрать сколь угодно много), а уже
> потом, когда сеть «насмотрится» на неразмеченные фотографии, дообучим ее на
> имеющемся размеченном наборе данных. Оказалось, что при этом конечный результат
> становится намного лучше, а хорошие и интересные признаки сеть начинает
> выделять еще на этапе предобучения без учителя.

#### 1.2. Искусственный интеллект и машинное обучение

> во второй половине 1950-х и начале 1960-х годов, появились и
> самообучающиеся машины, в частности перцептрон Розенблатта

> 1970-е годы стали временем расцвета систем, основанных на знаниях
> (knowledge-based systems), которые до сих пор являются важной частью науки
> об экспертных системах. Суть здесь состоит в том, чтобы накопить достаточно
> большой набор правил и знаний о предметной области, а затем делать выводы.
> Одним из самых ярких примеров таких проектов стала система MYCIN, посвященная
> идентификации бактерий, вызывающих серьезные инфекции, а затем рекомендующая
> антибиотики [65, 494]. В ней было около 600 правил, и ее результаты (она
> выдавала подходящий метод лечения в 69% случаев) были не хуже, чем у опытных
> врачей, и существенно лучше, чем у начинающих. Более того, такие системы
> могли объяснить, как именно они пришли к тому или иному решению, и оценить
> свою уверенность в этой гипотезе. Позднее они стали прообразами графических
> вероятностных моделей.

> Затем исследователи снова вспомнили о нейронных сетях: к началу 1980-х
> годов был разработан алгоритм обратного распространения ошибки (его мы
> подробно обсудим в главе 2), что открыло дорогу самым разнообразным архитектурам.
> Одним из ключевых понятий 1980-х годов был коннекционизм (connectionism):
> пришедшая из когнитивных наук идея о том, что нужно не пытаться задавать
> аксиоматические формальные системы для последующих рассуждений в них, а
> строить большие ансамбли параллельно работающих нейронов, которые, подобно
> человеческому мозгу, как-нибудь сами разберутся, что им делать. К концу
> восьмидесятых уже появилась бо􀀀льшая часть основных архитектур, о которых мы будем
> говорить в этой книге: сверточные сети, автокодировщики, рекуррентные сети...

> Поэтому вторая волна увлечения
> искусственным интеллектом закончилась в начале девяностых, когда многие
> компании не смогли оправдать завышенных ожиданий и лопнули.

> В 1990-е годы основной акцент сместился на машинное обучение и поиск
> закономерностей в данных, причем нейронные сети, как мы уже упоминали выше, не
> считались особенно перспективными. Зато самих данных, особенно с развитием
> Интернета, становилось все больше, компьютеры становились все быстрее. В
> итоге в середине 2000-х годов очередная новая идея наконец-то сработала, к ней
> быстро подтянулись другие

#### 1.3. Немного о словах: каким бывает машинное обучение

> что такое, собственно, машинное обучение (machine learning).
> Интуитивно понятно, что «обучение» — это когда некая модель каким-то образом
> «обучается», а потом начинает выдавать результаты, то есть, скорее всего, что-то
> предсказывать. Можно даже дать очень общее определение «обучаемости»,
> примерно такое, какое дает Томас Митчелл в классической книге «Машинное
> обучение» [368]: «Компьютерная программа обучается по мере накопления опыта
> относительно некоторого класса задач T и целевой функции P, если качество решения
> этих задач (относительно P) улучшается с получением нового опыта».

> Хотя это определение звучит чрезвычайно обобщенно и абстрактно, оно на
> самом деле позволяет прояснить некоторые важные моменты. Например,
> центральное место в нем занимают не данные (хотя они тоже есть), а целевая функция.
> Когда вы начинаете решать любую практическую задачу, крайне важно еще «на
> берегу» определить целевую функцию, договориться о том, как вы будете
> оценивать результаты. Выбор целевой функции полностью определяет всю дальнейшую
> работу, и даже в похожих задачах разные целевые функции могут привести к
> совершенно разным моделям. Например, было бы здорово «научить компьютер
> читать», но сначала нужно определить, что это, собственно, значит. Уметь правильно
> отвечать на вопросы по «прочитанному» тексту? Сделать синтаксический разбор
> предложения? Показать самые релевантные данному тексту статьи «Википедии»?
> Разные ответы приводят к разным моделям и направлениям исследований.

> Два основных класса задач машинного обучения — это задачи обучения
> с учителем (supervised learning) и обучения без учителя (unsupervised learning).

> При обучении с учителем на вход подается набор тренировочных примеров,
> который обычно называют обучающим или тренировочным набором данных (training
> set или training sample — тренировочная выборка), и задача состоит в том, чтобы
> продолжить уже известные ответы на новый опыт, выраженный обычно в виде
> тестового набора данных (test set, test sample). Основное предположение здесь в том,
> что данные, доступные для обучения, будут чем-то похожи на данные, на которых
> потом придется применять обученную модель, иначе никакое обобщение будет
> невозможно. Для «чтения» текста пример обучения с учителем — это обучение
> модели, которая строит деревья синтаксического разбора предложений (какие слова
> от каких зависят) по набору деревьев, построенных людьми для конкретных
> предложений. Предположение здесь в том, что деревья разбора строятся по одним и тем
> же законам, и модель, обученную на некотором наборе деревьев разбора, можно
> будет применить и к новым предложениям, не входящим в обучающий набор. Если
> это предположение нарушится, модель работать не будет. Например, если
> лингвисты размечали предложения на английском языке, а потом применили обученную
> модель к немецкому, где буквы примерно те же, но синтаксис совершенно другой,
> ожидать от модели разумного поведения не стоит.

> Задачи обучения с учителем обычно делятся на задачи классификации и
> регрессии. В задаче классификации нужно поданный на вход объект определить в один из
> (обычно конечного числа) классов, например, разделить фотографии животных на
> кошек, собак, лошадей и «все остальное»; или по фотографии человеческого лица
> понять, кто из ваших друзей в социальной сети на ней изображен. Если
> продолжать пример с языком, то типичная задача классификации — это разметка слов
> по частям речи. А в задаче регрессии нужно предсказать значение некоей
> функции, у которой обычно может быть бесконечно много разных значений. Например,
> по росту человека предсказать его вес, сделать прогноз завтрашней погоды,
> предсказать цену акции или, скажем, выделить на фотографии прямоугольник, в
> котором находится человеческое лицо — сделать это необходимо, чтобы затем эти
> прямоугольники подать на вход упомянутому выше классификатору.

> Деление на регрессию и классификацию, конечно, очень условно, можно
> легко придумать «промежуточные» примеры (тот же разбор предложения — к какому
> классу отнести задачу «построить дерево»?). Но обычно ясно, какую задачу мы
> решаем, и это деление имеет содержательный смысл: меняются целевые функции
> и, как следствие, процесс обучения. А есть и откровенно иные виды задач, не
> укладывающиеся в эту несложную классификацию. Например, в поисковых и
> рекомендательных системах часто встречается задача обучения ранжирования (learning to
> rank). Она ставится так: по имеющимся данным (в поисковой системе это будут
> тексты документов и прошлое поведение пользователей) отранжировать,
> расставить имеющиеся объекты в порядке убывания целевой функции (в поисковой
> системе она называется релевантностью: насколько данный документ подходит,
> что-бы выдать его в ответ на данный запрос). Эта задача чем-то похожа на задачу
> регрессии — нам так или иначе нужно предсказывать непрерывную целевую
> функцию, ту самую релевантность. Но при этом значений самой функции в данных
> совсем нет, да они нам и не важны. Имеют значение только результаты сравнения
> этой функции на разных объектах (какой документ будет выше другого в
> поисковой выдаче). Это приводит к ряду интересных и специфических методов обучения.

> Типичнейший пример задачи обучения без
> учителя — это кластеризация (clustering): нужно разбить данные на заранее
> неизвестные классы по некоторой мере похожести так, чтобы точки, отнесенные к
> одному и тому же кластеру, были как можно ближе друг к другу, как можно более
> похожи, а точки из разных кластеров были бы как можно дальше друг от друга, как
> можно менее похожи. Например, решив задачу кластеризации, можно выделить
> семейства генов из последовательностей нуклеотидов, или кластеризовать
> пользователей вашего веб-сайта и персонализовать его под каждый кластер, или
> сегментировать медицинский снимок, чтобы легко было понять, где же там опухоль.

> Еще одна часто встречающаяся задача обучения без учителя — это снижение
> размерности (dimensionality reduction), когда входные данные имеют большую
> размерность (например, если у вас на входе разбитый на слова текст, размерность
> будет исчисляться десятками тысяч, а если фотографии — миллионами), а задача
> состоит в том, чтобы построить представление данных меньшей размерности,
> которое тем не менее будет достаточно полно отражать исходные данные. То есть,
> например, по представлению меньшей размерности можно будет достаточно
> успешно реконструировать исходные точки большой размерности. Это можно
> рассматривать как частный случай общей задачи выделения признаков (feature extraction),
> и мы будем подробно говорить об этом на протяжении всей книги, а особенно в
> разделе 5.5, где речь пойдет об автокодировщиках.

> И наконец, третий и самый общий класс задач обучения без учителя —
> задача оценки плотности: нам даны точки данных {x1;...;xN} и, возможно, какие-то
> априорные представления о том, откуда взялись эти точки, а хочется оценить
> распределение p(x), из которого они получились. Это очень общая постановка задачи,
> к ней можно многое свести, и нейронные сети тоже отчасти ее и решают.

> Нередко в жизни возникает нечто среднее между обучением с учителем и
> обучением без учителя. Так обычно получается тогда, когда неразмеченные примеры
> найти очень легко, а размеченные получить сложно. Например, во все том же
> примере с синтаксическим разбором набрать сколько угодно неразмеченных текстов
> не представляет никакой сложности, а вот вручную нарисовать даже одно дерево
> нелегко. Или, скажем, задумайтесь о том, что такое «размеченные данные» для
> распознавания речи. Просто установить соответствие между звуковым файлом с
> речью и текстом, особенно если тексты достаточно длинные, здесь может быть
> недостаточно. По-настоящему размеченные данные для распознавания — это звуковые
> файлы, в которых вручную отмечены (или хотя бы проверены) границы каждой
> фонемы, каждого звука человеческой речи. Это адский труд, обычно делегируемый
> младшим научным сотрудникам, но даже целая армия лингвистов-фонологов
> будет двигаться достаточно медленно. А неразмеченных звуков живой человеческой
> речи вы можете записать сколько угодно, просто включив диктофон на запись.
> Такую ситуацию иногда называют обучением с частичным привлечением учителя,
> или полуконтролируемым обучением (английский термин semi-supervised learning
> устоялся куда больше), и с ней мы тоже не раз столкнемся в этой книге.

>В главе 9 мы с вами встретимся с другой постановкой задачи — обучением с
>подкреплением (reinforcement learning), когда агент, находясь в некоей среде,
> производит те или иные действия и получает за это награды. Цель агента — получить как
> можно большую награду с течением времени, а для этого неплохо бы понять, какие
> действия в конечном счете ведут к успеху. Так можно обучиться играть в разные
> игры или, например, сделать отличный протокол для A/B-тестирования.

#### 1.4. Особенности человеческого мозга

> ... важное замечание про работу человеческого
> мозга: мы распознаем лицо человека за пару сотен миллисекунд. А частота
> импульсов в аксонах бывает от 10 Гц в неактивном состоянии до примерно 200 Гц во
> время самой сильной активации. Это значит, что связи между отдельными нейронами
> активируются минимум за десятки миллисекунд, и в полном цикле распознавания
> человеческого лица не может быть последовательной цепочки активаций длиннее,
> чем буквально несколько нейронов; скорее всего, меньше десятка!

> То есть мозг, с одной стороны, содержит огромное число нейронов и еще больше
> связей между ними, но с другой — устроен очень плоско по сравнению с обычным
> процессором. Процессор в компьютере исполняет длинные последовательные
> цепочки команд, обрабатывая их в синхронном режиме, а у мозга цепочки короткие,
> зато работает он асинхронно (стохастически) и с очень высокой степенью
> параллелизации: нейроны активируются сразу во многих местах мозга, когда начинают
> распознавать лицо и делать много других увлекательных вещей. Можно сказать,
> что с этой точки зрения мозг больше похож на видеокарту, чем на процессор ...

> Основная идея искусственных нейронных сетей — собрать сеть из простых
> нейронов, активирующихся или не активирующихся в зависимости от
> снабженных поддающимися тренировке весами, — действительно позаимствована у
> природы. Однако дальше путь развития искусственного интеллекта отошел от
> природы; настоящие нейроны устроены значительно сложнее, чем те модели, которые
> мы будем обсуждать в этой книге.

#### 1.5. Пределы нейробиологии: что мы на самом деле знаем?

> В своей недавней яркой работе «Может ли нейробиолог понять микропроцессор?» [263] 
> (Кстати говоря, название статьи – отсылка к уже ставшей классической статье Юрия
> Лазебника «Может ли биолог починить радиоприемник» [299], перепечатанной в начале 2000-х годов тремя
> разными журналами, включая Cell. В этой статье Лазебник пытается проанализировать сломанный
> радиоприемник «Океан» методами биологических наук со столь же неутешительными выводами.)
> Эрик Джонас и Конрад Кординг пытаются проследить, насколько
> бы получилось у методов современной нейробиологии проанализировать
> какой-нибудь очень простой «мозг» на примере процессора MOS 6502. Такие процессоры
> устанавливались в Apple I и Atari VCS

> Для анализа Джонас и Кординг использовали классические методы, которыми
> нейробиология изучает настоящий человеческий мозг. Например, они специально
> симулировали повреждения отдельных транзисторов, чтобы узнать, за что они
> «отвечают». В рамках MOS 6502 они могли позволить себе попробовать повредить
> буквально каждый транзистор по отдельности. И действительно, они сумели
> выделить отдельные подмножества транзисторов, которые были необходимы для
> запуска каждой из трех рассмотренных игр (Space Invaders, Donkey Kong и Pitfall);
> без такого транзистора одна игра не запускалась, а две другие работали
> нормально. Можно было бы предположить, что эти транзисторы являются ключевыми для
> именно этого конкретного «поведения»... Вот только на самом деле не было ничего
> подобного: большинство этих транзисторов на самом деле реализовывали простые
> функции, например сложение, и чисто случайно именно эта часть реализации
> оказывалась нужна лишь в одной игре. Конечно, если бы исследователи заранее знали,
> что эта часть «мозга» реализует сложение, и затем начали повреждать отдельные
> транзисторы, смысла в этом было бы больше. Но ведь в реальной нейробиологии
> мы тоже совершенно не умеем изолировать настолько простые, базовые функции.

> Да и сами глубокие сети, о которых мы будем говорить в этой книге, не
> перестают удивлять исследователей. Хотя в данном случае люди сами
> запрограммировали этот «мыслительный аппарат» и твердо знают, как работает каждый
> конкретный «нейрон» сети, есть работы, посвященные буквально изучению свойств
> глубоких нейронных сетей, как будто они были бы природным объектом, данным
> нам для изучения (собственно, они таковым и являются, с той лишь разницей, что
> все же представляют собой математическую абстракцию). Например, в широко
> известной работе [249] рассказано, как можно обмануть сети, распознающие
> изображения (даже такие простые изображения, как черно-белые рукописные цифры),
> с помощью микроизменений, не влияющих на человеческое восприятие. Обученная
> глубокая сеть здесь выступает как «черный ящик», интересные свойства которого
> мы пытаемся понять.

#### 1.6. Блеск и нищета современных нейронных сетей

> Первым значительным индустриальным приложением современных глубоких
> нейронных сетей, которое подтвердило, что революция глубокого обучения
> действительно начинает необратимо менять ландшафт машинного обучения, да и
> вообще мира вокруг нас, стали успехи в распознавании речи. Структура
> полноценного распознавателя речи выглядит так:
> 1) сначала звуковой сигнал преобразуется в признаки специального вида;
> 2) затем эти признаки превращаются в гипотезы, которые предлагают варианты
> конкретных фонем для каждого окна в звуковом сигнале;
> 3) потом гипотезы о фонемах объединяются в гипотезы относительно
> произнесенных слов, и в выборе между ними уже участвует не только обработка
> самого звука, но и языковые модели.

> До глубоких сетей первые два шага этого процесса выглядели так: сначала
> звуковой сигнал превращался в так называемые MFCC-признаки 
> (расшифровывается как mel-frequency cepstral coefficients, то есть от сигнала нужно сначала
> взять преобразование Фурье, получив спектр, затем перейти к логарифмам амплитуд частот на шкале
> мелов, а потом взять от этих логарифмов обратное преобразование Фурье, получив кепстр (это слово
> получилось обращением первых четырех букв слова «спектр») [379].), фонемы из них
>распознавали с помощью скрытых марковских моделей [119], а языковые модели
> представляли собой обычно сглаженные распределения n-грамм, то есть модели,
> которые оценивают вероятность следующего слова при условии нескольких
> предыдущих [281]

> Глубокие сети начали с того, что заменили собой распознаватель, основанный
> на скрытых марковских моделях. Более того, быстро стало ясно, что MFCC-признаки
> тоже можно улучшить путем обучения: нет, сети пока что не начинают работу
>непосредственно с необработанного звукового сигнала, но представления,
> подающиеся на вход современным системам распознавания, гораздо более «сырые»,
> чем MFCC [260].

> Вслед за речью пришло время обработки изображений. Точнее, она была всегда:
> с 1980-х годов в группе Яна ЛеКуна изображения обрабатывали именно нейронными
> сетями. К тому же времени относится и первый взлет сверточных нейронных сетей,
> специальной архитектуры, которая отлично подходит для обработки именно
>таких входов, как картинки; сверточным сетям мы посвятим главу 5 [18, 205]. В
> целом, это редкий пример области, в которой нейронные сети никогда полностью не
> пропадали из виду. Однако после начала революции глубокого обучения прогресс
> в обработке изображений тоже резко ускорился. В 2009–2010 годах глубокие
> сверточные сети выиграли ряд соревнований по распознаванию символов [396] и даже
> распознаванию видео с камер слежения [259, 430]. Кроме того, в 2009 году
> появились первые реализации нейронных сетей на графических процессорах [434], что
> дало огромный импульс всем связанным со сверточными сетями исследованиям
> (видеокарты для сверточных сетей особенно полезны).

>Достижения глубоких нейронных сетей в обучении с подкреплением тоже трудно
> переоценить. Глубокие сети оказались как нельзя кстати, потому что дают
> универсальный «черный ящик», способный приблизить функцию «оценки позиции».
> Даже первые значительные успехи обучения с подкреплением в конце 1980-х уже
> были основаны на нейронных сетях. Последний громкий успех глубоких сетей
> в обучении с подкреплением — созданная DeepMind программа AlphaGo, которая
> сумела обыграть одного из лучших игроков мира в го — одну из последних
> классических игр с полной информацией, которые считались крайне сложными для
>компьютера

> люди очень хороши в том, что называется переносом обучения
> (transfer learning): мы можем быстро построить модель нового объекта или
> процесса, порождая правильные абстракции из очень, очень маленького числа
> обучающих примеров. Известно, что дети с трех до 14–15 лет изучают в среднем 8–9
> новых слов каждый день1. Довольно очевидно, что они не могут получить большое
> число разных контекстов для каждого нового слова и должны обучаться по считанным
> единицам тренировочных примеров. Сейчас начинают проводиться исследования о том,
> как перенести такое обучение (его обычно называют обучением по одному примеру,
> one-shot learning) в нейронные сети и модели машинного обучения в целом.

### Глава 2. Предварительные сведения, *или Курс молодого бойца*

> Во второй главе мы дадим краткий обзор предварительных сведений, требующихся
> для того, чтобы дальше перейти непосредственно к нейронным сетям.
>А именно, мы рассмотрим:

- основы теории вероятностей, теорему Байеса и вероятностный подход к
машинному обучению;
- функции ошибки в машинном обучении и регуляризацию;
- различие между регрессией и классификацией, функции ошибки для классификации;
- главный метод оптимизации в нейронных сетях — градиентный спуск;
- конструкцию графа вычислений и алгоритмы дифференцирования на нем;
- и наконец, практическое введение в библиотеку TensorFlow, которую мы
будем использовать для примеров в этой книге.

#### 2.1. Теорема Байеса

> Как мы уже
> видели в предыдущей главе, машинное обучение — это наука о том, как на
> основании данных делать выводы, откуда эти данные взялись, и предсказания, какие
> данные встретятся нам в будущем. Важно, что делать точные выводы невозможно:
> процессы, приводящие к порождению данных, слишком сложны даже в самых
> простых случаях.
> Простейший пример: если знать заранее все параметры броска монеты: начальную скорость,
> состояние окружающего воздуха, распределение массы и т. п., то теоретически вполне возможно
> рассчитать ее полет и достаточно уверенно предсказать, чем она выпадет. Но это настолько сложно, что мы не
> задумываясь используем монету как честный генератор случайных чисел.

> бывают *дискретные* случайные величины с конечным или счетным набором
> исходов; каждому из своих исходов они присваивают неотрицательную
> вероятность, и вероятности исходов в сумме дают единицу; классический и
> фактически единственный пример здесь — бросание кубика;

> бывают *одномерные непрерывные* случайные величины, у которых набор
> исходов представляет собой вещественную прямую R; тогда вероятности
> отдельных исходов превращаются в функцию распределения F(a) = p(x < a)
> и ее производную (в этом месте может быть много сложностей, но практически
> всегда в наших примерах функция F будет непрерывно дифференцируемой),
> плотность распределения p(x) = dF/dx теперь не сумма, а интеграл неотрицательной
> функции плотности должен быть равен единице

> *Совместная вероятность* — это вероятность одновременного наступления
> двух событий, p(x, y). Грубо говоря, если есть два кубика, на каждом из
> которых могут выпасть числа от 1 до 6, то мы можем рассмотреть новую
> случайную величину «два кубика», у которой будут возможные исходы (1; 1), (1; 2), (1; 3)
> и так далее до (6; 6), всего 6x6 = 36 исходов. Две случайные величины называются
> *независимыми*, если:
> p(x, y) = p(x)p(y):

> Чтобы получить обратно из совместной вероятности вероятность того или иного
> исхода одной из случайных величин, нужно просуммировать по другой.
> Этот процесс иногда называется умным словом *маргинализация*: если
> рассмотреть ее в случае непрерывных случайных величин, получится, что мы фактически
> проецируем двумерное распределение, поверхность в трехмерном пространстве, на
> одну из осей, получая функцию от одной переменной.

> *Условная вероятность* — вероятность наступления одного события, если
> известно, что произошло другое, p(x | y), ее обычно определяют формально так:
> p(x | y) = p(x, y)/p(y)

> Аналогично обычной независимости можно теперь определить *условную независимость*:
> x и y условно независимы при условии z, если
> p(x, y | z) = p(x | z)p(y | z)

> Чтобы проиллюстрировать все эти базовые определения, в качестве примера
> рассмотрим известный «парадокс» Монти Холла (в кавычках потому, что никакого
> парадокса здесь на самом деле нет). Представьте себе, что на игровом шоу
> усатый ведущий предлагает вам выбрать из трех абсолютно одинаковых шкатулок:
> в одной из них лежат деньги, в двух других ничего нет. Вы принимаете решение
> (пока что у вас нет никаких оснований предпочесть одну из шкатулок), после чего
> ведущий открывает одну из двух оставшихся и показывает, что в ней пусто.
> Очевидно, он всегда может так сделать: даже если вы выбрали пустую шкатулку, из
> двух оставшихся все равно одна пустая найдется. И теперь наступает момент
> истины: ведущий предлагает вам изменить свое решение и взять вместо выбранной
> ту шкатулку, которая осталась закрытой. Выгодно ли вам это делать?

> Многие предполагают, что нет никакой разницы. И действительно, рассмотрим
> события наличия денег в трех шкатулках, обозначив их через x1, x2 и x3
> соответственно. Изначально их вероятности были равны: p(x1) = p(x2) = p(x3) = 1/3
> Если бы ведущий просто открыл одну из шкатулок (для определенности пусть это
> будет x3) до вашего выбора, то две другие шкатулки остались бы равновероятными:
> p(x1 | x3 = 0) = p(x2 | x3 = 0) = 1/2

> Но структура эксперимента устроена сложнее! Ведущий открывает не
> случайную пустую шкатулку, а одну из двух не выбранных игроком. Поэтому события
> «какую из двух пустых шкатулок открыть» и «лежат ли деньги в выбранной вами
> шкатулке» становятся зависимыми. Давайте без потери общности предположим,
> что вы изначально выбрали первую шкатулку, а выбранную ведущим шкатулку
> обозначим через y. Будем предполагать, что если деньги действительно лежат в
> выбранной вами первой шкатулке (x1 = 1), то ведущий выбирает одну из двух пустых
> равновероятно. Тогда совместные вероятности разложатся так:

> p(x1 = 1, y = 2) = 1/6, p(x2 = 1, y = 2) = 0, p(x3 = 1, y = 2) = 1/3,

> p(x1 = 1, y = 3) = 1/6, p(x2 = 1, y = 3) = 1/3, p(x3 = 1, y = 3) = 0,

> и это совсем не похоже на определение независимых величин, правда?

#### 2.2. Функции ошибки и регуляризация

#### 2.3. Расстояние Кульбака — Лейблера и перекрестная энтропия

#### 2.4. Градиентный спуск: основы

#### 2.5. Граф вычислений и дифференцирование на нем

#### 2.6. И о практике: введение в TensorFlow и Keras

### Глава 3. Перцептрон, *или Эмбрион мудрого компьютера*

#### 3.1. Когда появились искусственные нейронные сети

#### 3.2. Как работает перцептрон

#### 3.3. Современные перцептроны: функции активации

#### 3.4. Как же обучаются настоящие нейроны

#### 3.5. Глубокие сети: в чем прелесть и в чем сложность?

#### 3.6. Пример: распознавание рукописных цифр на TensorFlow

## Часть II. Основные архитектуры

### Глава 4. Быстрее, глубже, сильнее, *или Об оврагах, долинах и трамплинах*

#### 4.1. Регуляризация в нейронных сетях

#### 4.2. Как инициализировать веса

#### 4.3. Нормализация по мини-батчам

#### 4.4. Метод моментов: Ньютон, Нестеров и Гессе

#### 4.5. Адаптивные варианты градиентного спуска

### Глава 5. Сверточные нейронные сети и автокодировщики, *или Не верь глазам своим*

#### 5.1. Зрительная кора головного мозга

#### 5.2. Свертки и сверточные сети

#### 5.3. Свертки для распознавания цифр

#### 5.4. Современные сверточные архитектуры

#### 5.5. Автокодировщики

#### 5.6. Пример: кодируем рукописные цифры

### Глава 6. Рекуррентные нейронные сети, *или Как правильно кусать себя за хвост*

#### 6.1. Мотивация: обработка последовательностей

#### 6.2. Распространение ошибки и архитектуры RNN

#### 6.3. LSTM

#### 6.4. GRU и другие варианты

#### 6.5. SCRN и другие: долгая память в обычных RNN

#### 6.6. Пример: порождаем текст символ за символом

## Часть III. Новые архитектуры и применения

### Глава 7. Как научить компьютер читать, *или Математик - Мужчина + Женщина =*

#### 7.1. Интеллектуальная обработка текстов

#### 7.2. Распределенные представления слов: word2vec

#### 7.3. Русскоязычный word2vec на практике

#### 7.4. GloVe: раскладываем матрицу правильно

#### 7.5. Вверх и вниз от представлений слов

#### 7.6. Рекурсивные нейронные сети и синтаксический разбор

### Глава 8. Современные архитектуры, *или Как в споре рождается истина*

#### 8.1. Модели с вниманием и encoder-decoder

#### 8.2. Порождающие модели и глубокое обучение

#### 8.3. Состязательные сети

#### 8.4. Практический пример и трюк с логистическим сигмоидом

#### 8.5. Архитектуры, основанные на GAN

### Глава 9. Глубокое обучение с подкреплением, *или Удивительное происшествие с чемпионом*

#### 9.1. Обучение с подкреплением

#### 9.2. Марковские процессы принятия решений

#### 9.3. От TDGammon к DQN

#### 9.4. Бамбуковая хлопушка

#### 9.5. Градиент по стратегиям и другие применения

### Глава 10. Нейробайесовские методы, *или Прошлое и будущее машинного обучения*

#### 10.1. Теорема Байеса и нейронные сети

#### 10.2. Алгоритм EM

#### 10.3. Вариационные приближения

#### 10.4. Вариационный автокодировщик

#### 10.5. Байесовские нейронные сети и дропаут

#### 10.6. Заключение: что не вошло в книгу и что будет дальше
