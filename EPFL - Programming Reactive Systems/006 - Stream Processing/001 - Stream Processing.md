# Обработка потоков

Это широкое понятие обычно ассоциируется с:

- Обработкой какого-то количества (или бесконечного количества) элементов;
  - Идея в том, что за раз мы не можем загрузить их все в память;
- Через пушинг и пуллинг через пайплайн;
- Такой пайплайн композируется из операций, которые модифицируют элементы;
- Операции часто описываются в качестве DSL похожжего на Scala коллекции (map, flatMap, filter)/

В этом курсе мы будем обсуждать один специфичный вид стриминга - реактивные стримы.

## Мотивация

Источники данных могут быть бесконечными (например - информация с сенсоров). При этом данные могут идти в распространённые узлы.

Обработка стримов пытается достичь:

- Композируемых строительных блоков (навешивать на стрим обработчики, написанные отдельно);
- Контролировать поток через такой пайплайн;
- Обрабатывать много (бесконечно) элементов на оптимальной скорости.


## Асинхронная обработка потоков

Синхронная обработка потоков проста (открытие файла и чтение). Асинхронная обработка (например, на нескольких узлах) - уже не так проста. Стандарты появились относительно недавно.

В этом курсе мы будем заниматься обработкой потоков, которая формализована как Спецификация Реактивных Потоков (Lightbend, Oracle, Pivotal, RedHat 2014-2017).

Начиная с Java 9 они есть по умолчанию в Java (java.util.concurrent.Flow).

## Примеры потоковой обработки

- Анализ твитов из твиттера;
- Анализ логов;
- Анализ твитов;
- Чаты, совмещающие приходящие сообщения в одно окошко...

## Resillience (упругость) стримов

- Будет ли рестартиться прогресс обработки из-за фейла стрима?
- Будут ли элементы теряться или снапшотиться или как-то отслеживать прогресс при рестарте?

Средства для всего этого есть в Akka Streams.



