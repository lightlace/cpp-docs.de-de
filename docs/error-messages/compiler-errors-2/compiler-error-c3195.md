---
title: Compilerfehler C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: c8274e121e953c3e51a0f2ff8c68c315759ce3e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760425"
---
# <a name="compiler-error-c3195"></a>Compilerfehler C3195

"operator" : ist reserviert und kann nicht als Member einer Verweisklasse oder eines Werttyps verwendet werden. CLR- oder WinRT-Operatoren müssen mit dem Schlüsselwort "operator" definiert werden.

Der Compiler hat eine Operatordefinition gefunden, in der die Managed Extensions for C++-Syntax verwendet wird. Sie müssen die C++ Syntax für Operatoren verwenden.

Im folgenden Beispiel wird C3195 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```
