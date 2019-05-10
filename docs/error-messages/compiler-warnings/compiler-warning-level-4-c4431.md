---
title: Compilerwarnung (Stufe 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 6a07a9ffa938d9372ebed9676847b3274115d526
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447019"
---
# <a name="compiler-warning-level-4-c4431"></a>Compilerwarnung (Stufe 4) C4431

Fehlender Typspezifizierer - int wird angenommen. Hinweis: C# unterstützt nicht mehr standardmäßig-int

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler generiert werden, die für Visual Studio 2005 durchgeführt wurde: Visual C++ wird nicht mehr standardmäßig nicht typisierten Bezeichner als Int erstellt. Der Typ eines Bezeichners muss explizit angegeben werden.

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