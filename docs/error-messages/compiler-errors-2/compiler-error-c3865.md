---
title: Compilerfehler C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 846657d3598e268d78ff3c39f2bfc901756ad370
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302019"
---
# <a name="compiler-error-c3865"></a>Compilerfehler C3865

'Aufrufkonvention': kann nur für systemeigene Memberfunktionen verwendet werden

Eine Aufrufkonvention wurde verwendet, auf eine Funktion, die entweder eine globale Funktion oder in einer verwalteten Memberfunktion. Die Aufrufkonvention kann nur in einer systemeigenen (nicht verwaltete) Memberfunktion verwendet werden.

Weitere Informationen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).

Im folgende Beispiel wird die C3865 generiert:

```
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```