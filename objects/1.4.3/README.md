## Задача 3. Проверка формулы

### Описание
Поговорим о математике. Чем старше мы становились, тем сложнее были формулы, которые нам приходилось и приходится использовать. Подобная задача иногда встречается на собеседованиях, звучит она так: 
на вход методу приходит формула, нужно ее разобрать и проверить, все ли открытые скобки в ней закрыты и нет ли закрытых или открытых скобок, которые находятся не на своем месте (например, `5*)(3+5())`). Если есть лишние скобки — возвращаем false, если лишних скобок нет — true.

### Функционал программы
1. Возможность ввода из консоли любого текста;
2. Проверка того, что ввели не пустую строку;
3. Проверка корректности формулы.

### Примеры
#### Пример 1
```
"Введите формулу:"
"(a+b)*c" <нажмите enter>
"Формула корректна"
```

#### Пример 2
```
"Введите формулу:"
"(a+b))*c" <нажмите enter>
"Формула некорректна"
```

### Процесс реализации
Прежде чем приступать к реализации, нужно продумать алгоритм. Советую вам для начала попробовать решить задачу на бумаге. 
Решить можно следующим образом: считываем каждый символ и увеличиваем специально отведенную для этого переменную (назовем ее "счетчик"), если это открывающая скобка, и уменьшаем переменную, если это закрывающая скобка. 
Формула будет верна, если после обхода всей строки наш счетчик будет равен нулю.

1. Создадим новый repl на сайте [repl.it](https://repl.it/repls), как написано в инструкции к выполнению домашней работы, и зададим название `homework1.4.3`.

2. Считываем строку из консоли и сохраняем в переменную input.

3. Создадим метод `isFormulaValid` (методы, возвращающие тип boolean, принято начинать не с get, а с is, как бы задавая вопрос). Возвращать он будет `true` или `false`, а входным параметром будет строка (формула, которую ввели). 
Метод должен находиться вне другого метода `main`, в котором мы запускаем программу. Сигнатура нового метода будет такая: `static boolean isFormulaValid(String formula)`.

4. В методе `isFormulaValid` создадим переменную (счетчик) типа `int` и назовем ее `counter`. Она будет отвечать за подсчет открытых и закрытых скобок. Также явно укажем, что она изначально равна нулю (`int counter = 0`).

5. Нам нужно перебрать всю строку. Нам известно, как взять длину строки. Метод `input.length()` вернет нам количество символов. На основе этих данных пишем цикл посимвольного обхода строки:

   ```
   for (int i = 0; i < input.length(); i++) {
      //TODO
   }
   ```

Чтобы взять символ строки, нужно обратиться к строке и вызвать метод `charAt`, который принимает на вход `index` символа (напомню, что индексы в строках и массивах начинаются с 0).

7. Вмеcто `//TODO` в цикле с предыдущего шага добавляем 

   ```
   char c = input.charAt(i);
   if (c == '(') {
       //если нашли открывающую скобку, увеличиваем счетчик
       counter++;
   } else if (c == ')') {
       //если нашли закрывающую скобку, уменьшаем счетчик
       counter--;
   }
   ```
   

8. Результатом выполнения нашего метода `isFormulaValid` будет сравнение counter c нулем. Можно записать как `return counter == 0`.

9. Осталось проверить и вызвать наш метод в методе `main`.

Примерная структура программы должна получиться следующая:

    import java.util.Scanner;
    class Main {
        public static void main(String[] args) {
            //1. Чтение из консоли
            //2. Вызов и вывод результата работы метода isFormulaValid
        }
    
        public static boolean isFormulaValid (String input) {
            //TODO  
        }
    }
 
