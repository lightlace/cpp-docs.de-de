---
title: Compilerwarnung (Stufe 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: 56fe0f314142d873fc02136bc2c3fe65e71f4dda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544065"
---
# <a name="compiler-warning-level-1-c4399"></a>Compilerwarnung (Stufe 1) C4399

> "*Symbol*": Prozessspezifische Symbole sollten nicht gekennzeichnet werden, mit der von "__declspec(dllimport)" ", bei der Kompilierung mit/clr: pure

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Daten über ein systemeigenes Image oder ein Bild mit systemeigenen und CLR-Konstrukte können nicht in einem reinen Image importiert werden. Um diese Warnung zu beheben, kompilieren Sie mit **"/ CLR"** (nicht **/CLR: pure**) oder Löschen von `__declspec(dllimport)`.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4399 generiert.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```