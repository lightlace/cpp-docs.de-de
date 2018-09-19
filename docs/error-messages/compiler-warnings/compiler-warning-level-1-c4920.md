---
title: Compilerwarnung (Stufe 1) C4920 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4920
dev_langs:
- C++
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4873fcb1e5bb6d712e44b86d6f60589d6c8ddf4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091737"
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