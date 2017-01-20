---
title: "Bei Verwendung eines Funktionsnamens ohne &quot;()&quot; wird kein Code generiert"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionen [C++], Ohne Klammern"
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Bei Verwendung eines Funktionsnamens ohne &quot;()&quot; wird kein Code generiert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn ein im Programm deklarierter Funktionsname ohne Klammern verwendet wird, generiert der Compiler keinen Code.  Die geschieht unabhängig davon, ob die Funktion Parameter erwartet oder nicht, da der Compiler die Funktionsadresse berechnet. Da jedoch der Aufrufoperator "\(\)" nicht vorhanden ist, wird kein Aufruf ausgeführt.  Das Ergebnis ist ähnlich dem folgenden Beispiel:  
  
```  
// compile with /Wall to generate a warning  
int a;  
a;      // no code generated here either  
```  
  
 In Visual C\+\+ wird nicht einmal bei Warnstufe 4 eine diagnostische Ausgabe generiert.  Es wird keine Warnung ausgegeben und kein Code generiert.  
  
 Der Beispielcode weiter unten wird \(mit einer Warnung\) kompiliert und ohne Fehlermeldungen korrekt verknüpft. Dennoch wird beim Verweis auf `funcn( )` kein Code generiert.  Damit der Code korrekt kompiliert wird, fügen Sie den Aufrufoperator "\(\)" hinzu.  
  
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
  
## Siehe auch  
 [Codeoptimierung](../../build/reference/optimizing-your-code.md)