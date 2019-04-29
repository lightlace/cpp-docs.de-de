---
title: Compilerfehler C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: 6a9568f3c3be88438eae1f28e12dc780301ead0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402579"
---
# <a name="compiler-error-c3389"></a>Compilerfehler C3389

> __declspec (*Schlüsselwort*) kann nicht verwendet werden, mit/clr: pure oder/clr: safe

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Ein [__declspec](../../cpp/declspec.md) Modifizierer impliziert einen prozessspezifischen Zustand.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) impliziert eine pro [Appdomain](../../cpp/appdomain.md) Zustand.  Also Deklarieren einer Variablen mit der `keyword` **__declspec** -Modifizierer und die Kompilierung mit **/CLR: pure** ist nicht zulässig.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3389 generiert:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```