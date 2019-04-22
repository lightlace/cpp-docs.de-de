---
title: Compilerfehler C3255
ms.date: 11/04/2016
f1_keywords:
- C3255
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
ms.openlocfilehash: 129d2698a782d2b98267877e8d575a6ee641b94b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778214"
---
# <a name="compiler-error-c3255"></a>Compilerfehler C3255

"Werttyp": Werttypobjekt auf systemeigenem Heap kann nicht dynamisch zuordnen

Instanzen eines Werttyps (finden Sie unter [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md)), die verwaltete Elemente enthalten kann auf dem Stapel, aber nicht auf dem Heap erstellt werden.

Im folgende Beispiel wird die C3255 generiert:

```
// C3255.cpp
// compile with: /clr
using namespace System;
value struct V {
   Object^ o;
};

value struct V2 {
   int i;
};

int main() {
   V* pv = new V;   // C3255
   V2* pv2 = new V2;
   V v2;
}
```
