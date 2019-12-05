---
title: Aufrufbeispiel:Funktionsprototyp und Aufruf
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: cbe9ee16db502c9e27dcbd74da4ef6a85f00960f
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857631"
---
# <a name="calling-example-function-prototype-and-call"></a>Aufrufbeispiel:Funktionsprototyp und Aufruf

**Microsoft-spezifisch**

Das folgende Beispiel zeigt die Ergebnisse eines Funktionsaufrufs mit unterschiedlichen Aufrufkonventionen.

Dieses Beispiel basiert auf dem folgenden Funktionsskelett. Ersetzen Sie `calltype` durch die entsprechende Aufrufkonvention.

```cpp
void    calltype MyFunc( char c, short s, int i, double f );
.
.
.
void    MyFunc( char c, short s, int i, double f )
    {
    .
    .
    .
    }
.
.
.
MyFunc ('x', 12, 8192, 2.7183);
```

Weitere Informationen finden Sie unter [Ergebnisse des aufrufenden Beispiels](../cpp/results-of-calling-example.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Aufrufkonventionen](../cpp/calling-conventions.md)