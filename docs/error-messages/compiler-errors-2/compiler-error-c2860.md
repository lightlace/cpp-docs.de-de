---
title: Compilerfehler C2860 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2860
dev_langs:
- C++
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51a73a9997dda717f2c4977d75d99da72d58ae7b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091152"
---
# <a name="compiler-error-c2860"></a>Compilerfehler C2860

"void" nicht möglich, ein Argumenttyp, mit Ausnahme von "(Void)"

Typ `void` kann nicht als Argumenttyp mit anderen Argumenten verwendet werden.

Im folgende Beispiel wird die C2860 generiert:

```
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```