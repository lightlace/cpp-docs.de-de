---
title: Compilerwarnung (Stufe 1) C4537 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4537
dev_langs:
- C++
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 052d11d5bdf269d950abe1ef761adc055cbc6ce3
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213362"
---
# <a name="compiler-warning-level-1-c4537"></a>Compilerwarnung (Stufe 1) C4537

> "*Objekt*': '*Operator*" auf nicht-UDT-Typ angewendet wird

## <a name="remarks"></a>Hinweise

Ein Verweis wurde übergeben, obwohl ein Objekt (UDT) erwartet wurde. Ein Verweis ist kein Objekt allerdings Inlineassemblercode kann nicht auf die Unterscheidung vornehmen zu können. Der Compiler generiert Code, als ob *Objekt* wurden von eine Instanz.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4537 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4537.cpp
// compile with: /W1 /c
// processor: x86
struct S {
    int member;
};

void f1(S &s) {
    __asm mov eax, s.member;   // C4537
    // try the following code instead
    // or, make the declaration "void f1(S s)"
    /*
    mov eax, s
    mov eax, [eax]s.member
    */
}
```