---
title: Compilerfehler C3698
ms.date: 11/04/2016
f1_keywords:
- C3698
helpviewer_keywords:
- C3698
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
ms.openlocfilehash: 78cded92c8f73c77f7871278443bd3dfd4dbe686
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529297"
---
# <a name="compiler-error-c3698"></a>Compilerfehler C3698

'Typ': Verwenden Sie diesen Typ kann nicht als Argument von 'Operator'

Ein verwaltetes Objekt wurde falsch deklariert.

Im folgende Beispiel wird die C3698 generiert:

```
// C3698.cpp
// compile with: /clr

int main() {
   array<int>^a = new array<int>^(20);   // C3698
   array<int>^a2 = gcnew array<int>(20);   // OK
}
```