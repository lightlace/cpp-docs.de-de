---
title: Compilerwarnung (Stufe 1) C4602 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4602
dev_langs:
- C++
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cae5810f94ed9c3feb22de145c7e12e1a7d813b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033315"
---
# <a name="compiler-warning-level-1-c4602"></a>Compilerwarnung (Stufe 1) C4602

\#Pragma-Pop_macro: 'Makroname' kein vorherigen #pragma Push_macro für diesen Bezeichner

Wenn Sie [pop_macro](../../preprocessor/pop-macro.md) für ein bestimmtes Makro verwenden, müssen Sie zunächst den entsprechenden Makronamen an [push_macro](../../preprocessor/push-macro.md)übergeben. Im folgenden Beispiel wird C4602 generiert:

```
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```