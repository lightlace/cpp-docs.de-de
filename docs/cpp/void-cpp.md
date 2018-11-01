---
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: cb4be000c3c41862d5b4df766d21ae1cddeb6838
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594112"
---
# <a name="void-c"></a>void (C++)

Wenn als Rückgabetyp einer Funktion verwendet die **"void"** -Schlüsselwort Gibt an, dass die Funktion keinen Wert zurückgibt. Wenn es für die Parameterliste einer Funktion verwendet wird, gibt "void" an, dass die Funktion keine Parameter akzeptiert. Bei Verwendung in der Deklaration eines Zeigers gibt "void" an, dass der Zeiger "universal" ist.

Ist der Typ eines Zeigers `void *`, der Zeiger auf eine beliebige Variable, die nicht mit deklariert ist zeigen kann die **const** oder **flüchtige** Schlüsselwort. Ein void-Zeiger kann nicht dereferenziert werden, es sei denn, er wird in einen anderen Typ umgewandelt. Ein void-Zeiger kann in jeden anderen Datenzeigertyp konvertiert werden.

Ein void-Zeiger kann auf eine Funktion, jedoch nicht auf einen Klassenmember in C++ zeigen.

Eine Variable vom Typ "void" kann nicht deklariert werden.

## <a name="example"></a>Beispiel

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Grundlegende Typen](../cpp/fundamental-types-cpp.md)