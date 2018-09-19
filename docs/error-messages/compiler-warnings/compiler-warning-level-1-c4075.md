---
title: Compilerwarnung (Stufe 1) C4075 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4075
dev_langs:
- C++
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5056c4bbca66b47ca991daf4c65485e80e43e0db
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073030"
---
# <a name="compiler-warning-level-1-c4075"></a>Compilerwarnung (Stufe 1) C4075

Initialisierungen stehen in nicht erkanntem Initialisierungsbereich

In einem [#pragma init_seg](../../preprocessor/init-seg.md) wird ein unbekannter Abschnittsname verwendet. Der Compiler ignoriert den **pragma** -Befehl.

Im folgenden Beispiel wird C4075 generiert:

```
// C4075.cpp
// compile with: /W1
#pragma init_seg("mysegg")   // C4075

// try..
// #pragma init_seg(user)

int main() {
}
```