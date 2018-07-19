---
title: Compilerfehler Fehler C2672 | Microsoft Docs
ms.date: 10/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2672
dev_langs:
- C++
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98c569c8b9b1466f184b44d345e76341d1476935
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236117"
---
# <a name="compiler-error-c2672"></a>Compilerfehler Fehler C2672

> "*Funktion*': kein passendes überladene Funktion gefunden

Der Compiler keine überladene Funktion gefunden, die die angegebene Funktion entspricht. Es wurde keine Funktion gefunden, dass übereinstimmender Parameter oder keine entsprechende Funktion übernimmt den erforderlichen Zugriff im Kontext verfügt.

Bei Verwendung durch bestimmte standardbibliothekscontainer oder Algorithmen müssen die Typen angeben, zugängliche Member oder Friend-Funktionen, die die Anforderungen des Containers oder des Algorithmus zu erfüllen. Z. B. die iteratortypen ableiten sollte `std::iterator<>`. Vergleichsoperationen oder nutzen von anderen Operatoren auf Elementtypen für Container möglicherweise der Typ als eine linke und eine rechter Operand betrachtet werden. Verwenden des Typs, wie ein rechter Operand des Operators als nicht-Memberfunktion des Typs Implementierung kann.

## <a name="example"></a>Beispiel

Compilerversionen vor Visual Studio 2017 Zugriff, die Prüfung auf qualifizierte Namen in bestimmten Kontexten für die Vorlage nicht ausgeführt werden. Das erwartete SFINAE-Verhalten kann behindert werden, in dem die Ersetzung aufgrund der Nichterreichbarkeit des Namens erwartungsgemäß fehlschlägt. Dies kann potenziell einen Absturz oder unerwartetes Verhalten zur Laufzeit auslösen, da der Compiler fälschlicherweise die falsche Überladung des Operators aufgerufen hat. In Visual Studio 2017 wird ein Compilerfehler ausgelöst.

In diesem Beispiel in Visual Studio 2015 kompiliert wird, aber löst einen Fehler in Visual Studio 2017 aus. Um dieses Problem zu beheben, stellen Sie die Vorlage Parameterelements zugegriffen werden kann, in denen ausgewertet.

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