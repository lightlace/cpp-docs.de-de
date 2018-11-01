---
title: Compilerwarnung (Stufe 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4055
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: e9fcb4356d993d86b622fd49c4a75d587554f7c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601317"
---
# <a name="compiler-warning-level-1-c4055"></a>Compilerwarnung (Stufe 1) C4055

> "*Konvertierung*': von Datenzeiger '*type1*'zu Funktionszeiger'*Typ2*"

## <a name="remarks"></a>Hinweise

**Veraltet:** diese Warnung wird von Visual Studio 2017 und höheren Versionen nicht generiert.

Ein Datenzeiger wird (möglicherweise falsch) in einen Funktionszeiger umgewandelt. Dies ist unter „/Za“ eine Warnung der Stufe 1 und unter „/Ze“ eine Warnung der Stufe 4.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4055 generiert:

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

Unter „/Ze“ ist dies eine Warnung der Stufe 4.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
