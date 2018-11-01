---
title: Compilerwarnung (Stufe 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: e898af8f109ed23bd1784df7b39c174bbed675f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552281"
---
# <a name="compiler-warning-level-3-c4159"></a>Compilerwarnung (Stufe 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>Pragma-pragma(pop,...): wurde per pop ausgelesen zuvor per push abgelegten Bezeichner "*Bezeichner*"

## <a name="remarks"></a>Hinweise

Enthält den Quellcode einer **Push** -Anweisung mit einem Bezeichner für ein Pragma, gefolgt von einem **pop** -Anweisung ohne Bezeichner. Daher *Bezeichner* wird per pop ausgelesen, und nachfolgende Verwendungen von *Bezeichner* kann unerwartetes Verhalten verursachen.

## <a name="example"></a>Beispiel

Um diese Warnung zu vermeiden, geben Sie einen Bezeichner der **pop** Anweisung. Zum Beispiel:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```