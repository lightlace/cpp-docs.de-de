---
title: Compilerwarnung (Stufe 4) C4061
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 073e3e9cb1cb5bb6b0f66157c986072227960212
ms.sourcegitcommit: 35c4b3478f8cc310ebbd932a18963ad8ab846ed9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59237119"
---
# <a name="compiler-warning-level-4-c4061"></a>Compilerwarnung (Stufe 4) C4061

> Enumerator '*Bezeichner*"im Schalter der Enumeration'*Enumeration*" wird nicht von einer Case-Bezeichnung explizit behandelt

Den angegebenen Enumerator *Bezeichner* weist keinen verknüpften Handler in einer `switch` -Anweisung mit einem `default` Fall. Die fehlende Case-Anweisung handelt es sich möglicherweise um ein Flüchtigkeitsfehler, oder er möglicherweise kein Problem. Es hängt von, ob der Enumerator von Standardfall oder nicht verarbeitet wird. Für eine verwandte Warnung für nicht verwendete Enumeratoren in `switch` Anweisungen, die keine `default` Groß-/Kleinschreibung, finden Sie unter [C4062](compiler-warning-level-4-c4062.md).

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen dazu, wie Sie Warnungen zu aktivieren, die standardmäßig deaktiviert sind, finden Sie unter [Compiler Warnungen, die standardmäßig deaktivierte](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

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

## <a name="see-also"></a>Siehe auch

[Compilerwarnung (Stufe 4) C4062](compiler-warning-level-4-c4062.md)
