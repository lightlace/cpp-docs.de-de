---
title: Compilerwarnung (Stufe 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 305c1156ae8dc664edba17287786db50bfabbd18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483700"
---
# <a name="compiler-warning-level-1-c4353"></a>Compilerwarnung (Stufe 1) C4353

nicht dem Standard entsprechende Erweiterung: Konstante 0 als Funktionsausdruck. Verwenden Sie stattdessen die systeminterne '__noop'-Funktion

Sie können die Konstante 0 (null) als Funktionsausdruck nicht verwenden. Weitere Informationen finden Sie unter [__noop](../../intrinsics/noop.md).

Im folgende Beispiel wird die C4353 generiert:

```
// C4353.cpp
// compile with: /W1
void MyPrintf(void){};
#define X 0
#if X
   #define DBPRINT MyPrint
#else
   #define DBPRINT 0   // C4353 expected
#endif
int main(){
DBPRINT();
}
```