---
title: While-Anweisung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e226fdf4f8978172a187e1bfa8d53655ce368f5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463300"
---
# <a name="while-statement-c"></a>while-Anweisung (C++)
Führt *Anweisung* solange wiederholt, bis *Ausdruck* zu NULL ausgewertet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Test des *Ausdruck* erfolgt vor jeder Ausführung der Schleife; aus diesem Grund eine **während** Schleife NULL oder mehrmals ausgeführt. *Ausdruck* muss ein ganzzahliger Typ, ein Zeigertyp oder ein Klassentyp mit einer eindeutigen Konvertierung in einen Ganzzahl- oder Zeigertyp sein.  
  
 Ein **während** -Schleife kann auch beendet, wenn eine [Break](../cpp/break-statement-cpp.md), [Goto](../cpp/goto-statement-cpp.md), oder [zurückgeben](../cpp/return-statement-cpp.md) Text wird in der Anweisung ausgeführt. Verwendung [weiterhin](../cpp/continue-statement-cpp.md) beendet die aktuelle Iteration ohne Beenden der **während** Schleife. **weiterhin** übergibt die Steuerung an die nächste Iteration der **während** Schleife.  
  
 Der folgende code verwendet ein **während** Schleife gekürzt Unterstriche von einer Zeichenfolge:  
  
```cpp 
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 Die Beendigungsbedingung wird am Anfang der Schleife ausgewertet. Solange keine nachgestellten Unterstriche vorhanden sind, wird die Schleife nicht ausgeführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Iterationsanweisungen](../cpp/iteration-statements-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [do-while-Anweisung (C++)](../cpp/do-while-statement-cpp.md)   
 [for-Anweisung (C++)](../cpp/for-statement-cpp.md)   
 [Bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md)