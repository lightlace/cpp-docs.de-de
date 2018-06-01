---
title: Compilerwarnung C4959 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4959
dev_langs:
- C++
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2819664fa94ca777339156dc9a31da17b991c6da
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705163"
---
# <a name="compiler-warning-c4959"></a>Compilerwarnung C4959

> nicht verwaltete Struktur kann nicht definiert "*Typ*" in/CLR: safe da führt zu nicht überprüfbaren Code den Zugriff auf ihre Member

## <a name="remarks"></a>Hinweise

Das Zugreifen auf einen Member eines nicht verwalteten Typs resultiert in einem nicht überprüfbaren Abbild (peverify.exe).

Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Die **/CLR: safe** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md) -Pragmas oder der Compileroption [/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4959 generiert:

```cpp
// C4959.cpp
// compile with: /clr:safe

// Uncomment the following line to resolve.
// #pragma warning( disable : 4959 )
struct X {
   int data;
};

int main() {
   X x;
   x.data = 10;   // C4959
}
```