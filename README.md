# Список вопросов к экзамену

Дан фрагмент кода на языке С++. Что выведется на экран в результате его работы?
~~~cpp
enum Color {
    YELLOW = -2,
    BLACK,
    PINK = -1,
    GREEN = 0
};

Color color = Color::BLACK;
std::cout << color;
~~~
Ответ:

- [x] -1
- [ ] Ошибка. Для Color не определён оператор <<
- [ ] 1
- [ ] -3
- [ ] Ошибка. Всем перечислителям должны быть заданы значения

---

Дан фрагмент кода на С++. Что отобразится на экране после его выполнения?
~~~cpp
template<typename T>
T sum(T a, T b){
    auto res = a + b;
    return res;
}

int main()
{
    std::cout << sum(3.0, 0.1415);
}
~~~
Ответ: 
- [ ] Ошибка компиляции
- [ ] 3
- [ ] 0.1415
- [x] 3.1415

---

Язык Go. Что будет выведено на экран в результате работы этого кода?
~~~go
package main
import "fmt"

type Data struct{
    i int
}

func (d *Data) method(){
    d.i = 1
}

func (d Data) method(){
    d.i = 1
}

func main() {
    var d *Data = &Data{}
    d.method()
    fmt.Print(d.i)
}
~~~
Ответ:
- [ ] 0
- [ ] 1
- [ ] Мусорное значение
- [x] Ошибка

---

Язык Go. Какие из ниже перечисленных команд, НЕ являются операторами цикла в Go?
Ответ:
- [ ] for
- [x] foreach
- [x] do while
- [x] repeat until
- [x] while

---

Дан фрагмент кода на Go. Что будет выведено на экран после выполнения фрагмента кода?
~~~go
for i := 0; i < 1; i++ {
    k := 10
    fmt.Print(i)
}
fmt.Print(k)
~~~
Ответ:
- [ ] 010
- [ ] 0110
- [x] Ошибка
- [ ] 110

---

Даны фрагменты кода на С++. Что отобразится на экране после его выполнения?
~~~cpp
int x = 5;
(x != 5) || std::cout << 11;
std::cout << x;
~~~
Ответ: <code> 115 </code>

---

Дан фрагмент кода на языке С++:
~~~cpp
int b[8][4][2];
~~~
Выберите все допустимые выражения.
Ответ:
- [x] int (*i)[4][2] = b;
- [ ] int ***k = b;
- [ ] int (**j)[2] = b;
- [ ] int *i[8][4][2] = b;

---

Язык С++. Член класса расположен в секции с модификатором доступа public. Этот член класса:
Ответ:
- [x] Можно использовать в коде методов наследников
- [ ] Нельзя использовать нигде
- [x] Можно использовать в коде не относящихся к классу функций
- [x] Можно использовать в коде методов класса

---

Дан фрагмент кода на языке С++. Что будет напечатано в результате его выполнения?
~~~cpp
struct SomeClass{
    const int i = 0;
    
    SomeClass(int i){
        this->i = i;
    }
};

SomeClass obj(10);
std::cout << obj.i;
~~~
Ответ:
- [ ] 10
- [x] Ошибка
- [ ] 0

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
namespace A{
    int i = 1;
}

int i = 2;

int main() {
    int i = 3;
    {
      using namespace A;      
      std::cout << i;
    }
}
~~~
Ответ:
- [ ] Ошибка
- [x] 3
- [ ] 1
- [ ] 2

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
int i = 1;

namespace C{
    int i = 2;
}

namespace A {
    namespace B {
        using namespace C;
        void print() {
            std::cout << i;
        }
    }
    int i = 3;
}

int main() {
    A::B::print();
}
~~~
Ответ:
- [ ] 1
- [ ] 2
- [ ] 3
- [x] Ошибка

---

Язык С++. Какой модификатор доступа у some_field?
~~~cpp
struct SomeClass{
    int some_field;
};
~~~
Ответ:
- [ ] private
- [x] public
- [ ] protected
- [ ] published

---

Сколько раз, в коде на языке С++, можно писать определение этой функции?
~~~cpp
void print(short a, short b, std::string sep){
    std::cout << a << sep << b;
}
~~~
Ответ:
- [ ] Ни одного;
- [ ] Любое количество раз;
- [x] Только один раз в программе;
- [ ] Не более одного раза в каждой области видимости;

---

Дан фрагмент кода на Go. Что будет выведено на экран в результате выполнения данного фрагмента?
~~~go
a := 5
b := 10
switch (a + b){
    case  5: 
        fmt.Print("0")
        fallthrough
    case 10: 
        fmt.Print("1")
        fallthrough
    case 15: 
        fmt.Print("2")
        fallthrough
    default: 
        fmt.Print("3")
}
~~~
Ответ: <code> 23 </code>

---

Какие из следующих вариантов использования мьютекса в Go являются правильными (считаем, что в процессе работы с данными ошибки быть не может)?
Ответ:
<ul>
<li>- [ ] <li>

~~~go
func foo() {
    mutex.Unlock()
    // работа с данными
    mutex.Lock()
}
~~~    
</li></li>

<li>- [ ] <li>

~~~go
func foo() {
    mutex.Unlock()
    // работа с данными
}
~~~
</li></li>

<li>- [x] <li>

~~~go
func foo() {
    mutex.Lock()
    defer mutex.Unlock()
    // работа с данными
}
~~~
</li></li>

<li>- [x] <li>

~~~go
func foo() {
    mutex.Lock()
    // работа с данными
    mutex.Unlock()
}
~~~
</li></li>
<li>- [ ] <li>

~~~go
func foo() {
    mutex.Lock()
    // работа с данными
}
~~~
</li></li>
</ul>

---

Дана функция на языке С++. Выберите все варианты вызова данной функции, при которых произойдёт обмен значениями переменных x и y. Переменные обвялены следующим образом: int x = 1; и int y = 2;:
~~~cpp
void swap(int& a, int& b){
    int t = a;
    a = b;
    b = t;
}
~~~
Ответ:
- [x] swap(x,y);
- [ ] Эта функция не может выполнить требуемое действие;
- [ ] swap(&x, &y);
- [ ] swap(*x, *y);
- [x] swap(y, x);

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
int i = 1;

namespace C{
    int i = 2;
}

namespace A {
    int i = 3;
    namespace B {
        using namespace C;
        void print() {
            std::cout << i;
        }
    }
}

int main() {
    A::B::print();
}
~~~
Ответ:
- [ ] Ошибка
- [ ] 1
- [ ] 2
- [x] 3

---

Язык С++. Известно, что переменные объявлены следующим образом:
~~~cpp
int i = 10;
int *p = &i;
~~~
Выберите все верные утверждения.
Ответ:
- [ ] & - оператор логическое И
- [ ] * - оператор умножения
- [ ] * - указатель
- [ ] * - оператор разыменования
- [x] * - часть описания типа переменной
- [ ] & - оператор побитовое И
- [x] & - оператор взятия адреса

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
namespace A{
    int i = 1;
}

int main() {
    std::cout << i;
}
~~~
Ответ:
- [x] Ошибка
- [ ] 1

---

Дан фрагмент кода на языке С++. Что выведется на экран в результате его работы?
~~~cpp
enum class Color {
    YELLOW,
    BLACK,
    PINK,
    GREEN
};

Color color = Color::BLACK;
std::cout << color;
~~~
Ответ:
- [x] Ошибка. Для Color не определён оператор <<
- [ ] 1
- [ ] Какое-то "мусорное" значение, т.к. для BLACK НЕ указано значение явно
- [ ] Строка BLACK
- [ ] 0

---

Дан фрагмент кода на языке С++. Что будет напечатано в результате его выполнения?
~~~cpp
struct SomeClass{
    int& i;
    
    SomeClass(int& i):i(i){
    }
};

int i = 0;
SomeClass obj(i);
std::cout << obj.i;
~~~
Ответ:
- [ ] 10
- [ ] Ошибка
- [x] 0

---

Дан фрагмент кода на языке С++. Будет ли код работать?
~~~cpp
int main(){
    print(1, 2, " ");
}

void print(short a, short b, std::string sep){
    std::cout << a << sep << b;
}
~~~
Ответ:
- [ ] Да. Но будет вызвана функция print из библиотеки iostream;
- [x] Нет. Ошибка на этапе компиляции;
- [ ] Нет. Ошибка на этапе исполнения;
- [ ] Да. Ошибок нет;

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
int i = 1;

namespace C{
    int i = 2;
}

namespace A {
    int i = 3;
    namespace B {
        using C::i;
        void print() {
            std::cout << i;
        }
    }
}

int main() {
    A::B::print();
}
~~~
Ответ:
- [ ] 3
- [ ] Ошибка
- [ ] 1
- [x] 2

---

Язык С++. Дан код:
~~~cpp
int array[3] = {5, 1, 3};
int* i = &array[1];
++*i;
std::cout << i[0];
~~~
Что будет выведено в результате?
Ответ:
- [ ] 1
- [ ] Ошибка
- [ ] 3
- [x] 2
- [ ] 5

---

Где можно объявить структуру в языке С++?
Ответ:
- [ ] Внутри списка параметров функции;
- [x] Вне функции;
- [x] Внутри других структур;
- [ ] Там, где указан возвращаемый тип функции;
- [x] Внутри тела функции;

---

Дан фрагмент кода на С++. Что отобразится на экране после его выполнения?
~~~cpp
int a = 5;
int b = 15;
if (a < b); std::cout << a;
else; std::cout << b;
~~~
Ответ:
- [x] Ошибка компиляции
- [ ] 5
- [ ] 515
- [ ] Ничего
- [ ] 155
- [ ] 15

---

Дан фрагмент кода на С++. Как инстанцировать данный шаблон?
~~~cpp
template<typename T>
T foo(T a, T b){
    auto res = a + b;
    return res;
}
~~~
Ответ:
- [x] foo<int>(3.0, 0.1415);
- [ ] foo<double, double>(3.0, 0.1415);
- [ ] foo(3.0, 0);
- [x] foo(3.0, 0.1415);
- [ ] foo<double, double, double>(3.0, 0.1415);
- [ ] foo(3, 0.1415);
- [x] foo<double>(3, 0.1415);
- [x] foo(3, 0);

---

Дан фрагмент кода на С++. Что будет выведено на экран в результате выполнения данного фрагмента?
~~~cpp
int x = 5;
(x != 5) && (std::cout << 11);
std::cout << x;
~~~
Ответ: <code> 5 </code>

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
int i = 1;

namespace A {
    namespace B {
        int i = 2;
        void print() {
            std::cout << i;
        }
    }
}

int main() {
    int i = 3;
    A::B::print();
}
~~~
Ответ:
- [x] 2
- [ ] 1
- [ ] Ошибка
- [ ] 3

---

Язык Go. Пакет импортирован следующим образом:
~~~go
import . "github.com/vigo5190/example/name"
~~~
Каким образом можно использовать экспортируемые имена из этого пакета в своём коде?
Ответ:
- [ ] Имя из пакета name можно использовать так: name.требуемое_имя
- [x] Имена объявленные в пакете name доступны для использования просто по своему имени
- [ ] Имя из пакета name можно использовать так: example.требуемое_имя
- [ ] Имена объявленные в пакете name НЕ доступны для использования

---

Язык Go. Дана структура и указатель на неё:
~~~go
type Data struct{
    value int
}

var a *Data = &Data{10}
~~~
Выберите все способы получить доступ к полю value через указатель a.
Ответ:
- [ ] a*.value
- [ ] a->value
- [x] a.value
- [x] (*a).value
- [ ] a.*value
- [ ] *a.value

---

Дана функция на языке Go. Выберите все верные утверждения:
~~~go
func mydiv(a, b int) *int{
    result := a % b
    return &result
}
~~~
При условии, что функция вызывается так:
~~~go
x, y := 9, 2
z := mydiv(x, y)
~~~
Ответ:
- [x] Функция возвращает результат по указателю;
- [ ] В точке вызова будет создана копия локальной переменной result;
- [ ] В точке вызова будет получен адрес по которому лежала переменная result во время работы функции mydiv, но была уделена во время выхода из функции;
- [x] В точке вызова будет получен адрес по которому лежит переменная result;
- [ ] Функция возвращает результат по значению;

---

Дана функция на языке С++. Выберите все варианты вызова данной функции, при которых произойдёт обмен значениями переменных x и y. Переменные объявлены следующим образом: int x = 1; и int y = 2;:
~~~cpp
void swap(int a, int b){
    int t = a;
    a = b;
    b = t;
}
~~~
Ответ:
- [ ] swap(&x, &y);
- [ ] swap(y, x);
- [ ] swap(x, y);
- [ ] swap(*x, *y);
- [x] Эта функция не может выполнить требуемое действие;

---

Дан фрагмент кода на С++. Что отобразится на экране после его выполнения?
~~~cpp
int a = 50;
int b = 15;
if (a > b) std::cout << a;
else; std::cout << b;
~~~
Ответ: <code> 5015 </code>

---

Язык Go. В текущий пакет из пакета other была импортирована структура:
~~~go
type Book struct {
    Title       string
    author      string
    Description string
    Price       int
    pages       int
}
~~~
Какие поля будут доступны для использования в текущем пакете?
Ответ:
- [ ] author
- [x] Price
- [x] Title
- [ ] pages
- [x] Description

---

Как обозначается l-value ссылка на значение типа int в С++?
Ответ:
- [ ] int**
- [ ] int*
- [x] int&
- [ ] int^
- [ ] int&&
- [ ] int^^

---

Язык С++. Что из нижеперечисленного приведёт к объявлению структуры?
Ответ:
<ul>
<li>- [x] <li>

~~~cpp
struct {
    int a;
} s;
~~~
</li></li>

<li>- [ ] <li>

~~~cpp
struct a_struct int a;
~~~
</li></li>

<li>- [x] <li>

~~~cpp
struct a_struct{
    int a;
};
~~~
</li></li>

<li>- [ ] <li>

~~~cpp
struct {
    int a;
}
~~~
</li></li>

<li>- [ ] <li>

~~~cpp
struct a_struct {
    int a;
}
~~~
</li></li>
</ul>




