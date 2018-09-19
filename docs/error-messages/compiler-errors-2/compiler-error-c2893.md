---
title: Compilerfehler C2893 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2893
dev_langs:
- C++
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73d4f838f030db3667b08295006c2ea1df94c87b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026178"
---
# <a name="compiler-error-c2893"></a>Compilerfehler C2893

Fehler beim spezialisieren der Funktionsvorlage "Vorlagenname"

Der Compiler konnte nicht spezialisiert werden eine Funktionsvorlage. Es kann viele Ursachen für diesen Fehler sein.

Im Allgemeinen ist die Möglichkeit, einen C2893 Fehler zu beheben, überprüfen die Signatur der Funktion, und stellen Sie sicher, dass Sie jeden Typ instanziieren können.

## <a name="example"></a>Beispiel

C2893 tritt auf, weil `f`der Vorlagenparameter `T` abgeleitet wird, um `std::map<int,int>`, aber `std::map<int,int>` weist keinen Member `data_type` (`T::data_type` kann nicht instanziiert werden, mit `T = std::map<int,int>`.). Im folgende Beispiel wird C2893 generiert.

```
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