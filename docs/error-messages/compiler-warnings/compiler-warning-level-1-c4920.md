---
title: Compilerwarnung (Stufe 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: 7cbb29c8dae24a87fcd5a32b4cf46d7a8ac4c790
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050242"
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

```cpp
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```