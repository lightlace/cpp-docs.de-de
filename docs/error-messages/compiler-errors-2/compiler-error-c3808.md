---
title: Compilerfehler C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: 0a1b0b82241c6e48d2c1941ff8122697d11492eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587732"
---
# <a name="compiler-error-c3808"></a>Compilerfehler C3808

> "*Typ*': eine Klasse mit dem ComImport-Attribut die Member kann nicht definiert"*Member*", nur abstrakte oder Dllimport-Funktionen sind zulässig

## <a name="remarks"></a>Hinweise

Ein Typ, der von abgeleitet <xref:System.Runtime.InteropServices.ComImportAttribute> kann nicht definiert *Member*.

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3808 generiert.

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```