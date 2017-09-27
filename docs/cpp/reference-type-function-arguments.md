---
title: Verweistyp Funktionsargumente | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- functions [C++], paramters
- function parameters, reference-type
- function arguments, reference-type
- passing parameters, reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e74cbde44cad618720983fbda4a6cf9ce8b75dc1
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="reference-type-function-arguments"></a>Verweistyp-Funktionsargumente
Häufig ist es effizienter, Verweise anstelle großer Objekte an Funktionen zu übergeben. Dies ermöglicht es dem Compiler, die Adresse des Objekts zu übergeben, während die Syntax beibehalten wird, die verwendet worden wäre, um auf das Objekt zuzugreifen. Betrachten Sie das folgende Beispiel, in dem die `Date`-Struktur verwendet wird:  
  
```  
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
  
 Der vorhergehende Code zeigt, dass Member einer Struktur, die als Verweis übergebene zugegriffen werden, mit dem Memberauswahloperator (**.**) anstelle der Zeiger Objektmember-auswahloperators (**->**).  
  
 Obwohl als Verweistypen Argumente übergeben wurden die Syntax von nichtzeigertypen überwachen, behalten sie ein wichtiges Merkmal der Zeigertypen: sie sind änderbar, es sei denn, die als deklariert sind **const**. Da die Absicht des vorangehenden Codes nicht in der Änderung des `GDate` -Objekts liegt, ist ein geeigneterer Funktionsprototyp:  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 Der Prototyp garantiert, dass die Funktion `JulianFromGregorian` das Argument nicht ändert.  
  
 Jeder Prototyp einen Verweistyp Funktion kann ein Objekt vom selben Typ in seiner Stelle akzeptieren, da es eine standardkonvertierung von ist *Typename* auf *Typename* ** & **.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise](../cpp/references-cpp.md)
