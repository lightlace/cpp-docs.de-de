---
title: Compilerfehler C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: ca603eb94d5d528a7fed15e0320e1f5d88bf0629
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760875"
---
# <a name="compiler-error-c2893"></a>Compilerfehler C2893

Fehler beim spezialisieren der Funktions Vorlage "Vorlagen Name".

Der Compiler konnte eine Funktions Vorlage nicht spezialisieren. Dieser Fehler kann viele Gründe haben.

Im Allgemeinen besteht die Möglichkeit zum Auflösen eines C2893-Fehlers darin, die Signatur der Funktion zu überprüfen und sicherzustellen, dass Sie jeden Typ instanziieren können.

## <a name="example"></a>Beispiel

C2893 tritt auf, weil `f`Vorlagen Parameter `T` als `std::map<int,int>`abgeleitet wurde, `std::map<int,int>` aber keinen Member `data_type` hat (`T::data_type` kann nicht mit `T = std::map<int,int>`instanziiert werden.). Im folgenden Beispiel wird C2893 generiert.

```cpp
// C2893.cpp
// compile with: /c /EHsc
#include<map>
using namespace std;
class MyClass {};

template<class T>
inline typename T::data_type
// try the following line instead
// inline typename  T::mapped_type
f(T const& p1, MyClass const& p2);

template<class T>
void bar(T const& p1) {
    MyClass r;
    f(p1,r);   // C2893
}

int main() {
   map<int,int> m;
   bar(m);
}
```
