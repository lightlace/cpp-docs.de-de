---
title: Compilerwarnung C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: c15de8b22f56a2555cc763a45153139b1df01a31
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280840"
---
# <a name="compiler-warning-c4956"></a>Compilerwarnung C4956

> "*Typ*': Dieser Typ kann nicht überprüft werden

## <a name="remarks"></a>Hinweise

Diese Warnung wird generiert, wenn [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) angegeben ist und Ihr Code einen Typ enthält, der nicht überprüfbar ist. Die **/CLR: safe** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md) -Pragmas oder der Compileroption [/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4956 generiert:

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```