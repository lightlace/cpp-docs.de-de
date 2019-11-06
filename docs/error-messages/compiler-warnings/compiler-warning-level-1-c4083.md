---
title: Compilerwarnung (Stufe 1) C4083
ms.date: 11/04/2016
f1_keywords:
- C4083
helpviewer_keywords:
- C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
ms.openlocfilehash: c267d466b70242ebef837fbe01c91f2cf0f69c02
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626884"
---
# <a name="compiler-warning-level-1-c4083"></a>Compilerwarnung (Stufe 1) C4083

"Token" erwartet; Bezeichner "Identifier" gefunden

Ein Bezeichner tritt an der falschen Stelle in einer **#pragma** Anweisung auf.

## <a name="example"></a>Beispiel

```cpp
// C4083.cpp
// compile with: /W1 /LD
#pragma warning disable:4083    // C4083
#pragma warning(disable:4083)   //correct
```

Überprüfen Sie die Syntax der [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) Direktiven.