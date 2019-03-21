---
title: Compilerfehler C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 59b2f63ba12a644f13b3586fbf6eec4d5bfa8be5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604190"
---
# <a name="compiler-error-c2939"></a>Compilerfehler C2939

'Klasse': Typ-Klassen-Id wird als lokale Datenvariable neu definiert.

Eine generische oder Vorlagenklasse kann nicht als lokale Datenvariable verwendet werden.

Dieser Fehler wird möglicherweise verursacht, wenn geschweifte Klammern nicht korrekt übereinstimmen.

Im folgenden Beispiel wird C2939 generiert:

```
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

C2939 kann auch auftreten, wenn Generics verwendet werden:

```
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```