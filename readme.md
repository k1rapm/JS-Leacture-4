## Array
![](./img/download.png)

### Массив — это объект, который содержит значения (любого типа), не входящие в именованные свойства/ключи. а скорее в числовой позиции В JavaScript массив представляет собой упорядоченный список значений. Каждое значение называется элементом, заданным индекс. ... Во-первых, массив может содержать значения смешанных типов.

### Объект Array, как и массивы в других языках программирования, позволяет хранить коллекцию из нескольких элементов под одним именем переменной и имеет члены для выполнения общих операций с массивами .

### В JavaScript массивы не являются примитивами , а представляют собой Arrayобъекты со следующими основными характеристиками:

### Размер массивов JavaScript можно изменять , и они могут содержать различные типы данных . (Если эти характеристики нежелательны, используйте вместо них типизированные массивы .)

### Массивы JavaScript не являются ассоциативными массивами , поэтому к элементам массива нельзя получить доступ с использованием произвольных строк в качестве индексов, но к ним необходимо обращаться с использованием неотрицательных целых чисел (или их соответствующей строковой формы) в качестве индексов.

### Массивы JavaScript имеют нулевой индекс : первый элемент массива находится по индексу 0, второй по индексу 1и т. д., а последний элемент имеет значение lengthсвойства массива минус 1.

### Операции копирования массива JavaScript создают неполные копии . (Все стандартные встроенные операции копирования с любыми объектами JavaScript создают поверхностные копии, а не глубокие копии ).

### Arrayобъекты не могут использовать произвольные строки в качестве индексов элементов (как в ассоциативном массиве ), но должны использовать неотрицательные целые числа (или их соответствующую строковую форму). Установка или доступ через нецелые числа не устанавливает или не извлекает элемент из самого списка массива, но устанавливает или получает доступ к переменной, связанной с коллекцией свойств объекта этого массива . Свойства объекта массива и список элементов массива разделены, и к этим именованным свойствам нельзя применить операции обхода и мутации массива .

### Элементы массива являются свойствами объекта в том же смысле, в котором они toStringявляются свойствами (но, если быть точным, toString()это метод). Тем не менее, попытка доступа к элементу массива следующим образом вызывает синтаксическую ошибку, поскольку имя свойства недопустимо:

### Синтаксис JavaScript требует, чтобы свойства, начинающиеся с цифры, были доступны с использованием скобочной записи вместо точечной записи . Индексы массива также можно заключить в кавычки (например, years['2']вместо years[2]), хотя обычно это не обязательно.

### Свойство массива JavaScript lengthи числовые свойства связаны.

### Некоторые встроенные методы массива (например, join(), slice(), indexOf()и т. д.) учитывают значение lengthсвойства массива при их вызове.

### Другие методы (например, push(), splice()и т. д.) также приводят к обновлению свойства массива length.

### При установке свойства в массиве JavaScript, когда свойство является допустимым индексом массива и этот индекс находится за пределами текущих границ массива, движок lengthсоответствующим образом обновит свойство массива:

### Методы массива ведут себя по-разному при обнаружении пустых ячеек в разреженных массивах . В общем, старые методы (например forEach, ) обрабатывают пустые слоты иначе, чем индексы, содержащие undefined.

### К методам, которые имеют специальную обработку для пустых слотов, относятся следующие: concat(), copyWithin(), every(), filter(), flat(), flatMap(), forEach(), indexOf(), lastIndexOf(), map(), , reduce(), reduceRight(), reverse(), slice(), some(), , sort()и splice(). Методы итерации, такие как forEachвообще не посещают пустые слоты. Другие методы, такие как concat, copyWithinи т. д., сохраняют пустые слоты при копировании, поэтому в конечном итоге массив все равно остается разреженным.

># POP

### Метод popудаления последнего элемента из массива и возвращает удаленное значение.

### Метод popне является судебным по данному типу; этот метод может быть вызван или применен к массивоподобным объектам. Объекты, не содержащие свойства length, отражающего последний элемент в серии последовательных числовых, начинающие с нуля, свойства, могут повести себя неправильным образом.

### Если вы вызываете pop()пустой массив, он возвращает значение undefined.

>### SHIFT

### Метод shift()удаляет элемент с нулевым индексом и сдвигает значения последовательных индексов вниз, а затем возвращает удаленное значение. Если lengthсвойство равно 0, undefinedвозвращается.

### Поведение метода pop()аналогично методу shift(), но применяется к последнему элементу массива.

### Метод shift()является мутирующим методом . Он меняет длину и содержимое this. Если вы хотите, чтобы значение thisбыло таким же, но возвращало новый массив с удаленным первым элементом, вы можете использовать arr.slice(1)его.

### Метод shift()является универсальным . Он ожидает только, что thisзначение будет иметь lengthсвойство и свойства с целочисленным ключом. Хотя строки также подобны массивам, этот метод не подходит для применения к ним, поскольку строки неизменяемы.

># PUSH

### Метод push()добавляет значения в массив.

### Array.prototype.unshift()имеет аналогичное поведение push(), но применяется к началу массива.

### Метод push()является мутирующим методом . Он меняет длину и содержимое this. Если вы хотите, чтобы значение thisбыло таким же, но возвращало новый массив с добавленными в конец элементами, вы можете использовать arr.concat([element0, element1, /* ... ,*/ elementN])вместо него. Обратите внимание, что элементы заключены в дополнительный массив — в противном случае, если элемент сам является массивом, он будет распределен, а не отправлен как один элемент из-за поведения concat().

### Метод push()является универсальным . Он ожидает только, что thisзначение будет иметь lengthсвойство и свойства с целочисленным ключом. Хотя строки также подобны массивам, этот метод не подходит для применения к ним, поскольку строки неизменяемы.

># UNSHIFT

### Метод unshift()вставляет заданные значения в начало объекта, подобного массиву.

### Array.prototype.push()ведет себя аналогично unshift(), но применяется к концу массива.

### Обратите внимание: если в качестве параметров передаются несколько элементов, они вставляются в чанк в начале объекта в том же порядке, в котором они были переданы в качестве параметров. Следовательно, вызов unshift()с n аргументами один раз или вызов его nнесколько раз с одним аргументом (например, с помощью цикла) не дает одинаковых результатов.

># JOIN

### Строковые преобразования всех элементов массива объединяются в одну строку. Если элемент равен undefined, null, он преобразуется в пустую строку вместо строки "null"или "undefined".

### Доступ к методу joinосуществляется внутри Array.prototype.toString()без аргументов. Переопределение экземпляра массива также joinпереопределит его поведение.toString

### Array.prototype.joinрекурсивно преобразует каждый элемент, включая другие массивы, в строки. Поскольку строка, возвращаемая Array.prototype.toString(что аналогично вызову join()), не имеет разделителей, вложенные массивы выглядят так, как будто они сглажены. Вы можете управлять только разделителем первого уровня, тогда как более глубокие уровни всегда используют запятую по умолчанию.

># SPLISE

### Метод splice()является мутирующим методом . Это может изменить содержимое this. Если указанное количество вставляемых элементов отличается от количества удаляемых элементов, массив lengthтакже будет изменен. В то же время он используется @@speciesдля создания нового экземпляра возвращаемого массива.

### Если удаленная часть является разреженной , возвращаемый массив splice()также будет разреженным, а соответствующие индексы будут пустыми слотами.

### Метод splice()является универсальным . Он ожидает только, что thisзначение будет иметь lengthсвойство и свойства с целочисленным ключом. Хотя строки также подобны массивам, этот метод не подходит для применения к ним, поскольку строки неизменяемы.

># toREVERSED

### Метод toReversed()транспонирует элементы вызывающего объекта массива в обратном порядке и возвращает новый массив.

### При использовании с разреженными массивами метод toReversed()перебирает пустые слоты, как если бы они имели значение undefined.

### Метод toReversed()является универсальным . Он ожидает только, что thisзначение будет иметь lengthсвойство и свойства с целочисленным ключом.



