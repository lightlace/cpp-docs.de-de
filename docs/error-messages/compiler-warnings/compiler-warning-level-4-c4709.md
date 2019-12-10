---
title: Compilerwarnung (Stufe 4) C4709
ms.date: 11/04/2016
f1_keywords:
- C4709
helpviewer_keywords:
- C4709
ms.assetid: 8abfdd45-8c70-4c27-b0fb-ca0c3f0fccf9
ms.openlocfilehash: 4dd06baf9da3ae454bf87747bdafb2639d817fef
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989863"
---
# <a name="compiler-warning-level-4-c4709"></a>Compilerwarnung (Stufe 4) C4709

Komma-Operator innerhalb des Array Index Ausdrucks

Wenn ein Komma in einem Array Index Ausdruck auftritt, verwendet der Compiler den Wert nach dem letzten Komma.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4709 generiert:

```cpp
// C4709.cpp
// compile with: /W4
#include <stdio.h>

int main()
{
    int arr[2][2];
    arr[0][0] = 10;
    arr[0][1] = 11;

    // Prints 10, not 11
    printf_s("\n%d",arr[0][1,0]);   // C4709
}
```
