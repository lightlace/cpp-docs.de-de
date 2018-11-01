---
title: Compilerfehler C2672
ms.date: 10/24/2017
f1_keywords:
- C2672
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
ms.openlocfilehash: df0f656c9db23739ec62629088b9cc5f7950a92d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570442"
---
# <a name="compiler-error-c2672"></a>Compilerfehler C2672

> "*Funktion*": keine übereinstimmende überladene Funktion gefunden.

Der Compiler keine überladene Funktion gefunden, die die angegebene Funktion entspricht. Keine Funktion gefunden, übereinstimmender Parameter oder keine entsprechende Funktion nimmt den erforderlichen Zugriff in Kontext hat.

Wenn durch bestimmte-standardbibliothekscontainer oder Algorithmen verwendet, müssen die Typen angeben, zugängliche Member oder Friend-Funktionen, die die Anforderungen des Containers oder des-Algorithmus zu erfüllen. Z. B. die iteratortypen ableiten sollten `std::iterator<>`. Vergleichsvorgänge oder die Verwendung von anderen Operatoren auf Elementtypen für Container unter Umständen der Typ als einen linken und einen rechtsseitigen Operanden betrachtet werden. Verwenden des Typs, wie ein rechtsseitigen Operanden Implementierung des Operators als Funktion nicht-Member des Typs erforderlich sein kann.

## <a name="example"></a>Beispiel

Die Versionen des Compilers vor dem Zugriff auf qualifizierte Namen in bestimmten Kontexten von Vorlagen von Visual Studio 2017 nicht ausgeführt haben. Das erwartete SFINAE-Verhalten kann behindert werden, in dem die Ersetzung aufgrund der Nichterreichbarkeit des Namens erwartungsgemäß fehlschlägt. Dies kann potenziell einen Absturz oder unerwartetes Verhalten zur Laufzeit auslösen, da der Compiler fälschlicherweise die falsche Überladung des Operators aufgerufen hat. In Visual Studio 2017 wird ein Compilerfehler ausgelöst.

In diesem Beispiel wird in Visual Studio 2015 kompiliert, aber löst einen Fehler in Visual Studio 2017. Um dieses Problem zu beheben, stellen Sie das Element der Vorlage Parameter zugegriffen werden kann, in dem sie ausgewertet wird.

```cpp
#include <type_traits>

template <class T> class S {
// public:    // Uncomment this line to fix
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x)
{
    return (x == 0);
}

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```