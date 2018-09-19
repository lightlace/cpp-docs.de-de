---
title: Compilerwarnung (Stufe 1) C4286 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4286
dev_langs:
- C++
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1a796ee1956de0795f677afec90dd2a65bb3d1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099524"
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