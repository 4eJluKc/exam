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

---

Язык С++. Выберите все допустимые варианты создания ссылок.

Ответ:
- [x] int& b = /* инициализатор */;
- [ ] int& c[10] = /* инициализатор */;
- [ ] void& a = /* инициализатор */;
- [x] int& *f = /* инициализатор */;
- [x] int (&d)[10] = /* инициализатор */;
- [ ] int* &e = /* инициализатор */;

---

Выберите все выражения, которые не вызовут ошибку, при условии, что переменная a объявлена как:
~~~cpp
int a = 4;
~~~

Ответ:
- [ ] int&& r6 = r1;
- [ ] int&& r2 = a;
- [x] int& r1 = a;
- [x] int& r5 = r1;
- [x] int& r7 = r4;
- [x] int&& r4 = a + 1;
- [ ] int& r3 = a + 1;
- [ ] int&& r8 = r4;

---

Дан фрагмент кода на языке С++. Что выведется на экран в результате его работы?
~~~cpp
enum Color {
    YELLOW,
    BLACK,
    PINK,
    GREEN
};

int BLACK = 0;
Color color = Color::BLACK;
std::cout << color;
~~~

Ответ:
- [ ] 0
- [ ] Строка BLACK
- [ ] Ошибка. Для Color не определён оператор <<
- [x] Ошибка. Повторное объявление имени BLACK
- [ ] 1

---

Дан код на языке Go:
~~~go
#include <iostream>
#include <map>

void add(std::map<int, int> c, int value){
    c[c.size()] = value;
}

int main(){
    std::map<int, int> container;
    add(container, 10);
    std::cout << container.size();
}
~~~

В результате его исполнения:

Ответ:
- [ ] Переменная container изменится;
- [x] Переменная container не изменится;
      
---

Дан фрагмент кода на C++. Что будет выведено на экран в результате выполнения данного фрагмента кода?
~~~cpp
for(int i=0; i < 20; i += 3) cout << i;
~~~

Ответ: <code> 0369121518 </code>

---

Что будет выведено на экран в результате работы этого кода?
~~~cpp
#include <iostream>

void foo(int& a){
    std::cout << "+" << std::endl;
}

void foo(int&& a){
    std::cout << "-" << std::endl;
}

int main(){
    int a = 4;
    foo(a + 1);
}
~~~

Ответ:
- [ ] +
- [x] -

---

Язык С++. Переменная-указатель p хранит адрес некоторой переменной i. Как получить доступ к значению переменной i по её адресу?

Ответ:
- [ ] Применить к p оператор взятия адреса
- [x] Применить к p оператор разыменования
- [ ] Применить к p оператор разрешения контекста
- [ ] Просто использовать в выражениях p вместо i

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
int A = 1;

int A(){
    return 2;
}

int main() {
    std::cout << A();
}
~~~

Ответ:
- [x] Ошибка
- [ ] 1
- [ ] 2

---

Дан фрагмент кода на языке С++. Что будет на экране в результате выполнения данного фрагмента?
~~~cpp
struct А{
    A(int value){
        this->value = value;
    }
    int value = 1;
};

struct B: A{
    B(int value){
        this->value = value;
    }
};

B obj(5);
std::cout << obj.value;
~~~

Ответ:
- [ ] 1
- [ ] 5
- [x] Ошибка

---

Язык Go. Дан фрагмент кода:
~~~go
i, j := 1, 1
~~~

Требуется изменить значение переменной i. Выберите все варианты, которыми это можно сделать.

Ответ:
- [ ] i, j := 2, 2
- [ ] i, _ := 2, 2
- [x] i, k := 2, 2
- [x] i, j = 2, 2

---

Язык С++. Что из нижеперечисленного может быть полем структуры?

Ответ:
- [x] Структуры и Классы;
- [x] Фундаментальные типы (int, double, ...);
- [x] Указатели;
- [x] Строки;
- [x] Массивы;

---

Язык Go. Что будет доступно по имени j в следующем коде?
~~~go
str := "hello, world"
for i, j := range str{
    fmt.Println(i, j)
}
~~~

Ответ:
- [x] Копия символа из строки
- [ ] Индекс символа в строке
- [ ] Указатель на символ в строке
- [ ] Указатель на индекс символа в строке

---

Язык С++. Выберите все верные утверждения:

Ответ:
- [x] sizeof(int *) == sizeof(vector<int*> *)
- [x] sizeof(int *) == sizeof(double *)
- [x] sizeof(int *) == sizeof(vector<int> *)
- [ ] Нет верных утверждения
- [x] sizeof(int *) == sizeof(void *)

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
namespace A {
    namespace B {
        void print() {
            std::cout << i;
        }
    }
}

int main() {
    int i = 1;
    A::B::print();
}
~~~

Ответ:
- [x] Ошибка
- [ ] 1

---

Язык С++. Что из перечисленного может быть использовано в качестве объявления конструктора по умолчанию для класса SomeClass?

Ответ:
- [x] SomeClass() = default;
- [ ] SomeClass(int a){}
- [ ] default SomeClass(){}
- [x] SomeClass(){}
- [x] SomeClass(int a=0, int b=0){}
- [ ] SomeClass(int a) = default;

---

Дан фрагмент кода на С++. Что отобразится на экране после его выполнения?
~~~cpp
class Point{
    ~Point(){}
};
 
int main(){
    Point p;
    std::cout << sizeof(p);
}
~~~

Ответ:
- [ ] 2
- [ ] 1
- [ ] 4
- [x] Ошибка. Не доступен деструктор
- [ ] 8
- [ ] 0

---

Что такое горутина в Go?

Ответ:
- [ ] Функция, которая может быть вызвана только один раз
- [x] Легковесный поток выполнения
- [ ] Объект, который управляет памятью
- [ ] Переменная, хранящая данные
- [ ] Поток с приоритетом

---

Даны фрагменты кода на С++. Результатом каких выражений будет true?

Ответ:
- [ ] !(5 == 4) && 10 < 10;
- [ ] 5 == 4 && 10 < 11;
- [x] !0 != 0;
- [ ] true && !true || 0;
- [x] 5 == 4 || 10 < 11;
- [ ] 0 && 3 || 0 && 3;

---

Дан фрагмент кода на С++. Что отобразится на экране после его выполнения?
~~~cpp
void print(int a){
    std::cout << a;
}

void print(double& a){
    std::cout << 99;
}

int main()
{
    double i = 0.5;
    print(i);
}
~~~

Ответ:
- [ ] 0
- [x] 99
- [ ] Ошибка компиляции
- [ ] 0.5

---

Язык С++. Что будет напечатано в результате исполнения следующего кода?
~~~cpp
#include <iostream>

class A{
public:
    void get(){
        std::cout << 'A';
    }
};

class B: public A{
public:
    virtual void get(){
        std::cout << 'B';
    }
};

class C: public B{
public:
    virtual void get(){
        std::cout << 'C';
    }
};

int main(){
    C* obj = new A;
    obj->get();
}
~~~

Ответ:
- [ ] B
- [ ] C
- [ ] A
- [x] Ошибка

---

Дан фрагмент кода на Go. Сколько раз выполнится цикл?
~~~go
k := 10
for k != 0 { 
    fmt.Print(1)
    k -= 1
}
~~~

Ответ: <code> 10 </code>

---

Дан фрагмент кода на С++
~~~cpp
int a, b, c = (1, 2, 3);
~~~

Выберите все верные утверждения.

Ответ:
- [x] переменная b содержит мусорное значение;
- [x] переменная c содержит 3;
- [ ] переменная c содержит мусорное значение;
- [ ] переменная c содержит 1;
- [ ] переменная a содержит 3;
- [x] переменная a содержит мусорное значение;
- [ ] переменная a содержит 1;
- [ ] переменная b содержит 2;

---

Дан фрагмент кода на С++. Что будет содержать переменная container после его выполнения?
~~~cpp
std::map<std::string, int> container{{"1", 2}, {"3", 2}};
container[-1] = 5;
~~~

Ответ:
- [ ] Пары: -1:5, 1:2, 3:2
- [x] Ошибка компиляции - недопустимый тип
- [ ] Пары: 1:2, 3:2, -1:5
- [ ] Ошибка доступа - указанного элемента не существует
- [ ] Пары: 1:2, 3:2, 5:-1

---

Дан фрагмент кода на языке С++. Что будет на экране в результате выполнения данного фрагмента?
~~~cpp
class A{
public:
    void get(){
        std::cout << 'A';
    }
};

class B{
public:
    void get(){
        std::cout << 'B';
    }
};

class C: public B, public A{
public:
    void get(){
        B::get();
    }
};

C obj;
obj.get();
~~~

Ответ:
- [x] B
- [ ] AB
- [ ] C
- [ ] BA
- [ ] A
- [ ] Ошибка

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
namespace A{
    int i = 1;
}

int main() {
    using A::i;
    int i = 2;
    std::cout << i;
}
~~~

Ответ:
- [x] Ошибка
- [ ] 2
- [ ] 1

---

Язык Go. Выберите все верные утверждения касающиеся оператора return в теле функции:

Ответ:
- [x] Прерывает исполнение функции и возвращает поток исполнения в точку вызова;
- [x] Может быть указан в теле функции более одного раза;
- [x] Может отсутствовать в некоторых функциях;
- [ ] Может быть указан в теле функции только один раз;
- [ ] Определяет позицию в теле функции, в которую нужно будет вернуться и продолжить выполнение при следующем её вызове;

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
namespace A{
    int i = 1;
}

int i = 2;

int main() {    
    std::cout << i;
}
~~~

Ответ:
- [ ] Ошибка
- [ ] 2
- [ ] 1

---

Дан фрагмент кода на С++. Каким образом можно получить доступ к полю x переменной p?
~~~cpp
struct Point{
    double x, y;
} p;
~~~

Ответ:
- [ ] p>x;
- [ ] p~x;
- [ ] p<-x;
- [ ] p-x;
- [ ] p->x;
- [x] p.x;

---

Дан фрагмент кода на языке С++:
~~~cpp
int* p = new int{5};
~~~

Какой оператор нужно использовать, чтобы освободить выделенную память?

Ответ:
- [ ] free(p);
- [x] delete p;
- [ ] delete[5] p;
- [ ] delete[] p;

---

Дан фрагмент кода на C++. Что будет выведено в результате выполнения следующего фрагмента кода:
~~~cpp
for (int i = 0; i < 4; ++i)
{
   switch (i)
   {
        case 0  : cout << "0";
        case 1  : cout << "1"; continue;
        case 2  : cout << "2"; break;
        default : cout << "D"; break;
   }
   cout << ".";
}
~~~

Ответ: <code> 0112.D. </code>

---

Язык С++. Дана структура:
~~~cpp
struct Point{
    int x,y;
};
~~~

Каким образом можно создать переменную типа Point?

Ответ:
- [x] Point p {1, 2};
- [ ] Point p();
- [ ] Point(1, 2) p;
- [x] Point p = {};
- [ ] Point p = [1, 1];
- [ ] Point p {x=1, y=1};
- [x] Point p = {1, 1};

---

Дан фрагмент кода на C++. Что будет выведено на экран после выполнения фрагмента кода?
~~~cpp
int i = 0;
for (int i = 5; i<11; i++);
  cout << i;
cout << i;
~~~

Ответ: <code> 56789100 </code>

---

Дан фрагмент кода на С++. Что будет содержать переменная container2 после его выполнения?
~~~cpp
std::set<int> container1{4, 3, 2, 1, 2, 3, 4};
std::vector<int> container2(container1.begin(), container1.end());
~~~

Ответ:
- [ ] 1, 2, 3, 4 но в порядке зависящем от хэш-функции
- [ ] 4, 3, 2, 1
- [ ] 4, 3, 2, 1, 2, 3, 4
- [x] 1, 2, 3, 4
- [ ] 4, 3, 2, 1, 2, 3, 4 но в порядке зависящем от хэш-функции

---

Каким образом можно преобразовать int* i в double* j ?

Ответ:
- [ ] j = static_cast<int*>(i);
- [x] Это невозможно сделать указанными способами
- [ ] j = (int*)i;
- [ ] j = static_cast<int>(i);
- [ ] j = (int)i;
- [ ] j = i;

---

Дан фрагмент кода на языке С++. Что будет напечатано в результате его выполнения?
~~~cpp
struct SomeClass{
    int i = 0;
    int j = 0;
    
    SomeClass(){
        i = 10;    
    }
    
    SomeClass(int value){
        SomeClass();
        j = value;
    }
};

SomeClass obj(10);
std::cout << obj.i << ' ' << obj.j;
~~~

Ответ:
- [ ] 10 10
- [ ] 10 0
- [x] 0 10
- [ ] 0 0

---

Дан фрагмент кода на С++. Что будет напечатано в результате его выполнения?
~~~cpp
namespace A{
    int i = 1;
}

int main() {
    using namespace A;
    std::cout << i;
    int i = 2;
}
~~~

Ответ:
- [ ] 2
- [ ] Ошибка
- [x] 1

---

Язык Go. Что делает оператор break вызванный внутри цикла?

Ответ:
- [x] Прерывает выполнение цикла
- [ ] Данный оператор игнорируется
- [ ] Заставляет цикл выполняться с самого начала
- [ ] Ошибка. Оператор break не используется в циклах
- [ ] Принудительный переход к следующей итерации цикла

---

Дан фрагмент кода на С++. Что будет содержать переменная container2 после его выполнения?
~~~cpp
std::vector<int> container1{4, 3, 2, 1, 2, 3, 4};
std::vector<int> container2(container1.begin(), container1.end());
~~~

Ответ:
- [ ] 1, 2, 3, 4
- [ ] 4, 3, 2, 1, 2, 3, 4 но в порядке зависящем от хэш-функции
- [ ] 4, 3, 2, 1
- [ ] 1, 2, 3, 4 но в порядке зависящем от хэш-функции
- [ ] 4, 3, 2, 1, 2, 3, 4

---

Язык C++. Что делает оператор continue вызванный внутри цикла?

Ответ:
- [ ] Прерывает выполнение цикла
- [ ] Заставляет цикл выполняться с самого начала
- [ ] Данный оператор игнорируется
- [x] Принудительный переход к следующей итерации цикла
- [ ] Ошибка. Оператор continue не используется в циклах

---

Язык С++. Где можно объявить/определить новый класс?

Ответ:
- [x] Внутри других классов
- [ ] В списке параметров функции
- [x] В глобальной области видимости
- [x] Внутри конструкции блок {}
- [x] В теле функции

---

Язык С++. Дано перечисление. Выберите все способы получения значения со стандартного ввода.
~~~cpp
enum Color {
    YELLOW = 0,
    BLACK = 1,
    PINK = 2
} color;
~~~

Ответ:

<ul>
<li>- [x] <li>

~~~cpp
int i;
std::cin >> i; // Пользователь вводит число: 0
color = static_cast<Color>(i);
~~~
</li></li>

<li>- [ ] <li>

~~~cpp
std::cin >> color; // Пользователь вводит число: 0
~~~
</li></li>

<li>- [ ] <li>

~~~cpp
std::string str;
std::cin >> str; // Пользователь вводит строку: YELLOW
color = static_cast<Color>(str);
~~~
</li></li>

<li>- [ ] <li>

~~~cpp
std::cin >> color; // Пользователь вводит строку: YELLOW
~~~
</li></li>

<li>- [x] <li>

~~~cpp
int i;
std::cin >> i; // Пользователь вводит число: 0
color = Color(i);
~~~
</li></li>
</ul>

---

Дан фрагмент кода на Go. Что будет выведено на экран в результате выполнения данного фрагмента кода?
~~~go
for i := 0; i < 20; i += 3 {
    fmt.Print(i)  
} 
~~~

Ответ: <code> 0369121518 </code>

---

Дан фрагмент кода на языке С++. Что будет на экране в результате выполнения данного фрагмента?
~~~cpp
struct А{
    int value = 1;
};

struct B: A{
    B(int value){
        this->value = value;
    }
};

B obj(5);
std::cout << obj.value;
~~~

Ответ: 
- [x] 5
- [ ] Ошибка
- [ ] 1

---

Даны фрагменты кода на Go. Результатом каких выражений будет true?

Ответ:
- [ ] 5 == 4 && 10 < 11
- [x] 5 == 4 || 10 < 11
- [ ] true && !true || false
- [ ] false && true || false && true
- [ ] !(5 == 4) && 10 < 10
- [x] !false != false

---

Дан фрагмент кода на С++. Что отобразится на экране после его выполнения?
~~~cpp
void print(int a){
    std::cout << -a;
}

void print(double a){
    std::cout << a;
}

int main()
{
    bool i = 10;
    print(i);
}
~~~

Ответ:
- [ ] 10
- [ ] -10
- [ ] 1
- [ ] Ошибка компиляции
- [x] -1

---

Дан фрагмент кода на C++. Сколько раз выполнится цикл?
~~~cpp
int k = 10;
while(k--) cout << 0;
~~~

Ответ: <code> 10 </code>

---

Дан фрагмент кода на Go. Что будет выведено на экран после выполнения фрагмента кода?
~~~go
i := 0
for i := 5; i < 11; i++{
    fmt.Print(i)
}
fmt.Print(i)
~~~

Ответ: <code> 56789100 </code>

---

Дан фрагмент кода на языке С++. Что будет на экране в результате выполнения данного фрагмента?
~~~cpp
struct А{
    int value = 1;
};

struct B: A{
    int value = 1;
    B(int value){
        this->value = value;
    }
};

B obj(5);
std::cout << obj.value;
~~~

Ответ:
- [ ] Ошибка
- [ ] 1
- [x] 5

---

Дан фрагмент кода на языке С++. Будет ли код работать?
~~~cpp
void print(short a, short b, std::string sep){
    std::cout << a << sep << b;
}

int main(){
    print(1, 2, " ");
}
~~~

Ответ:
- [x] Да. Ошибок нет;
- [ ] Да. Но будет вызвана функция print из библиотеки iostream;
- [ ] Нет. Ошибка на этапе исполнения;
- [ ] Нет. Ошибка на этапе компиляции;

---

Дана функция на языке С++. Выберите все верные утверждения:
~~~cpp
int min(int* a, int* b){
    return *a < *b ? *a : *b;
}
~~~

При условии, что функция вызывается так:
~~~cpp
int x = 10, y = 0;
min(&x, &y);
~~~

Ответ:
- [x] Функция принимает аргументы по указателю;
- [ ] Параметры функции становятся вторыми именами для переменных x и y;
- [ ] Параметры функции получают локальную копию аргументов;
- [ ] Функция принимает аргументы по ссылке;
- [ ] Функция принимает аргументы по значению;
- [x] Параметры функции получают адреса, по которым расположены переменные;

---

Дан фрагмент кода на С++. Каким образом можно создать один или несколько объектов класса Point?
~~~cpp
struct Point{
    Point(){}
};
~~~

Ответ:
- [x] class Point p;
- [x] new Point();
- [x] new Point;
- [x] Point p[10];
- [ ] Point p();
- [x] Point p;

---

Язык Go. Дан фрагмент кода:
~~~go
type A struct{
    value int
}

func (a A) get() int{
    return a.value
}

func (a A) set(val int){
    a.value = val
}

type Accessor interface{
    get() int
    set(val int)
}

func main() {
    var obj A
    g := Accessor(obj)
    g.set(10)
    
    fmt.Print(obj.get())
}
~~~

Ответ:
- [x] 0
- [ ] 10
- [ ] Ошибка

---

Дан фрагмент кода на С++. Что будет содержать переменная container после его выполнения?
~~~cpp
std::vector<int> container{1, 2, 3, 4};
container.insert(container.begin(), 4);
~~~

Ответ:
- [ ] 1, 2, 3, 4
- [ ] 1, 2, 3, 4, 4
- [ ] 4, 1, 2, 3 , 4
- [ ] 1, 2, 3, 4 но в порядке зависящем от хэш-функции



