---
title: Compilerwarnung (Stufe 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 102e9bdb2804988875d8c535eb8c266bd8fb03df
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683067"
---
# <a name="compiler-warning-level-4-c4431"></a>Compilerwarnung (Stufe 4) C4431

Fehlender Typspezifizierer - int wird angenommen. Hinweis: default-int wird von C++ nicht unterstützt

Dieser Fehler kann als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio 2005 ausgeführt C++ wurde: Visual erstellt nicht mehr standardmäßig nicht typisierte IDs als int. Der Typ eines Bezeichners muss explizit angegeben werden.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4431 generiert.

```c
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```