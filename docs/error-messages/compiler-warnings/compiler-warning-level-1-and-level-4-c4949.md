---
title: Compilerwarnung (Stufe 1 und Stufe 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 8050edbd7a653776d046bc7b4155fd43094d9a5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187521"
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