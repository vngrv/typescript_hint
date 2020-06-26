### Typescript Hint question

1. Для чего нужен тип "Omit"?
    Новый тип, в котором можно указать свойства, которые будут исключены из исходного типа
    Constructs a type by picking all properties from T and then removing K.
 ```js
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
    При использовании, необъявленной в проекте TS, библиотеки JS
3. Как автоматически получить файлы declaration?
    Установив опцию в jsconfig.js
```
{
"compilerOptions": {
    ...
    "declaration": true,
  }
}
```
4. Как перезагрузить функцию и что такое перезагрузка функции?
    Достигается реализация полиморфизма. Функции две и более могут иметь одно и тоже имя, но бывают случаи когда необходимо изменить их тела.
    Надо использовать то же имя цункции над оригинальной функцией без фигурных скобом, затем изменить число, типы входящих и исходящих значений. 
```js
function add(x: string, y: string): string;
function add(x: number, y: number): number {
    return x+y;
}
``` 
5. Как сделать все свойства интерфейса необязательными?
    Добавив попросительный знак после имени свойства в интерфейсп или использовать тип Partial
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
    Класс, свойства, методы и аргументы метода

7. Для чего нужен тип "Record"?
    Позволяет создаавать типизированную карту
