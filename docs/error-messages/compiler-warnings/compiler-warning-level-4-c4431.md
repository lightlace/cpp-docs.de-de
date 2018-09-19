---
title: Compilerwarnung (Stufe 4) C4431 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4431
dev_langs:
- C++
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b44cd72548f88d922accfd571bd3ce9734b3a409
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034745"
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