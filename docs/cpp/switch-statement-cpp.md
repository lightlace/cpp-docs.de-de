---
title: switch-Anweisung (C++)
ms.date: 11/04/2016
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 67918b7df747d3bee923da500729e60b4fe04336
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328850"
---
# <a name="switch-statement-c"></a>switch-Anweisung (C++)

Ermöglicht die Auswahl von mehreren Codeabschnitten, abhängig vom Wert eines ganzzahligen Ausdrucks.

## <a name="syntax"></a>Syntax

```
   switch ( init; expression )
   case constant-expression : statement
   [default  : statement]
```

## <a name="remarks"></a>Hinweise

Die *Ausdruck* muss ein ganzzahliger Typ oder einen Klassentyp, der für die eine eindeutige Konvertierung in einen ganzzahligen Typ vorhanden ist. Ganzzahlige Erweiterung wird ausgeführt, wie in beschrieben [Standardkonvertierungen](standard-conversions.md).

Die **wechseln** -Anweisungstext besteht aus einer Reihe von **Fall** -Bezeichnungen und einer optionalen **Standard** Bezeichnung. Keine zwei Konstante Ausdrücke in **Fall** Anweisungen können auf den gleichen Wert ausgewertet. Die **Standard** Bezeichnung kann nur einmal vorkommen. Die bezeichneten Anweisungen sind nicht syntaktischen Anforderungen, aber die **wechseln** -Anweisung ist ohne sie bedeutungslos.   Die default-Anweisung muss nicht am Ende stehen. Sie kann überall im Text der switch-Anweisung vorkommen. Eine case- oder default-Bezeichnung kann nur innerhalb einer switch-Anweisung angezeigt werden.

Die *Konstantenausdruck* in den einzelnen **Fall** Bezeichnung konvertiert wird, in den Typ des *Ausdruck* und *Ausdruck* für Gleichheit. Steuerelement an die Anweisung übergeben, deren **Fall** *Konstantenausdruck* entspricht dem Wert *Ausdruck*. Der resultierende Verhalten wird in der folgenden Tabelle gezeigt.

### <a name="switch-statement-behavior"></a>Verhalten der switch-Anweisung

|Bedingung|Aktion|
|---------------|------------|
|Der konvertierte Wert stimmt mit dem des hochgestuften steuernden Ausdrucks überein.|Die Steuerung wird an die Anweisung übertragen, die auf die Bezeichnug folgt.|
|Keine der Konstanten entspricht den Konstanten in der **Fall** Bezeichnungen; eine **Standard** -Bezeichnung ist vorhanden.|Die Steuerung an die **Standard** Bezeichnung.|
|Keine der Konstanten entspricht den Konstanten in der **Fall** Bezeichnungen. **Standard** Bezeichnung ist nicht vorhanden.|Die Steuerung an die Anweisung nach der **wechseln** Anweisung.|

Wenn ein entsprechender Ausdruck gefunden wird, ist Steuerelement nicht von nachfolgenden behindert **Fall** oder **Standard** Bezeichnungen. Die [Break](../cpp/break-statement-cpp.md) -Anweisung verwendet, um die Ausführung angehalten, und übertragen Sie die Steuerung an die Anweisung nach der **wechseln** Anweisung. Ohne eine **Break** -Anweisung wird jede Anweisung von der entsprechenden **Fall** -Bezeichnung bis zum Ende des der **wechseln**, einschließlich der **Standard**, ist ausgeführt. Zum Beispiel:

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   char *buffer = "Any character stream";
   int capa, lettera, nota;
   char c;
   capa = lettera = nota = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            capa++;
            break;
         case 'a':
            lettera++;
            break;
         default:
            nota++;
      }
   }
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",
      capa, lettera, (capa + lettera + nota) );
}
```

Im obigen Beispiel wird `capa` inkrementiert, wenn `c` ein groß geschriebenes `A` ist. Die **Break** Anweisung nach `capa++` beendet die Ausführung der **wechseln** -Anweisungstexts und übergibt Sie an der **während** Schleife. Ohne die **Break** -Anweisung, Ausführung würde "Fortfahren" nächste Anweisung mit Bezeichnung, so, dass `lettera` und `nota` würde auch erhöht werden. Ein ähnlicher Zweck erfüllt die **Break** -Anweisung für `case 'a'`. Wenn `c` ein klein geschriebenes `a`, `lettera` wird erhöht, und die **Break** -Anweisung beendet die **wechseln** Anweisungstext. Wenn `c` kein `a` oder `A`, **Standard** -Anweisung ausgeführt wird.

**Visual Studio 2017 und höher:** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) die `[[fallthrough]]` -Attribut ist in C ++ 17-standard angegeben. Es kann verwendet werden, eine **wechseln** Anweisung als Hinweis für den Compiler (oder für alle Benutzer beim Lesen des Codes), Fall-through-Verhalten vorgesehen ist. Visual C++-Compiler warnt derzeit nicht auf Fallthrough-Verhalten, damit Sie dieses Attribut hat keine Auswirkungen Compilerverhalten. Beachten Sie, dass das Attribut auf eine leere Anweisung innerhalb der Anweisung mit Bezeichnung angewendet wird. mit anderen Worten ist das Semikolon erforderlich.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): eine Switch-Anweisung kann einführen und initialisieren Sie eine Variable, deren Bereich auf den Block der Switch-Anweisung beschränkt ist:

```cpp
    switch (Gadget gadget(args); auto s = gadget.get_status())
    {
    case status::good:
        gadget.zip();
        break;
    case status::bad:
        throw BadGadget();
    };
```

Ein innerer Block einer **wechseln** -Anweisung kann Definitionen mit Initialisierungen enthalten, solange sie erreichbar sind, d. h. nicht von allen möglichen Ausführungspfaden umgangen. Namen, die mit diesen Deklarationen eingeführt werden, weisen einen lokalen Gültigkeitsbereich auf. Zum Beispiel:

```cpp
// switch_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    switch( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    case 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        break;

    case 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        break;

    default:
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        break;
    }
}
```

Ein **wechseln** Anweisung kann geschachtelt sein. In solchen Fällen **Fall** oder **Standard** Bezeichnungen ordnen Sie die nächstgelegene **wechseln** -Anweisung, die sie umschließt.

**Microsoft-spezifisch**

Microsoft C beschränkt nicht die Anzahl der Case-Werten in einer **wechseln** Anweisung. Die Anzahl wird nur durch den verfügbaren Speicher beschränkt. ANSI C erfordert, dass mindestens 257 Case-Bezeichnungen werden innerhalb von einer **wechseln** Anweisung.

Bei Microsoft C sind die Microsoft-Erweiterungen standardmäßig aktiviert. Verwenden der [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption verwenden, um diese Erweiterungen zu deaktivieren.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Auswahlanweisungen](../cpp/selection-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)