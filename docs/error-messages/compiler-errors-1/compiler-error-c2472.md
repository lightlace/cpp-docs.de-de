---
title: Compilerfehler C2472 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43279190847322fa2154c6faababdcd41b490eef
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704859"
---
# <a name="compiler-error-c2472"></a>Compilerfehler C2472

> "*Funktion*" kann nicht in verwaltetem Code generiert werden: "*Nachricht*"; Kompilieren Sie mit "/ CLR", um ein gemischtes Image zu generieren.

## <a name="remarks"></a>Hinweise

Dieser Fehler tritt auf, wenn von verwaltetem Code nicht unterstützte Typen innerhalb einer reinen CLR-Umgebung (Common Language Runtime) verwendet werden. Kompilieren Sie mit **/clr** , um den Fehler zu beheben.

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2472 generiert.

```cpp
// C2472.cpp
// compile with: /clr:pure
// C2472 expected

#include <cstdlib>

int main()
{
   int * __ptr32 p32;
   int * __ptr64 p64;

   p32 = (int * __ptr32)malloc(4);
   p64 = p32;
}
```

## <a name="see-also"></a>Siehe auch

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)
