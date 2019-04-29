---
title: Compilerwarnung (Stufe 4) C4463
ms.date: 11/04/2016
f1_keywords:
- C4463
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
ms.openlocfilehash: e125a532f87533958ec43ed5580665ad4108856b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400798"
---
# <a name="compiler-warning-level-4-c4463"></a>Compilerwarnung (Stufe 4) C4463

> Überlauf; Zuweisen von *Wert* zu Bit-Feld, das nur Werte enthalten kann *Low_value* zu *High_value*

Die zugewiesene *Wert* liegt außerhalb des Bereichs von Werten, die der Bit-Feld enthalten kann. Typen mit Vorzeichen Bitfeld verwenden das höherwertige bit für das Zeichen, wenn also *n* ist die Größe des Bereichs Bitfeld für die Vorzeichen von Bitfeldern-2<sup>n-1</sup> auf 2<sup>n-1</sup>1, während ohne Vorzeichen Bitfelder müssen einen Bereich von 0 bis 2<sup>n</sup>-1.

## <a name="example"></a>Beispiel

In diesem Beispiel wird C4463 generiert, da versucht wird, weisen Sie den Wert 3 ein Bitfeld des Typs `int` mit einer Größe von 2, die über einen Bereich von-2 bis 1 verfügt.

Um dieses Problem zu beheben, können Sie den zugewiesenen Wert einen im zulässigen Bereich ändern. Das Bitfeld zum Speichern von Werten ohne Vorzeichen im Bereich von 0 bis 3 vorgesehen ist, können Sie ändern die Art der Anmeldung zu `unsigned`. Wenn das Feld zum Speichern der Werte in den Bereich-4 bis 3 vorgesehen ist, können Sie die Größe des Bit-Feld auf 3 ändern.

```cpp
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S {
    int x : 2; // int type treats high-order bit as sign
};

int main() {
    S s;
    s.x = 3; // warning C4463: overflow; assigning 3
    // to bit-field that can only hold values from -2 to 1
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type
    // to unsigned.
}
```
