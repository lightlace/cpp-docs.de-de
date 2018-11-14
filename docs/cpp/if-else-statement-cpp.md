---
title: if-else-Anweisung (C++)
ms.date: 07/17/2017
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 16aa65ab64d9fd855ae3306da88f8eb14eec759c
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330827"
---
# <a name="if-else-statement-c"></a>if-else-Anweisung (C++)

Steuert den bedingten Branch. Anweisungen in der *If-Block* werden nur ausgeführt, wenn die *If-Ausdruck* ergibt einen Wert ungleich Null (oder "true"). Wenn der Wert des *Ausdruck* ungleich NULL ist, *statement1* und alle anderen Anweisungen im Block ausgeführt werden, und der else-Block, falls vorhanden, wird übersprungen. Wenn der Wert des *Ausdruck* 0 (null), wird der If-Block wird übersprungen, und der else-Block, falls vorhanden, wird ausgeführt. Ausdrücke, die ungleich NULL ausgewertet, werden.

- true
- ein nicht-Null-Zeiger ist,
- alle arithmetischen Wert ungleich NULL, oder
- Geben Sie ein Klassentyp, der eine eindeutige Konvertierung in ein arithmetischer "," Boolean "oder" Zeiger definiert. (Weitere Informationen über Konvertierungen finden Sie unter [Standardkonvertierungen](../cpp/standard-conversions.md).)

## <a name="syntax"></a>Syntax

```cpp
if ( expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
}
```

## <a name="example"></a>Beispiel

```cpp
// if_else_statement.cpp
#include <iostream>

using namespace std;

class C
{
    public:
    void do_something(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

    // no else statement
    if (x == 10)
    {
        x = 0;
    }

    C* c;
    init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```

## <a name="if_with_init"></a> Wenn die Anweisung mit einem Initialisierer

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): ein **Wenn** Anweisung enthält möglicherweise auch einen Ausdruck, der deklariert und initialisiert eine benannte Variable. Verwenden Sie diese Form der If-Anweisung aus, wenn die Variable nur innerhalb des Bereichs der If-Block erforderlich ist.

## <a name="example"></a>Beispiel

```cpp
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>

using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }

    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }
}
```

In allen Arten von der **Wenn** Anweisung *Ausdruck*, die einen beliebigen Wert außer einer Struktur verfügen können ausgewertet wird, einschließlich aller Nebeneffekte. Wird die Steuerung von der **Wenn** Anweisung, um die nächste Anweisung im Programm, wenn eines der *Anweisung*s enthält eine [Break](../cpp/break-statement-cpp.md), [weiterhin](../cpp/continue-statement-cpp.md), oder [Goto](../cpp/goto-statement-cpp.md).

Die **else** -Klausel eine `if...else` Anweisung bezieht sich auf die nächstgelegene vorherigen **Wenn** -Anweisung im gleichen Gültigkeitsbereich, der einen entsprechenden keinen **else** -Anweisung.

## <a name="a-nameifconstexpr-if-constexpr-statements"></a><a name="if_constexpr"> Wenn "constexpr"-Anweisungen

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): In Funktionsvorlagen, können Sie eine **Wenn "constexpr"** Anweisung, damit Verzweigungen Entscheidungen treffen zu kompilieren auf mehreren funktionsüberladungen zurückgreifen müssen. Beispielsweise können Sie einer einzelnen Funktion schreiben, diese Handles Parameter Entpacken (keine Überladung für die NULL-Parameter ist erforderlich):

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
    // handle t
    do_something(t);

    // handle r conditionally
    if constexpr (sizeof...(r))
    {
        f(r...);
    }
    else
    {
        g(r...);
    }
}
```

## <a name="see-also"></a>Siehe auch

[Auswahlanweisungen](../cpp/selection-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[switch-Anweisung (C++)](../cpp/switch-statement-cpp.md)