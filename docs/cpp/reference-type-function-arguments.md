---
title: "Verweistyp-Funktionsargumente"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Argumente [C++], Funktion"
  - "Funktionsargumente, Verweistyp"
  - "Funktionsparameter, Verweistyp"
  - "Funktionen [C++], Parameter"
  - "Übergeben von Parametern, Verweistypargumente"
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Verweistyp-Funktionsargumente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Häufig ist es effizienter, Verweise anstelle großer Objekte an Funktionen zu übergeben.  Dies ermöglicht es dem Compiler, die Adresse des Objekts zu übergeben, während die Syntax beibehalten wird, die verwendet worden wäre, um auf das Objekt zuzugreifen.  Betrachten Sie das folgende Beispiel, in dem die `Date`\-Struktur verwendet wird:  
  
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
  
 Der obige Code zeigt, dass auf Member einer durch Verweis übergebenen Struktur mit dem Memberauswahloperator \(**.**\) zugegriffen wird und nicht mit dem Operator für Zeiger auf Memberauswahl \(**–\>**\).  
  
 Obwohl die Verweistypen, die als Argumente übergeben wurden, die Syntax von Nichtzeigertypen überwachen, behalten sie ein wichtiges Merkmal der Zeigertypen bei: Sie sind änderbar, es sei denn, sie sind als **const** deklariert.  Da die Absicht des vorangehenden Codes nicht in der Änderung des `GDate` \-Objekts liegt, ist ein geeigneterer Funktionsprototyp:  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 Der Prototyp garantiert, dass die Funktion `JulianFromGregorian` das Argument nicht ändert.  
  
 Alle Funktionen, deren Prototyp einen Verweistyp übernehmen können, können stattdessen ein Objekt des gleichen Typs annehmen, da es sich um eine Standardkonvertierung von *typename* in *typename***&** handelt.  
  
## Siehe auch  
 [Verweise](../cpp/references-cpp.md)