---
title: Compilerwarnung (Stufe 1) C4286
ms.date: 11/04/2016
f1_keywords:
- C4286
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
ms.openlocfilehash: be02d330678eaab7f538ed092641f957bdcb01b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455210"
---
# <a name="compiler-warning-level-1-c4286"></a>Compilerwarnung (Stufe 1) C4286

"Typ1": wurde aufgefangen durch Basisklasse ('Typ2') in Zeilennummer

Der Typ der angegebenen Ausnahme wird von einem vorherigen Handler behandelt. Der Typ für den zweiten Catch ist vom Typ des ersten abgeleitet. Ausnahmen für eine Basisklasse fangen Sie Ausnahmen für eine abgeleitete Klasse.

## <a name="example"></a>Beispiel

```
//C4286.cpp
// compile with: /W1
#include <eh.h>
class C {};
class D : public  C {};
int main()
{
    try
    {
        throw "ooops!";
    }
    catch( C ) {}
    catch( D ) {}  // warning C4286, D is derived from C
}
```