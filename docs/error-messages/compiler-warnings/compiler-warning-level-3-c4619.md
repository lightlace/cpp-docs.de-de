---
title: Compilerwarnung (Stufe 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: 658e52a2349f070def1efb80ca8a1cd93abca0cd
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991966"
---
# <a name="compiler-warning-level-3-c4619"></a>Compilerwarnung (Stufe 3) C4619

\#pragma-Warnung: Es ist keine Warnungs Nummer ' Number ' vorhanden.

Es wurde versucht, eine Warnung zu deaktivieren, die nicht vorhanden ist.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4619 generiert:

```cpp
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```
