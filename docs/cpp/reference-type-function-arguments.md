---
title: Verweistyp-Funktionsargumente
ms.date: 08/27/2018
helpviewer_keywords:
- arguments [C++], function
- functions [C++], parameters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
ms.openlocfilehash: 2a0bd21023bd1c6bc14b1f587c85960cf1e8b820
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244180"
---
# <a name="reference-type-function-arguments"></a>Verweistyp-Funktionsargumente

Häufig ist es effizienter, Verweise anstelle großer Objekte an Funktionen zu übergeben. Dies ermöglicht es dem Compiler, die Adresse des Objekts zu übergeben, während die Syntax beibehalten wird, die verwendet worden wäre, um auf das Objekt zuzugreifen. Betrachten Sie das folgende Beispiel, in dem die `Date`-Struktur verwendet wird:

```cpp
// reference_type_function_arguments.cpp
#include <iostream>

struct Date
{
    short Month;
    short Day;
    short Year;
};

// Create a date of the form DDDYYYY (day of year, year)
// from a Date.
long DateOfYear( Date& date )
{
    static int cDaysInMonth[] = {
        31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31
    };
    long dateOfYear = 0;

    // Add in days for months already elapsed.
    for ( int i = 0; i < date.Month - 1; ++i )
        dateOfYear += cDaysInMonth[i];

    // Add in days for this month.
    dateOfYear += date.Day;

    // Check for leap year.
    if ( date.Month > 2 &&
        (( date.Year % 100 != 0 || date.Year % 400 == 0 ) &&
        date.Year % 4 == 0 ))
        dateOfYear++;

    // Add in year.
    dateOfYear *= 10000;
    dateOfYear += date.Year;

    return dateOfYear;
}

int main()
{
    Date date{ 8, 27, 2018 };
    long dateOfYear = DateOfYear(date);
    std::cout << dateOfYear << std::endl;
}
```

Der vorhergehende Code zeigt, dass Member einer Struktur, die als Verweis übergeben wird, zugegriffen werden mit dem Memberauswahloperator (**.**) anstelle der Zeiger Objektmember-auswahloperators (**->**).

Obwohl als Verweistypen Argumente übergeben wurden, die Syntax von nichtzeigertypen überwachen, behalten sie ein wichtiges Merkmal der Zeigertypen: sie sind änderbar, es sei denn, die als deklariert **const**. Da die Absicht des vorangehenden Codes nicht in der Änderung des `date` -Objekts liegt, ist ein geeigneterer Funktionsprototyp:

```cpp
long DateOfYear( const Date& date );
```

Der Prototyp garantiert, dass die Funktion `DateOfYear` das Argument nicht ändert.

Alle Funktionen Prototyp einen Verweistyp übernehmen kann stattdessen ein Objekt des gleichen Typs an seiner Stelle annehmen, da es eine standardkonvertierung von ist *Typename* zu *Typename* <strong>&</strong>.

## <a name="see-also"></a>Siehe auch

[Verweise](../cpp/references-cpp.md)<br/>
