---
title: Compilerfehler C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: 5cd7a83575da7ab2a30401406d0c2ccf6c1b603e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166645"
---
# <a name="compiler-error-c2435"></a>Compilerfehler C2435

> "*Var*": dynamische Initialisierung ist eine verwaltete CRT erforderlich ist, kann nicht mit/clr: safe kompiliert werden

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Die Initialisierung pro Anwendungsdomäne globale Variable erfordert kompilierte die CRT mit `/clr:pure`, die erzeugt kein überprüfbaren Abbild.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2435 generiert:

```cpp
// C2435.cpp
// compile with: /clr:safe /c
int globalvar = 0;   // C2435

__declspec(process)
int globalvar2 = 0;
```