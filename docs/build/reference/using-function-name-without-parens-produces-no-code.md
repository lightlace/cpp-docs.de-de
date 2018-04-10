---
title: Verwendung eines Funktionsnamens ohne () kein Code erzeugt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c03706be0b9853cbbdebe79b58e410f7237692ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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