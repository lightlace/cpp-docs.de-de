---
title: Compilerwarnung (Stufe 1) C4224
ms.date: 11/04/2016
f1_keywords:
- C4224
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
ms.openlocfilehash: 2ac7c49f33c052c895c71ca1dc3ce60be8dd9c8d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627291"
---
# <a name="compiler-warning-level-1-c4224"></a>Compilerwarnung (Stufe 1) C4224

nicht dem Standard entsprechende Erweiterung: der formale Parameter "Identifier" wurde zuvor als Typ definiert.

Der Bezeichner wurde zuvor als `typedef`verwendet. Dies verursacht eine Warnung unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Beispiel

```cpp
// C4224.cpp
// compile with: /Za /W1 /LD
typedef int I;
void func ( int I );  // C4224
```