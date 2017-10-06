---
title: While-Anweisung (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
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
ms.openlocfilehash: 694852e40699ac7b2663392cb8a4c02218a422a7
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="while-statement-c"></a>while-Anweisung (C++)
Führt *Anweisung* solange wiederholt, bis *Ausdruck* wird zu NULL ausgewertet.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Test von *Ausdruck* erfolgt vor jeder Ausführung der Schleife aus diesem Grund eine `while` Schleife 0 (null) oder mehrmals ausgeführt. *Ausdruck* muss ein ganzzahliger Typ, ein Zeigertyp oder ein Klassentyp mit einer eindeutigen Konvertierung in einen Ganzzahl- oder Zeigertyp sein.  
  
 Ein `while` Schleife kann auch beendet werden, wenn eine [Break](../cpp/break-statement-cpp.md), [Goto](../cpp/goto-statement-cpp.md), oder [zurückgeben](../cpp/return-statement-cpp.md) Text wird in der Anweisung ausgeführt. Verwendung [weiterhin](../cpp/continue-statement-cpp.md) ohne beendet die aktuelle Iteration beendet die `while` Schleife. **weiterhin** übergibt die Steuerung an die nächste Iteration der der `while` Schleife.  
  
 Im folgenden Code wird eine `while`-Schleife verwendet, um nachstehende Unterstriche von einer Zeichenfolge abzuschneiden:  
  
```  
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
