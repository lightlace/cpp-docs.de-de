---
title: Compilerwarnung (Stufe 1) C4384 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4384
dev_langs:
- C++
helpviewer_keywords:
- C4384
ms.assetid: fafa8eb2-cbfc-4edb-8b0f-511ff5d37ac0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54d913aac76f767728bbe7b4a31d4ea1c8bbd96d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026997"
---
# <a name="compiler-warning-level-1-c4384"></a>Compilerwarnung (Stufe 1) C4384

\#Pragma "Make_public" sollte nur im globalen Gültigkeitsbereich verwendet werden

Die [Make_public](../../preprocessor/make-public.md) Pragma wurde falsch angewendet.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4384 generiert.

```
// C4384.cpp
// compile with: /c /W1
namespace n {
   #pragma make_public(N::C)   // C4384
   namespace N {
      class C {};
   }
}
```