---
title: Compilerwarnung (Ebene 1 und Ebene 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: f2876813131271ebb2561f8ea7435bb96dc2ce17
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627417"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Compilerwarnung (Ebene 1 und Ebene 4) C4949

die Pragmas "Managed" und "unmanaged" sind nur sinnvoll, wenn Sie mit "/CLR [: Option]" kompiliert werden.

Der Compiler ignoriert die [verwalteten](../../preprocessor/managed-unmanaged.md) und nicht verwalteten Pragmas, wenn der Quellcode nicht mit [/CLR](../../build/reference/clr-common-language-runtime-compilation.md)kompiliert ist. Diese Warnung dient nur zu Informationszwecken.

Im folgenden Beispiel wird C4949 generiert:

```cpp
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

Wenn **#pragma nicht verwaltete** ohne **/CLR**verwendet wird, ist C4949 eine Warnung der Stufe 4.

Im folgenden Beispiel wird C4949 generiert:

```cpp
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```