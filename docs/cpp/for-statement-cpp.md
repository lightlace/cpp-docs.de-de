---
title: for-Anweisung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a845fde2010f17d4d92be0d8ed0d4cce0bdb070
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061499"
---
# <a name="for-statement-c"></a>for-Anweisung (C++)

Führt eine Anweisung wiederholt aus, bis die Bedingung false ergibt. Weitere Informationen zu den bereichsbasierter for-Anweisung, finden Sie unter [bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md).

## <a name="syntax"></a>Syntax

```
for ( init-expression ; cond-expression ; loop-expression )
    statement;
```

## <a name="remarks"></a>Hinweise

Verwenden der **für** Anweisung zum Erstellen von Schleifen, die eine angegebene Anzahl von Malen ausgeführt werden muss.

Die **für** Anweisung besteht aus drei optionalen Komponenten, wie in der folgenden Tabelle gezeigt.

### <a name="for-loop-elements"></a>for-Schleifenelemente

|Syntaxname|Ausführung bei|Beschreibung|
|-----------------|-------------------|-----------------|
|`init-expression`|Vor jedem anderen Element von der **für** Anweisung `init-expression` wird nur einmal ausgeführt. Das Steuerelement wird dann an `cond-expression` übergeben.|Wird häufig zum Initialisieren von Schleifenindizes verwendet. Es können Ausdrücke oder Deklarationen enthalten sein.|
|`cond-expression`|Vor der Ausführung jeder Iteration von `statement`, einschließlich der ersten Iteration. `statement` wird nur ausgeführt, wenn `cond-expression` den Wert „True“ (ungleich 0 (null)) annimmt.|Ein Ausdruck, der einen Ganzzahltyp oder einen Klassentyp ergibt, der über eine eindeutige Konvertierung in einen Ganzzahltyp verfügt. Wird normalerweise zum Testen von Beendigungskriterien für Schleifen verwendet.|
|`loop-expression`|Am Ende jeder Iteration von `statement`. Nachdem `loop-expression` ausgeführt wird, wird `cond-expression` ausgewertet.|Wird normalerweise zum Erhöhen von Schleifenindizes verwendet.|

Die folgenden Beispiele zeigen verschiedene Verwendungsmöglichkeiten der **für** Anweisung.

```cpp
#include <iostream>
using namespace std;

int main() {
    // The counter variable can be declared in the init-expression.
    for (int i = 0; i < 2; i++ ){
       cout << i;
    }
    // Output: 01
    // The counter variable can be declared outside the for loop.
    int i;
    for (i = 0; i < 2; i++){
        cout << i;
    }
    // Output: 01
    // These for loops are the equivalent of a while loop.
    i = 0;
    while (i < 2){
        cout << i++;
    }
}
    // Output: 012
```

`init-expression` und `loop-expression` können mehrere durch Kommas getrennte Anweisungen enthalten. Zum Beispiel:

```cpp
#include <iostream>
using namespace std;

int main(){
    int i, j;
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {
        cout << "i + j = " << (i + j) << '\n';
    }
}
    // Output:
    i + j = 15
    i + j = 17
    i + j = 19
```

Der `loop-expression` kann erweitert oder verringert werden oder in anderer Weise geändert werden.

```cpp
#include <iostream>
using namespace std;

int main(){
for (int i = 10; i > 0; i--) {
        cout << i << ' ';
    }
    // Output: 10 9 8 7 6 5 4 3 2 1
    for (int i = 10; i < 20; i = i+2) {
        cout << i << ' ';
    }
    // Output: 10 12 14 16 18
```

Ein **für** Schleife wird beendet, wenn eine [Break](../cpp/break-statement-cpp.md), [zurückgeben](../cpp/return-statement-cpp.md), oder [Goto](../cpp/goto-statement-cpp.md) (eine Anweisung mit Bezeichnung außerhalb der **für**Schleife) innerhalb von `statement` ausgeführt wird. Ein [weiterhin](../cpp/continue-statement-cpp.md) -Anweisung in einem **für** -Schleife wird nur die aktuelle Iteration beendet.

Wenn `cond-expression` wird weggelassen wird, gilt es als "true" und die **für** Schleife nicht beendet, ohne eine **Break**, **zurückgeben**, oder **Goto** in `statement`.

Obwohl die drei Felder der **für** Anweisung normalerweise zum Initialisieren, Testen auf Beendigung und inkrementieren verwendet werden, sind nicht auf dieser Verwendungsmöglichkeiten begrenzt. Beispielsweise gibt der folgende Code die Zahlen 0 bis 4 aus. In diesem Fall handelt es sich bei `statement` um die null-Anweisung:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i;
    for( i = 0; i < 5; cout << i << '\n', i++){
        ;
    }
}
```

## <a name="for-loops-and-the-c-standard"></a>for-Schleifen und der C++-Standard

Die C++-Standard besagt, dass eine Variable in deklariert eine **für** Schleife wird verlassen den Gültigkeitsbereich nach Beenden der **für** Schleife. Zum Beispiel:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

In der Standardeinstellung unter [/Ze](../build/reference/za-ze-disable-language-extensions.md), eine Variable deklariert, die einer **für** Schleife bleibt im Gültigkeitsbereich, bis die **für** Schleife des einschließenden Bereich endet.

[/ Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) ermöglicht Standardverhalten der ohne Angabe in for-Schleifen deklarierten Variablen `/Za`.

Es ist auch möglich, mit der Bereichsdefinition Differenzen der **für** Schleife um Deklarieren von Variablen unter `/Ze` wie folgt:

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Dies genauer imitiert das Standardverhalten einer Variablen, die in deklariert eine **für** -Schleife, die Variablen, die in erfordert eine **für** Schleife zum Verlassen des Bereichs nach die Schleife abgeschlossen ist. Beim Deklarieren einer Variablen einem **für** Schleife der Compiler intern stuft sie auf eine lokale Variable in der **für** Schleife des einschließenden Bereich, selbst wenn bereits eine lokale Variable mit dem gleichen Namen vorhanden ist.

## <a name="see-also"></a>Siehe auch

[Iterationsanweisungen](../cpp/iteration-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[while-Anweisung (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while-Anweisung (C++)](../cpp/do-while-statement-cpp.md)<br/>
[Bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md)