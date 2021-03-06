---
title: return-Anweisung (C++)
ms.date: 11/04/2016
f1_keywords:
- return_cpp
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
ms.openlocfilehash: 47bf9c50a2da039b0ffa074796a768290b732bb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268537"
---
# <a name="return-statement-c"></a>return-Anweisung (C++)

Beendet die Ausführung einer Funktion und gibt die Steuerung an die aufrufende Funktion zurück (oder an das Betriebssystem, wenn Sie die Steuerung von der `main`-Funktion übertragen). Die Ausführung wird in der aufrufenden Funktion an dem Punkt fortgesetzt, der dem Aufruf unmittelbar folgt.

## <a name="syntax"></a>Syntax

```
return [expression];
```

## <a name="remarks"></a>Hinweise

Die Klausel `expression` wird, sofern vorhanden, in den Typ konvertiert, der in der Funktionsdeklaration angegeben wird, als ob eine Initialisierung durchgeführt würde. Konvertierung vom Typ des Ausdrucks, der die **zurückgeben** Typ der Funktion kann temporäre Objekte erstellen. Weitere Informationen dazu, wie und wann temporäre Objekte erstellt werden, finden Sie unter [temporäre Objekte](../cpp/temporary-objects.md).

Der Wert der `expression`-Klausel wird an die aufrufende Funktion zurückgegeben. Wenn der Ausdruck ausgelassen wird, wird der Rückgabewert der Funktion nicht definiert. Konstruktoren und Destruktoren sowie Funktionen des Typs **"void"**, keinen Ausdruck im Angeben der **zurückgeben** Anweisung. Funktionen aller anderen Typen müssen Geben Sie einen Ausdruck in der **zurückgeben** Anweisung.

Wenn die ablaufsteuerung den Block mit der Definition der Funktion beendet wird, werden Sie das Ergebnis ist dasselbe wie wenn eine **zurückgeben** -Anweisung ohne einen Ausdruck musste ausgeführt wurde. Dies ist ungültig bei Funktionen, die mit Rückgabewert deklariert werden.

Eine Funktion kann eine beliebige Anzahl von haben **zurückgeben** Anweisungen.

Im folgenden Beispiel wird einen Ausdruck mit einem **zurückgeben** Anweisung, um die größte von zwei ganzen Zahlen zu erhalten.

## <a name="example"></a>Beispiel

```cpp
// return_statement2.cpp
#include <stdio.h>

int max ( int a, int b )
{
   return ( a > b ? a : b );
}

int main()
{
    int nOne = 5;
    int nTwo = 7;

    printf_s("\n%d is bigger\n", max( nOne, nTwo ));
}
```

## <a name="see-also"></a>Siehe auch

[Sprunganweisungen](../cpp/jump-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)