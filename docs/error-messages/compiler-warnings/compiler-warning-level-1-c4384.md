---
title: Compilerwarnung (Stufe 1) C4384
ms.date: 11/04/2016
f1_keywords:
- C4384
helpviewer_keywords:
- C4384
ms.assetid: fafa8eb2-cbfc-4edb-8b0f-511ff5d37ac0
ms.openlocfilehash: 467f15522503d16d3b023661ee339c986f74ddec
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73964891"
---
# <a name="compiler-warning-level-1-c4384"></a>Compilerwarnung (Stufe 1) C4384

\#Pragma "make_public" sollte nur im globalen Gültigkeitsbereich verwendet werden.

Das [make_public](../../preprocessor/make-public.md) -Pragma wurde falsch angewendet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4384 generiert.

```cpp
// C4384.cpp
// compile with: /c /W1
namespace n {
   #pragma make_public(N::C)   // C4384
   namespace N {
      class C {};
   }
}
```