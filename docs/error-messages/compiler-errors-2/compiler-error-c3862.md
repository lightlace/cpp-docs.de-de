---
title: Compilerfehler C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: 2ba130862b1debbe2991ca7cbcae50192f900cd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446240"
---
# <a name="compiler-error-c3862"></a>Compilerfehler C3862

> "*Funktion*": kann nicht kompiliert werden eine nicht verwaltete Funktion mit/clr: pure oder/clr: safe

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Eine Kompilierung mit **/CLR: pure** oder **/CLR: safe** erzeugt eine einzige MSIL-Images, die ein Image ohne systemeigenen (nicht verwalteten) Code.  Aus diesem Grund können keine der `unmanaged` Pragma in einem **/CLR: pure** oder **/CLR: safe** Kompilierung.

Weitere Informationen finden Sie unter [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) und [verwaltete, unverwaltete](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3862 generiert:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```