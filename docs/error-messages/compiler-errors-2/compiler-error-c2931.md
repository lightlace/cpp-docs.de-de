---
title: Compilerfehler C2931
ms.date: 11/04/2016
f1_keywords:
- C2931
helpviewer_keywords:
- C2931
ms.assetid: 33430407-b149-4ba3-baf8-b0dae1ea3a5d
ms.openlocfilehash: 8fffa6e272da64ca7baa35af635b2b0a7d40c6f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661330"
---
# <a name="compiler-error-c2931"></a>Compilerfehler C2931

"Klasse": "Typ-Klassen-ID" wird als Memberfunktion von "Bezeichner" neu definiert.

Eine generische oder Vorlagenklasse kann nicht als Memberfunktion einer anderen Klasse verwendet werden.

Dieser Fehler kann dadurch verursacht werden, dass geschweifte Klammern nicht korrekt übereinstimmen.

Im folgenden Beispiel wird C2931 generiert:

```
// C2931.cpp
// compile with: /c
template<class T>
struct TC { };
struct MyStruct {
   void TC<int>();   // C2931
};

struct TC2 { };
struct MyStruct2 {
   void TC2();
};
```

C2931 kann auch auftreten, wenn Generics verwendet werden:

```
// C2931b.cpp
// compile with: /clr /c
generic<class T> ref struct GC {};
struct MyStruct {
   void GC<int>();   // C2931
   void GC2();   // OK
};
```