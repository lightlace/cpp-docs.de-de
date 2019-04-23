---
title: Compilerwarnung C4957
ms.date: 11/04/2016
f1_keywords:
- C4957
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
ms.openlocfilehash: 79a1b516db1508c755693b67ca2e4070095839da
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778981"
---
# <a name="compiler-warning-c4957"></a>Compilerwarnung C4957

> "*Umwandlung*": explizite Umwandlung von '*Cast_from*'to'*Cast_to*' kann nicht überprüft werden

## <a name="remarks"></a>Hinweise

Eine Umwandlung ergibt ein nicht überprüfbares Image.

Einige Umwandlungen sind sicher (z. B. eine `static_cast` die benutzerdefinierte Umwandlungen auslöst, und eine `const_cast`). Eine [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) generiert auf jeden Fall überprüfbaren Code.

Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Die **/CLR: safe** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md) -Pragmas oder der Compileroption [/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4957 generiert:

```cpp
// C4957.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4957 )
using namespace System;
int main() {
   Object ^ o = "Hello, World!";
   String ^ s = static_cast<String^>(o);   // C4957
   String ^ s2 = safe_cast<String^>(o);   // OK
}
```