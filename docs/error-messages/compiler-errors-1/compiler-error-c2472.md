---
title: Compilerfehler C2472
ms.date: 11/04/2016
f1_keywords:
- C2472
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
ms.openlocfilehash: d2f104bb61915f8d19d5fff22eea17929c0e8d74
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350909"
---
# <a name="compiler-error-c2472"></a>Compilerfehler C2472

> "*Funktion*' kann nicht in verwaltetem Code generiert werden:"*Nachricht*"; Kompilieren Sie mit" / CLR ", um ein gemischtes Image zu generieren.

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
