---
title: Compilerwarnung (Stufe 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 640eb77273fdbda0b12bbf2c2a326e970951cbda
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051991"
---
# <a name="compiler-warning-level-2-c4756"></a>Compilerwarnung (Stufe 2) C4756

Überlauf bei konstanter Arithmetik

Der Compiler hat eine Ausnahme beim Ausführen konstanter arithmetischer Berechnungen während der Kompilierung generiert.

Im folgenden Beispiel wird C4756 generiert:

```cpp
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```