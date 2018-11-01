---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 3609e3f0541cfd8a8af8559d8d49e6a77c00d91c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660004"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Der Einschränkungsspezifizierer kann auf Funktions- und Lambda-Deklarationen angewendet werden. Er erzwingt Einschränkungen für den Code in der Funktion und das Verhalten der Funktion in Anwendungen, die C++ Accelerated Massive Parallelism(C++ AMP)-Laufzeit verwenden.

> [!NOTE]
>  Informationen zu den **einschränken** Schlüsselwort, das Teil ist die **__declspec** speicherklassenattribute, finden Sie unter [einschränken](../cpp/restrict.md).

Die **einschränken** -Klausel nimmt folgende Formen:

|Klausel|Beschreibung|
|------------|-----------------|
|`restrict(cpu)`|Die Funktion kann die vollständige C++-Programmiersprache verwenden. Es können nur andere Funktionen, die durch die Verwendung von restrict(cpu)-Funktionen deklariert werden, die Funktion aufrufen.|
|`restrict(amp)`|Die Funktion kann nur die Teilmenge der Programmiersprache C++ verwenden, die mit C++ AMP beschleunigt werden kann.|
|Eine Sequenz von `restrict(cpu)` und `restrict(amp)`.|Die Funktion muss den Einschränkungen von `restrict(cpu)` und `restrict(amp)` folgen. Die Funktion kann von Funktionen aufgerufen werden, die durch die Verwendung von `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` oder `restrict(amp, cpu)` deklariert werden.<br /><br /> Das Formular `restrict(A) restrict(B)` kann als `restrict(A,B)` geschrieben werden.|

## <a name="remarks"></a>Hinweise

Die **einschränken** -Schlüsselwort ist ein kontextbezogenes Schlüsselwort. Die Einschränkungsspezifizierer, `cpu` und `amp` sind keine reservierten Wörter. Die Liste der Spezifizierer ist nicht erweiterbar. Eine Funktion, die keinem **einschränken** -Klausel ist identisch mit einer Funktion mit der `restrict(cpu)` Klausel.

Eine Funktion, die über die `restrict(amp)`-Klausel verfügt, hat folgende Einschränkungen:

- Die Funktion kann nur Funktionen aufrufen, die die `restrict(amp)`-Klausel enthalten.

- Die Funktion muss inlinable sein.

- Die Funktion kann nur deklariert **Int**, **ganze Zahl ohne Vorzeichen**, **"float"**, und **doppelte** Variablen, Klassen und Strukturen, die nur enthalten. Diese Typen. **"bool"** ist ebenfalls zulässig, aber es muss nicht 4-Byte-ausgerichtet, wenn Sie ihn in einem Verbundtyp verwenden.

- Lambda-Funktionen können nicht als Verweis erfassten und können keine Zeiger erfassen.

- Verweise und Einzeldereferenzierungszeiger werden nur als lokale Variablen, Funktionsargumente und Rückgabetypen unterstützt.

- Folgendes ist nicht zulässig:

   - Rekursion.

   - Variablen, die mit der [flüchtige](../cpp/volatile-cpp.md) Schlüsselwort.

   - Virtuelle Funktionen.

   - Zeiger auf Funktionen.

   - Zeiger auf die Memberfunktionen.

   - Zeiger in Strukturen.

   - Zeiger auf Zeiger.

   - **"GoTo"** Anweisungen.

   - Anweisungen mit Bezeichnung.

   - **Versuchen Sie es**, **catch**, oder **auslösen** Anweisungen.

   - Globale Variablen.

   - Statische Variablen. Verwendung [Tile_static-Schlüsselwort](../cpp/tile-static-keyword.md) stattdessen.

   - **Dynamic_cast** Umwandlungen.

   - Die **Typeid** Operator.

   - ASM-Deklarationen.

   - Varargs.

Eine Erläuterung der funktionseinschränkungen, finden Sie unter [einschränken (Amp)-Einschränkungen](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie mit der `restrict(amp)`Klausel.

```cpp
void functionAmp() restrict(amp) {}
void functionNonAmp() {}

void callFunctions() restrict(amp)
{
    // int is allowed.
    int x;
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.
    // long long int y;

    // Calling an amp-restricted function is allowed.
    functionAmp();

    // Calling a non-amp-restricted function is not allowed.
    // functionNonAmp();
}
```

## <a name="see-also"></a>Siehe auch

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)