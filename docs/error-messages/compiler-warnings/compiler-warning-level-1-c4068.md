---
title: Compilerwarnung (Stufe 1) C4068
ms.date: 11/04/2016
f1_keywords:
- C4068
helpviewer_keywords:
- C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
ms.openlocfilehash: ba6e57fb954e0331e8eede5e7859fbeed5ce6424
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626930"
---
# <a name="compiler-warning-level-1-c4068"></a>Compilerwarnung (Stufe 1) C4068

Unbekanntes Pragma

Der Compiler hat ein nicht erkanntes [Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)ignoriert. Stellen Sie sicher, dass das **Pragma** vom verwendeten Compiler zugelassen wird. Im folgenden Beispiel wird C4068 generiert:

```cpp
// C4068.cpp
// compile with: /W1
#pragma NotAValidPragmaName   // C4068, use valid name to resolve
int main()
{
}
```