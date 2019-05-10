---
title: Nicht dem Standard entsprechendes Verhalten
ms.date: 05/06/2019
helpviewer_keywords:
- compatibility and compliance, nonstandard behavior
- Microsoft-specific, compiler behavior
- nonstandard behavior, compliance and compatibility
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
ms.openlocfilehash: 82c5faae68f9da747017119d76578cc88163d8bb
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222027"
---
# <a name="nonstandard-behavior"></a>Nicht dem Standard entsprechendes Verhalten

Den folgenden Abschnitten werden einige Bereiche, in denen die Microsoft-Implementierung von C++ stimmt nicht überein, mit der C++ standard. Die unten angegebenen Abschnittszahlen beziehen sich auf die Abschnittszahlen im C++ 11-Standard (ISO/IEC 14882:2011(E)).

Die Liste der Compiler-Grenzen, die von den in der C++-Standard definierten abweichen erhält [Compiler-Grenzen](../cpp/compiler-limits.md).

## <a name="covariant-return-types"></a>Kovariante Rückgabetypen

Virtuelle Basisklassen werden nicht als kovariante Rückgabetypen unterstützt, wenn die virtuelle Funktion eine variable Anzahl von Argumenten hat. Dies entspricht nicht Abschnitt 10.3, Absatz 7 der C++ ISO-Spezifikation. Im folgende Beispiel wird nicht kompiliert, sodass Compilerfehler [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md)

```cpp
// CovariantReturn.cpp
class A
{
   virtual A* f(int c, ...);   // remove ...
};

class B : virtual A
{
   B* f(int c, ...);   // C2688 remove ...
};
```

## <a name="binding-nondependent-names-in-templates"></a>Bindung von nicht abhängigen Namen in Vorlagen

Microsoft C++ Compiler unterstützt derzeit nicht von nicht abhängigen Namen bei der Vorlage anfänglich analysiert. Dies entspricht nicht Abschnitt 14.6.3, Absatz 7 der C++ ISO-Spezifikation. Das kann zu Überladungen führen, die deklariert werden, nachdem die Vorlage (aber bevor die Vorlage instanziiert wird) angezeigt werden kann.

```cpp
#include <iostream>
using namespace std;

namespace N {
   void f(int) { cout << "f(int)" << endl;}
}

template <class T> void g(T) {
    N::f('a');   // calls f(char), should call f(int)
}

namespace N {
    void f(char) { cout << "f(char)" << endl;}
}

int main() {
    g('c');
}
// Output: f(char)
```

## <a name="function-exception-specifiers"></a>Funktionsausnahmebezeichner

Funktionsausnahmebezeichner mit Ausnahme von `throw()` werden analysiert, aber nicht verwendet. Dies entspricht nicht Abschnitt 15.4 der C++ ISO C++-Spezifikation. Zum Beispiel:

```cpp
void f() throw(int); // parsed but not used
void g() throw();    // parsed and used
```

Weitere Informationen zu Ausnahmespezifikationen finden Sie unter [Ausnahmespezifikationen](../cpp/exception-specifications-throw-cpp.md).

## <a name="chartraitseof"></a>char_traits::eof()

Die C++ -Standard gibt an, die [char_traits:: EOF](../standard-library/char-traits-struct.md#eof) muss nicht entsprechen, die eine gültige `char_type` Wert. Microsoft C++ Compiler erzwingt diese Einschränkung für Typ **Char**, jedoch nicht für Typ **"wchar_t"**. Dies entspricht nicht der Anforderung in Tabelle 62, in Abschnitt 12.1.1 der C++ ISO-Spezifikation. Das unten gezeigte Beispiel veranschaulicht dies.

```cpp
#include <iostream>

int main()
{
    using namespace std;

    char_traits<char>::int_type int2 = char_traits<char>::eof();
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;

    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;
}
```

## <a name="storage-location-of-objects"></a>Speicherort für Objekte

Der C++-Standard (Abschnitt 1,8, Absatz 6) erfordert vollständige C++-Objekte, um eindeutige Speicherpositionen zu haben. Jedoch mit Microsoft C++, es gibt Fälle, in denen Typen ohne Datenmember einen Speicherort mit anderen Typen für die Lebensdauer des Objekts freigeben werden.