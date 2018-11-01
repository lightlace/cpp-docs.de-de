---
title: Verweise (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
ms.openlocfilehash: aafc582299402eabab2736ac7d07b6c4c397413c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616451"
---
# <a name="references-c"></a>Verweise (C++)

Ein Verweis, z. B. ein Zeiger ist, speichert die Adresse eines Objekts, das sich an anderer Stelle im Speicher befindet. Im Gegensatz zu einem Zeiger kann sich ein Verweis nach der Initialisierung nicht auf ein anderes Objekt beziehen oder auf null gesetzt werden. Es gibt zwei Arten von verweisen: Lvalue-Verweise, die auf einer benannten Variable und Rvalue-Verweise, die verweisen beziehen auf eine [temporäres Objekt](../cpp/temporary-objects.md). Der &-Operator gibt einen Lvalue-Verweis und der & &-Operator gibt einen Rvalue-Verweis oder einen universellen Verweis (Rvalue oder Lvalue) je nach Kontext.

Verweise können mit der folgenden Syntax deklariert werden:

> \[*Speicherklassenspezifizierer*] \[ *cv-Qualifizierer*] *-Typspezifizierer* \[ *ms-Modifizierer*]  *Deklarator* \[ **=** *Ausdruck*]**;**

Jeder gültige Deklarator, der einen Verweis angibt, kann verwendet werden. Sofern der Verweis kein Verweis auf den Funktions- oder Arraytyp ist, gilt die folgende vereinfachte Syntax:

> \[*Speicherklassenspezifizierer*] \[ *cv-Qualifizierer*] *-Typspezifizierer* \[ **&** oder **&&**] \[ *cv-Qualifizierer*] *Bezeichner* \[ **=** *Ausdruck*]**;**

Verweise werden unter Verwendung dieser Reihenfolge deklariert:

1. Die Deklarationsspezifizierer:

   - Ein optionaler Speicherklassenbezeichner.

   - Optionale **const** und/oder **flüchtige** Qualifizierer.

   - Der Typspezifizierer: der Name eines Typs

1. Der Deklarator:

   - Ein optionaler Microsoft-spezifischer Modifizierer. Weitere Informationen finden Sie unter [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).

   - Die **&** Operator oder **&&** Operator.

   - Optionale **const** und/oder **flüchtige** Qualifizierer.

   - Der Bezeichner.

1. Ein optionaler Initialisierer.

Die komplexeren deklaratorformen für Zeiger auf Arrays und Funktionen gelten auch für Verweise auf Arrays und Funktionen verwendet werden. Weitere Informationen finden Sie unter [Zeiger](../cpp/pointers-cpp.md).

Mehrere Deklaratoren und Initialisierer erscheinen möglicherweise in einer durch Trennzeichen getrennten Liste, die einem einzelnen Deklarationsspezifizierer folgt. Zum Beispiel:

```cpp
int &i;
int &i, &j;
```

Verweise, Zeiger und Objekte können zusammen deklariert werden:

```cpp
int &ref, *ptr, k;
```

Ein Verweis enthält die Adresse eines Objekts, verhält sich aber syntaktisch wie ein Objekt.

Beachten Sie im folgenden Programm, dass der Name des Objekts `s` und der Verweis auf das Objekt `SRef` in Programmen identisch verwendet werden kann:

## <a name="example"></a>Beispiel

```cpp
// references.cpp
#include <stdio.h>
struct S {
   short i;
};

int main() {
   S  s;   // Declare the object.
   S& SRef = s;   // Declare the reference.
   s.i = 3;

   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);

   SRef.i = 4;
   printf_s("%d\n", s.i);
   printf_s("%d\n", SRef.i);
}
```

```Output
3
3
4
4
```

## <a name="see-also"></a>Siehe auch

[Verweistyp-Funktionsargumente](../cpp/reference-type-function-arguments.md)<br/>
[Verweistyp-Funktionsrückgaben](../cpp/reference-type-function-returns.md)<br/>
[Verweise auf Zeiger](../cpp/references-to-pointers.md)
