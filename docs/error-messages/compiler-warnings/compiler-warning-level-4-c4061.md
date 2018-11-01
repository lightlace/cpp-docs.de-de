---
title: Compilerwarnung (Stufe 4) C4061
ms.date: 11/30/2017
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 8b730d561134b8b7ca4454ee74f99216fbc72cb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453270"
---
# <a name="compiler-warning-level-4-c4061"></a>Compilerwarnung (Stufe 4) C4061

> Enumerator '*Bezeichner*"im Schalter der Enumeration'*Enumeration*" wird nicht von einer Case-Bezeichnung explizit behandelt

Der Enumerator hat keinen verknüpften Handler in einer `switch` Anweisung.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C4061; Fügen Sie einen Fall für den fehlenden Enumerator Fehler beheben:

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```