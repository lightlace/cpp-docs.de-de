---
title: Compilerwarnung (Stufe 1 und Stufe 4) C4949 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f806912188ada3a4f97f0b1500e811d1271f40fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077307"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Compilerwarnung (Stufe 1 und Stufe 4) C4949

Pragmas "managed" und "unmanaged" sind sinnvoll, nur bei der Kompilierung mit "/ Clr [: Option]"

Der Compiler ignoriert die [verwaltet](../../preprocessor/managed-unmanaged.md) und nicht verwaltete Pragmas, wenn der Quellcode nicht kompiliert wird, mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md). Diese Warnung dient nur zu Informationszwecken.

Im folgende Beispiel wird die C4949 generiert:

```
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

Wenn **#pragma unmanaged** wird verwendet, ohne **"/ CLR"**, C4949 wird eine Warnung der Stufe 4.

Im folgende Beispiel wird die C4949 generiert:

```
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```