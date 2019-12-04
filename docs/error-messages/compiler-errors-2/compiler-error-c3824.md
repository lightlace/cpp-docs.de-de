---
title: Compilerfehler C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: 47363da66416c326755cad12fe4cfd448e3154e2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741728"
---
# <a name="compiler-error-c3824"></a>Compilerfehler C3824

"Member": dieser Typ kann nicht in diesem Kontext (Funktionsparameter, Rückgabetyp oder statischer Member) vorkommen.

Das Fixieren von Zeigern kann nicht Funktionsparameter, Rückgabe Typen oder deklarierte `static`sein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3824 generiert:

```cpp
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
