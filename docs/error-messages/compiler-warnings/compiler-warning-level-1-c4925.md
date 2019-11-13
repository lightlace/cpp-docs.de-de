---
title: Compilerwarnung (Stufe 1) C4925
ms.date: 11/04/2016
f1_keywords:
- C4925
helpviewer_keywords:
- C4925
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
ms.openlocfilehash: 88eb09bdde1fa8dc50fa601cf7ae200d2851ac03
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052293"
---
# <a name="compiler-warning-level-1-c4925"></a>Compilerwarnung (Stufe 1) C4925

„method“: Die dispinterface-Methode kann nicht von einem Skript aufgerufen werden.

Skriptsprachen können keine VT_BYREF-„in“-Parameter, sondern nur VT_BYREF-„out“-Parameter erstellen.

Eine weitere Möglichkeit zum Beheben dieser Warnung besteht darin, den Parameter (in der Definition und Implementierung) nicht zu einem Zeigertyp zu machen.

Im folgenden Beispiel wird C4925 generiert.

```cpp
// C4925.cpp
// compile with: /LD /W1
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[ module(name="Test")];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IDisp {
   [id(9)] void f([in] int*);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002")  ]
struct CDisp : IDisp {   // C4925
   void f(int*) {}
};
```