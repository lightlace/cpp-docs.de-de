---
title: Compilerwarnung (Stufe 1) C4305 | Microsoft Docs
ms.custom: ''
ms.date: 1/17/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4305
dev_langs:
- C++
helpviewer_keywords:
- C4305
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7694c511f57b6907227d62f969b61218f836cb14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4305"></a>Compilerwarnung (Stufe 1) C4305

> "*Kontext*': Verkürzung von '*Typ1*'to'*Typ2*"  

## <a name="remarks"></a>Hinweise

Diese Warnung wird ausgegeben, wenn ein Wert in einen kleineren Typ in einer Initialisierung oder als ein Konstruktorargument führt zu einem Dienstausfall Informationen konvertiert wird.

## <a name="example"></a>Beispiel

In diesem Beispiel werden zwei Möglichkeiten, die Sie möglicherweise diese Warnung angezeigt:

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

Um dieses Problem zu beheben, initialisieren Sie, indem Sie einen Wert mit dem richtigen Typ, oder verwenden Sie eine explizite Umwandlung in den richtigen Typ. Verwenden Sie z. B. eine **"float"** z. B. 2.71828f anstelle von literalen eine **doppelte** (dem Standardtyp für gleitkommaliterale) initialisiert werden, eine **"float"** Variable, oder Übergabe an ein Konstruktor, akzeptiert eine **"float"** Argument.
