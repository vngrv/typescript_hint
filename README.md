### Typescript Hint question

1. Для чего нужен тип "Omit"?
<br>
    Новый тип, в котором можно указать свойства, которые будут исключены из исходного типа
<br>
    Constructs a type by picking all properties from T and then removing K.
<br>
 ```
interface Todo {
    title: string;
    description: string;
    completed: boolean;
}
type TodoPreview = Omit<Todo, 'description'>;
const todo: TodoPreview = {
    title: 'Clean room',
    completed: false,
};
```

2. Когда нужно использовать ключевое слово "declare"?
    <br>При использовании, необъявленной в проекте TS, библиотеки JS
3. Как автоматически получить файлы declaration?
    <br>Установив опцию в jsconfig.js
```
{
"compilerOptions": {
    ...
    "declaration": true,
  }
}
```
4. Как перезагрузить функцию и что такое перезагрузка функции?
    <br>Достигается реализация полиморфизма. Функции две и более могут иметь одно и тоже имя, но бывают случаи когда необходимо изменить их тела.
    <br>Надо использовать то же имя цункции над оригинальной функцией без фигурных скобом, затем изменить число, типы входящих и исходящих значений. 
```
function add(x: string, y: string): string;
function add(x: number, y: number): number {
    return x+y;
}
``` 
5. Как сделать все свойства интерфейса необязательными?
    <br>Добавив попросительный знак после имени свойства в интерфейсп или использовать тип Partial
```js
interface Person {
  name: string;
  age: number;
}

type PartialPerson = Partial<Person>; // Аналогично следующему коду

linesinterface PartialPerson {
  name?: string;
  age?: number;
}
```
6. К чему можно применять декораторны?
    <br>Класс, свойства, методы и аргументы метода

7. Для чего нужен тип "Record"?
    <br>Позволяет создаавать типизированную карту
8. Как можно получить доступ к классам вне модуля, в котором они определены?
    <br>Ключевым словом export перед классом
9. Когда используется ключевое словово unknown?
    <br>Когда вы не хотите использовать ключевое слово any и/или заранее не знаете точный тип, но хотите его обозначить позже.
```js
let person: unknown = 'John';
if (typeof person === string) {
  let name: string = person;
} 
```
10. Что такое ".map" файл, как и зачем его использовать?
    <br> Map-файл - файл карты исходников, который можно использовать при выполнении отладки. Его можно сгенерировать, установив опцию компилятора sourceMap в true (tsconfig.js)
