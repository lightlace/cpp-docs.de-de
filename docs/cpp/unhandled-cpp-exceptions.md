---
title: "Nicht behandelte C++-Ausnahmen"
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
  - "C++-Ausnahmebehandlung, Nicht behandelte Ausnahmen"
  - "catch-Schlüsselwort [C++], Handler nicht gefunden"
  - "Ereignishandler, Nicht behandelte Ausnahmen"
  - "Ausnahmen, Unbehandelt"
  - "Nicht behandelte Ausnahmen"
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Nicht behandelte C++-Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn kein entsprechender Handler \(oder Auslassungszeichen\-**catch**\-Handler\) für die aktuelle Ausnahme gefunden werden kann, wird die vordefinierte `terminate`\-Laufzeitfunktion aufgerufen. \(Sie können auch `terminate` in jedem Ihrer Handler explizit aufrufen.\) Der Standardvorgang von `terminate` besteht darin, `abort` aufzurufen.  Wenn `terminate` eine andere Funktion in Ihrem Programm aufrufen soll, bevor Sie die Anwendung beenden, rufen Sie die `set_terminate`\-Funktion mit dem Funktionsnamen auf, der als sein einzelnes Argument aufgerufen werden soll.  Sie können `set_terminate` an jedem Punkt im Programm aufrufen.  Die `terminate` \-Routine ruft immer die letzte Funktion auf, die für `set_terminate` als Argument angegeben wurde.  
  
## Beispiel  
 Das folgende Beispiel löst eine `char *`\-Ausnahme aus, aber es enthält keinen Handler, der dazu vorgesehen ist, Ausnahmen des Typs `char *` zu erfassen.  Der Aufruf von `set_terminate` weist `terminate` an, `term_func` aufzurufen.  
  
```  
// exceptions_Unhandled_Exceptions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void term_func() {  
   cout << "term_func was called by terminate." << endl;  
   exit( -1 );  
}  
int main() {  
   try  
   {  
      set_terminate( term_func );  
      throw "Out of memory!"; // No catch handler for this exception  
   }  
   catch( int )  
   {  
      cout << "Integer exception raised." << endl;  
   }  
   return 0;  
}  
```  
  
## Ausgabe  
  
```  
term_func was called by terminate.  
```  
  
 Die `term_func`\-Funktion muss das Programm oder den aktuellen Thread beenden, idealerweise mit dem Aufruf von `exit`.  Wenn stattdessen eine Rückkehr zum Aufruf erfolgt, wird `abort` aufgerufen.  
  
## Siehe auch  
 [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)