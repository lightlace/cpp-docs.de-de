---
title: Compilerwarnung (Stufe 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 1cef70ab02148924bf6a0f29e298b34c54b28bc4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624327"
---
# <a name="compiler-warning-level-4-c4431"></a>Compilerwarnung (Stufe 4) C4431

Fehlender Typspezifizierer - int wird angenommen. Hinweis: default-int wird von C++ nicht unterstützt

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für Visual C++ 2005 durchgeführt wurde generiert werden: Visual C++ erstellt in der standardmäßig keine nicht typisierten Bezeichner als Int. Der Typ eines Bezeichners muss explizit angegeben werden.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4431 generiert.

```
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```