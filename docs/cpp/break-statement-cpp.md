---
title: break-Anweisung (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 3dda0b19fffaaf725ab363a0c4fe70d2ca54e3f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267714"
---
# <a name="break-statement-c"></a>break-Anweisung (C++)

Die **Break** -Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder bedingungsanweisung, in dem er angezeigt wird. Das Steuerelement wird an die Anweisung übergeben, die auf das Ende der Anweisung folgt, falls vorhanden.

## <a name="syntax"></a>Syntax

```
break;
```

## <a name="remarks"></a>Hinweise

Die **Break** Anweisung wird verwendet, mit der bedingten [wechseln](../cpp/switch-statement-cpp.md) Anweisung und die [führen](../cpp/do-while-statement-cpp.md), [für](../cpp/for-statement-cpp.md), und [beim](../cpp/while-statement-cpp.md) schleifenanweisungen.

In einem **wechseln** -Anweisung, die **Break** Anweisung bewirkt, dass das Programm zum Ausführen der nächsten Anweisung außerhalb der **wechseln** Anweisung. Ohne eine **Break** -Anweisung wird jede Anweisung von der entsprechenden **Fall** -Bezeichnung bis zum Ende des der **wechseln** -Anweisung, einschließlich der **Standard**-Klausel ausgeführt wird.

In Schleifen die **Break** -Anweisung beendet die Ausführung der nächsten einschließenden **führen**, **für**, oder **während** Anweisung. Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.

Innerhalb von geschachtelten Anweisungen der **Break** -Anweisung beendet nur die **führen**, **für**, **wechseln**, oder **beim**-Anweisung, die direkt eingeschlossen. Sie können eine **zurückgeben** oder **"GoTo"** Anweisung, um das Steuerelement von tiefer geschachtelten Strukturen.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit der **Break** -Anweisung in einem **für** Schleife.

```cpp
#include <iostream>
using namespace std;

int main()
{
    // An example of a standard for loop
    for (int i = 1; i < 10; i++)
    {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }

    // An example of a range-based for loop
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    for (int i : nums) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }
}
```

```Output
In each case:
1
2
3
```

Der folgende Code zeigt, wie Sie mit **Break** in einer **während** Schleife und einem **führen** Schleife.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;

    while (i < 10) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    }

    i = 0;
    do {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    } while (i < 10);
}
```

```Output
In each case:
0123
```

Der folgende Code zeigt, wie Sie mit **Break** in einer Switch-Anweisung. Verwenden Sie **Break** in jedem Fall, wenn Sie jeden Fall getrennt behandeln möchten, wenn Sie nicht verwenden **Break**, mit dem nächsten Fall fällt die codeausführung.

```cpp
#include <iostream>
using namespace std;

enum Suit{ Diamonds, Hearts, Clubs, Spades };

int main() {

    Suit hand;
    . . .
    // Assume that some enum value is set for hand
    // In this example, each case is handled separately
    switch (hand)
    {
    case Diamonds:
        cout << "got Diamonds \n";
        break;
    case Hearts:
        cout << "got Hearts \n";
        break;
    case Clubs:
        cout << "got Clubs \n";
        break;
    case Spades:
        cout << "got Spades \n";
        break;
    default:
          cout << "didn't get card \n";
    }
    // In this example, Diamonds and Hearts are handled one way, and
    // Clubs, Spades, and the default value are handled another way
    switch (hand)
    {
    case Diamonds:
    case Hearts:
        cout << "got a red card \n";
        break;
    case Clubs:
    case Spades:
    default:
        cout << "didn't get a red card \n";
    }
}
```

## <a name="see-also"></a>Siehe auch

[Sprunganweisungen](../cpp/jump-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[continue-Anweisung](../cpp/continue-statement-cpp.md)