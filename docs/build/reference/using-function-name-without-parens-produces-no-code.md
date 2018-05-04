---
title: Verwendung eines Funktionsnamens ohne () kein Code erzeugt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40aed3969ae0707b07f0912d7247b49886d0319d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="using-function-name-without--produces-no-code"></a>Bei Verwendung eines Funktionsnamens ohne "()" wird kein Code generiert
Wenn Sie den Namen einer Funktion deklariert, die in Ihrem Programm ohne Klammern verwendet wird, gibt der Compiler Code nicht zurück. Dies tritt unabhängig davon, ob die Funktion Parameter akzeptiert, da der Compiler die Funktionsadresse berechnet; Da der Funktionsaufrufoperator "()" nicht vorhanden ist, wird kein Aufruf ausgeführt. Das Ergebnis ist ähnlich der folgenden:  
  
```  
// compile with /Wall to generate a warning  
int a;  
a;      // no code generated here either  
```  
  
 Sogar mit der Warnstufe 4 in Visual C++ generiert keinen Diagnoseausgabe aus. Es wird keine Warnung ausgegeben; Es wird kein Code erstellt.  
  
 Im folgenden Beispielcode kompiliert (mit einer Warnmeldung) und ohne Fehler ordnungsgemäß verknüpft jedoch erzeugt kein Code auf `funcn( )`. Damit dies ordnungsgemäß funktioniert fügen Sie den Funktionsaufruf-Operator "()" hinzu.  
  
```  
#include <stdio.h>  
void funcn();  
  
int main() {  
   funcn;      /* missing function call operator;   
                  call will fail.  Use funcn() */  
   }  
  
void funcn() {  
   printf("\nHello World\n");  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Codeoptimierung](../../build/reference/optimizing-your-code.md)