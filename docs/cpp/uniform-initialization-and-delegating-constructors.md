---
title: Einheitliche Initialisierung und Delegierung von Konstruktoren
ms.date: 11/04/2016
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
ms.openlocfilehash: 5c5cb6421d9c8ce20f0c5e24de986ee50d9b2238
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162108"
---
# <a name="uniform-initialization-and-delegating-constructors"></a>Einheitliche Initialisierung und Delegierung von Konstruktoren

In modernem C++ können Sie *geschweifter Klammern Initialisierung* für den beliebigen Typs, ohne das Gleichheitszeichen. Außerdem können Sie delegierende Konstruktoren verwenden, um den Code zu vereinfachen, wenn mehrere Konstruktoren ähnliche Aufgaben ausführen.

## <a name="brace-initialization"></a>Initialisierung mit geschweiften Klammern

Sie können die Initialisierung mit geschweiften Klammern für jede Klasse, Struktur oder Union verwenden. Wenn ein Typ einen Standardkonstruktor hat, der entweder implizit oder explizit deklariert wurde, können Sie die Standardinitialisierung mit geschweiften klammern verwenden (mit leeren Klammern). Beispielsweise kann die folgende Klasse durch Verwenden der standardmäßigen und nicht standardmäßigen Initialisierung mit geschweiften Klammern initialisiert werden:

```cpp
#include <string>
using namespace std;

class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}
double m_double;
string m_string;
};

int main()
{
    class_a c1{};
    class_a c1_1;

    class_a c2{ "ww" };
    class_a c2_1("xx");

    // order of parameters is the same as the constructor
    class_a c3{ "yy", 4.4 };
    class_a c3_1("zz", 5.5);
}
```

Wenn eine Klasse nicht standardmäßige Konstruktoren enthält, ist die Reihenfolge, in der Klassenmember im Initialisierer für geschweifte Klammern angezeigt werden, die Reihenfolge, in der die entsprechenden Parameter im Konstruktor angezeigt werden, und nicht die Reihenfolge, in der die Member deklariert werden (wie für `class_a` im vorherigen Beispiel). Wenn der Typ andernfalls keinen deklarierten Konstruktor hat, ist die Reihenfolge, in der die Member im Initialisierer für geschweifte Klammern angezeigt werden, dieselbe Reihenfolge, in der sie deklariert werden. In diesem Fall können Sie beliebig viele öffentliche Member initialisieren, Sie dürfen jedoch keinen Member überspringen. Das folgende Beispiel zeigt die Reihenfolge, die für die Initialisierung mit geschweiften Klammern verwendet wird, wenn kein deklarierter Konstruktor vorhanden ist:

```cpp
class class_d {
public:
    float m_float;
    string m_string;
    wchar_t m_char;
};

int main()
{
    class_d d1{};
    class_d d1{ 4.5 };
    class_d d2{ 4.5, "string" };
    class_d d3{ 4.5, "string", 'c' };

    class_d d4{ "string", 'c' }; // compiler error
    class_d d5("string", 'c', 2.0 }; // compiler error
}
```

Wenn der Standardkonstruktor explizit deklariert wird, jedoch als gelöscht markiert wurde, kann die Standardinitialisierung mit geschweiften Klammern nicht angewendet werden:

```cpp
class class_f {
public:
    class_f() = delete;
    class_f(string x): m_string { x } {}
    string m_string;
};
int main()
{
    class_f cf{ "hello" };
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function
}
```

Sie können die Initialisierung mit geschweiften Klammern an einer beliebigen Stelle Sie würden normalerweise eine Initialisierung durchführen – beispielsweise als Funktionsparameter oder Rückgabewert oder mit der **neue** Schlüsselwort:

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

## <a name="initializerlist-constructors"></a>initializer_list-Konstruktoren

Die [Initializer_list-Klasse](../standard-library/initializer-list-class.md) stellt eine Liste von Objekten eines angegebenen Typs, die in einem Konstruktor und in anderen Kontexten verwendet werden können. Sie können ein initializer_list-Objekt durch Verwenden der Initialisierung mit geschweiften Klammern erstellen:

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
>  Um diese Klasse verwenden zu können, müssen Sie enthalten die [ \<Initializer_list >](../standard-library/initializer-list.md) Header.

Ein `initializer_list`-Objekt kann kopiert werden. In diesem Fall sind die Member der neuen Liste Verweise auf die Member der ursprünglichen Liste:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

Die Standard-Bibliothekscontainerklassen sowie `string`, `wstring` und `regex` verfügen über `initializer_list`-Konstruktoren. Die folgenden Beispiele zeigen, wie die Initialisierung mit geschweiften Klammern mit diesen Konstruktoren durchgeführt wird:

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{'x', 'y', 'z'};
```

## <a name="delegating-constructors"></a>Delegierende Konstruktoren

Viele Klassen verfügen über mehrere Konstruktoren, die ähnliche Aufgaben ausführen, beispielsweise Parameter überprüfen:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c() {}
    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
        middle = my_middle < max && my_middle > min ? my_middle : 5;
    }
};
```

Sie können Codewiederholungen reduzieren, indem Sie eine Funktion hinzufügen, die die gesamte Validierung übernimmt. Der Code für `class_c` wäre jedoch einfacher zu verstehen und zu verwalten, wenn ein Konstruktor einen Teil der Aufgaben an einen anderen Konstruktor delegieren würde. Zum Hinzufügen von delegierenden Konstruktoren verwenden Sie die Syntax `constructor (. . .) : constructor (. . .)`:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) : class_c(my_max) {
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){
        middle = my_middle < max && my_middle > min ? my_middle : 5;
}
};
int main() {

    class_c c1{ 1, 3, 2 };
}
```

Während Sie das vorherige Beispiel schrittweise ausführen, achten Sie darauf, ob der `class_c(int, int, int)`-Konstruktor zuerst den `class_c(int, int)`-Konstruktor aufruft, der wiederum `class_c(int)` aufruft. Jeder der Konstruktoren führt nur die Aufgaben aus, die nicht von den anderen Konstruktoren ausgeführt werden.

Der erste Konstruktor, der aufgerufen wird, initialisiert das Objekt, sodass alle seine Member zu diesem Zeitpunkt initialisiert werden. Sie können Memberinitialisierungen nicht in einem Konstruktor durchführen, der an einen anderen Konstruktor delegiert wird, wie hier gezeigt:

```cpp
class class_a {
public:
    class_a() {}
    // member initialization here, no delegate
    class_a(string str) : m_string{ str } {}

    //can’t do member initialization here
    // error C3511: a call to a delegating constructor shall be the only member-initializer
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}

    // only member assignment
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string;
};
```

Im folgenden Beispiel wird die Verwendung von nicht statischen Datenmemberinitialisierern verdeutlicht. Wenn ein Konstruktor auch einen angegebenen Datenmember initialisiert, wird der Memberinitialisierer überschrieben:

```cpp
class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };
};

int main() {
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"
    int y = 4;
}
```

Die Konstruktordelegierungssyntax verhindert nicht die versehentliche Erstellung der Konstruktorrekursion, d. h. Constructor1 ruft Constructor2 auf, der wiederum Constructor1 aufruft. Es wird nur ein Fehler ausgelöst, wenn es zu einem Stapelüberlauf kommt. Sie müssen dafür sorgen, Zyklen zu vermeiden.

```cpp
class class_f{
public:
    int max;
    int min;

    // don't do this
    class_f() : class_f(6, 3){ }
    class_f(int my_max, int my_min) : class_f() { }
};
```