# substring
substr.js
Реализуйте и экспортируйте по умолчанию функцию substr, которая возвращает подстроку из переданной строки. Подстрокой называется любая выбранная часть строки. Функция принимает на вход три параметра:

Строка.
Начальный индекс. Значение по умолчанию: 0.
Длина подстроки. Значение по умолчанию: длина всей строки.
У этой функции множество вариантов поведения:

Если переданная длина отрицательная, то внутри она становится единицей
Если переданная длина равна нулю, то возвращается пустая строка
Если конечный индекс (переданная длина + начальный индекс) выходит за границу строки, то берется подстрока от начального индекса до конца строки
Если начальный индекс отрицательный, то внутри он становится нулем
Если начальный индекс выходит за границу слова справа, то всегда возвращается пустая строка
По умолчанию возвращается сама строка:

substr('');     // => ''
substr('abba'); // => abba
substr('abba', 0, 1);    // => a
substr('abba', 1, 2);    // => bb
substr('abba', -10, 2);  // => ab
substr('abba', -1, 100); // => abba
substr('abba', -1, -1);  // => a
substr('abba', 1, -10);  // => b
substr('abba', 1, 10);   // => bba
substr('abba', 1, 0);    // => ''
substr('abba', 100, 3);  // => ''
Для реализации этой функции, используйте подход, который называется "нормализация". Он заключается в том, что перед тем как делать вычисления, данные приводятся к виду, с которым удобно работать. Например длина строки для substr может иметь следующие неудобные значения:

Отрицательное число
Число выходящее за границу строки
Индекс + Длина выходят за границу строки
В каждой из этих ситуаций длину строки можно изменить на такое значение, которое будет удобно для обработки сразу всех возможных случаев. Если число отрицательное, то длина становится равной единице (из условия), если оно выходит за границу строки, то его нужно сделать равным длине строки. В последнем случае длина должна стать числом Длина Строки - Индекс. После этих манипуляций, процесс взятия подстроки становится универсальным и не содержащим условия.

Подсказки
Функция getLength возвращает длину переданной ей строки: getLength('cat'); // => 3
