---
title: Compilerfehler C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 34d19e8e9f51c90c48ec0d429f98bb82e3d829d4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778909"
---
# <a name="compiler-error-c2750"></a>Compilerfehler C2750

'Typ': kann nicht für den Verweistyp zu "new" verwendet Verwenden Sie stattdessen "Gcnew"

Um eine Instanz eines CLR-Typs zu erstellen, der bewirkt, die Instanz auf dem Heap der Garbage collection platziert werden kann dass, müssen Sie verwenden [Gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md).

Im folgende Beispiel wird die C2750 generiert:

```
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```