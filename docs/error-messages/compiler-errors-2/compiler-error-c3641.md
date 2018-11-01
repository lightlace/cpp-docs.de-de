---
title: Compilerfehler C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: f6c27067e4f07c89b4226cf4d26adf2afb0b07ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648577"
---
# <a name="compiler-error-c3641"></a>Compilerfehler C3641

> "*Funktion*': ungültige Aufrufkonvention 'Aufrufkonvention' für die Funktion, die mit/CLR kompiliert: pure oder/clr: safe

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Nur [__clrcall](../../cpp/clrcall.md) Aufrufkonvention kann mit [/CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3641 generiert:

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```