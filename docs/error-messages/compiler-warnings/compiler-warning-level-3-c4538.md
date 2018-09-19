---
title: Compilerwarnung (Stufe 3) C4538 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4538
dev_langs:
- C++
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c4d9095eef3e37aaa487ebec9ae271bcd48c74f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075526"
---
# <a name="compiler-warning-level-3-c4538"></a>Compilerwarnung (Stufe 3) C4538

'Typ': Const/Volatile-Qualifizierer für diesen Typ werden nicht unterstützt.

Ein Qualifiziererschlüsselwort wurde in ein Array falsch angewendet. Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).

Im folgende Beispiel wird die C4538 generiert:

```
// C4538.cpp
// compile with: /clr /W3 /LD
const array<int> ^f1();   // C4538
array<const int> ^f2();   // OK
```