---
title: Compilerwarnung (Stufe 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: cd501cf0e3b434523623276027056c93c77fc278
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580688"
---
# <a name="compiler-warning-level-1-c4920"></a>Compilerwarnung (Stufe 1) C4920

enum-Enumerationsmember 'member=value' ist bereits in der enum-Enumerarion als 'member=value' aufgetreten

Wenn in einer TLB-Datei, die Sie an '#import' übergeben, in zwei oder mehr Enumerationen das gleiche Symbol definiert ist, weist diese Warnung darauf hin, dass nachfolgende identische Symbole ignoriert werden und in der TLH-Datei auskommentiert werden.

Bei Zugrundelegung einer TLB-Datei, die folgendes enthält:

```
library MyLib
{
    typedef enum {
        enumMember = 512
    } AProblem;

    typedef enum {
        enumMember = 1024
    } BProblem;
};
```

wird im folgenden Beispiel C4920 generiert,

```
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```