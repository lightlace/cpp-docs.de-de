---
title: "return-Anweisung (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "return"
  - "return_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "return-Schlüsselwort [C++]"
  - "return-Schlüsselwort [C++], Syntax"
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# return-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beendet die Ausführung einer Funktion und gibt die Steuerung an die aufrufende Funktion zurück \(oder an das Betriebssystem, wenn Sie die Steuerung von der `main`\-Funktion übertragen\).  Die Ausführung wird in der aufrufenden Funktion an dem Punkt fortgesetzt, der dem Aufruf unmittelbar folgt.  
  
## Syntax  
  
```  
return [expression];  
```  
  
## Hinweise  
 Die Klausel `expression` wird, sofern vorhanden, in den Typ konvertiert, der in der Funktionsdeklaration angegeben wird, als ob eine Initialisierung durchgeführt würde.  Eine Konvertierung vom Typ des Ausdrucks in den `return`\-Typ der Funktion kann temporäre Objekte erstellen.  Weitere Informationen darüber, wie und wann temporäre Objekte erstellt werden, finden Sie unter [Temporäre Objekte](../cpp/temporary-objects.md).  
  
 Der Wert der `expression`\-Klausel wird an die aufrufende Funktion zurückgegeben.  Wenn der Ausdruck ausgelassen wird, wird der Rückgabewert der Funktion nicht definiert.  Konstruktoren und Destruktoren sowie Funktionen des Typs `void`, `` können keinen Ausdruck in der `return`\-Anweisung angeben.  Funktionen aller anderen Typen müssen einen Ausdruck in der `return`\-Anweisung angeben.  
  
 Wenn die Ablaufsteuerung den Block verlässt, der die Funktionsdefinition einschließt, ist das Ergebnis das gleiche wie beim Ausführen der `return`\-Anweisung ohne einen Ausdruck.  Dies ist ungültig bei Funktionen, die mit Rückgabewert deklariert werden.  
  
 Eine Funktion kann eine beliebige Anzahl von `return`\-Anweisungen aufweisen.  
  
 Im folgenden Beispiel wird ein Ausdruck mit einer `return`\-Anweisung verwendet, um die größte von zwei ganzen Zahlen zu erhalten.  
  
## Beispiel  
  
```  
// return_statement2.cpp  
#include <stdio.h>  
  
int max ( int a, int b )  
{  
   return ( a > b ? a : b );  
}  
  
int main()  
{  
    int nOne = 5;  
    int nTwo = 7;  
  
    printf_s("\n%d is bigger\n", max( nOne, nTwo ));  
}  
```  
  
## Siehe auch  
 [Sprunganweisungen](../cpp/jump-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)