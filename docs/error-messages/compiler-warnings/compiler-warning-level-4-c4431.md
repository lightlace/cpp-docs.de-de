---
title: Compilerwarnung (Stufe 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 1cef70ab02148924bf6a0f29e298b34c54b28bc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391516"
---
# <a name="compiler-warning-level-4-c4431"></a>Compilerwarnung (Stufe 4) C4431

Fehlender Typspezifizierer - int wird angenommen. Hinweis: C# unterstützt nicht mehr standardmäßig-int

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für visuelle durchgeführt wurde generiert C++ 2005: Visual C++ wird nicht mehr standardmäßig nicht typisierten Bezeichner als Int erstellt. Der Typ eines Bezeichners muss explizit angegeben werden.

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