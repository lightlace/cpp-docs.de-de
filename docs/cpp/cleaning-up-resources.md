---
title: "Bereinigen von Ressourcen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, Beendigungshandler"
  - "Ausnahmebehandlung, Bereinigen von Ressourcen"
  - "Ausnahmebehandlung, Bereinigungscode"
  - "Ressourcen [C++], Bereinigung"
  - "Beendigungshandler, Bereinigen von Ressourcen"
  - "try-catch-Schlüsselwort [C++], Beendigungshandler"
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Bereinigen von Ressourcen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Während der Ausführung des Beendigungshandlers wissen Sie möglicherweise nicht, welche Ressourcen tatsächlich zugeordnet wurden, bevor der Beendigungshandler aufgerufen wurde.  Es ist möglich, dass der `__try`\-Anweisungsblock unterbrochen wurde, bevor alle Ressourcen zugeordnet wurden, sodass nicht alle Ressourcen geöffnet wurden.  
  
 Vorsichtshalber sollten Sie daher überprüfen, welche Ressourcen tatsächlich geöffnet sind, bevor Sie die Bereinigung der Abbruchbehandlung fortsetzen.  Dazu wird diese Vorgehensweise empfohlen:  
  
1.  Initialisieren Sie die Handles mit dem Wert NULL.  
  
2.  Ordnen Sie im `__try`\-Anweisungsblock Ressourcen zu.  Beim Zuordnen der Ressourcen werden positive Werte für die Handles festgelegt.  
  
3.  Im `__finally`\-Anweisungsblock geben Sie alle Ressourcen frei, deren entsprechender Handle oder deren entsprechende Flagvariable ungleich 0 oder nicht NULL ist.  
  
## Beispiel  
 Beispielsweise verwendet der folgende Code einen Beendigungshandler, um drei Dateien und einen Speicherblock zu schließen, die im `__try`\-Anweisungsblock zugeordnet wurden.  Bevor eine Ressource bereinigt wird, überprüft der Code zunächst, ob die Ressource zugeordnet wurde.  
  
```  
// exceptions_Cleaning_up_Resources.cpp  
#include <stdlib.h>  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void fileOps() {  
   FILE  *fp1 = NULL,  
         *fp2 = NULL,  
         *fp3 = NULL;  
   LPVOID lpvoid = NULL;  
   errno_t err;  
  
   __try {  
      lpvoid = malloc( BUFSIZ );  
  
      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );  
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );  
      err = fopen_s(&fp3, "CARS.DAT", "w+" );  
   }  
   __finally {  
      if ( fp1 )  
         fclose( fp1 );  
      if ( fp2 )  
         fclose( fp2 );  
      if ( fp3 )  
         fclose( fp3 );  
      if ( lpvoid )  
         free( lpvoid );  
   }  
}  
  
int main() {  
   fileOps();  
}  
```  
  
## Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)