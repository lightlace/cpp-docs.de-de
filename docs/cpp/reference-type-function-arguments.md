---
title: Verweistyp Funktionsargumente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- functions [C++], paramters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad8fc85a37aec80d09ed6df9280a78de0540f01
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409055"
---
# <a name="reference-type-function-arguments"></a>Verweistyp-Funktionsargumente
Häufig ist es effizienter, Verweise anstelle großer Objekte an Funktionen zu übergeben. Dies ermöglicht es dem Compiler, die Adresse des Objekts zu übergeben, während die Syntax beibehalten wird, die verwendet worden wäre, um auf das Objekt zuzugreifen. Betrachten Sie das folgende Beispiel, in dem die `Date`-Struktur verwendet wird:  
  
```cpp 
// reference_type_function_arguments.cpp  
struct Date  
{  
short DayOfWeek;  
short Month;  
short Day;  
short Year;  
};  
  
// Create a Julian date of the form DDDYYYY  
// from a Gregorian date.  
long JulianFromGregorian( Date& GDate )  
{  
static int cDaysInMonth[] = {  
31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31  
   };  
long JDate = 0;  
// Add in days for months already elapsed.  
for ( int i = 0; i < GDate.Month - 1; ++i )  
JDate += cDaysInMonth[i];  
// Add in days for this month.  
JDate += GDate.Day;  
  
// Check for leap year.  
if ( GDate.Year % 100 != 0 && GDate.Year % 4 == 0 )  
JDate++;  
// Add in year.  
JDate *= 10000;  
JDate += GDate.Year;  
  
return JDate;  
}  
  
int main()  
{  
}  
```  
  
 Der vorhergehende Code zeigt, dass Member einer Struktur, die als Verweis übergeben wird, zugegriffen werden mit dem Memberauswahloperator (**.**) anstelle der Zeiger Objektmember-auswahloperators (**->**).  
  
 Obwohl als Verweistypen Argumente übergeben wurden, die Syntax von nichtzeigertypen überwachen, behalten sie ein wichtiges Merkmal der Zeigertypen: sie sind änderbar, es sei denn, die als deklariert **const**. Da die Absicht des vorangehenden Codes nicht in der Änderung des `GDate` -Objekts liegt, ist ein geeigneterer Funktionsprototyp:  
  
```cpp 
long JulianFromGregorian( const Date& GDate );  
```  
  
 Der Prototyp garantiert, dass die Funktion `JulianFromGregorian` das Argument nicht ändert.  
  
 Alle Funktionen Prototyp einen Verweistyp übernehmen kann stattdessen ein Objekt des gleichen Typs an seiner Stelle annehmen, da es eine standardkonvertierung von ist *Typename* , * Typename ***&**.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise](../cpp/references-cpp.md)