---
title: "if-else-Anweisung (C++)"
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
  - "else_cpp"
  - "else"
  - "if_cpp"
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "else-Schlüsselwort [C++]"
  - "if-Schlüsselwort [C++]"
  - "if-Schlüsselwort [C++], if-else"
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# if-else-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Steuert die bedingte Verzweigung.  
  
## Syntax  
  
```  
  
      if ( expression )  
   statement1  
[else  
   statement2]  
```  
  
## Hinweise  
 Wenn der Wert von *expression* ungleich 0 \(null\) ist, wird *statement1* ausgeführt.  Wenn das optionale **else** vorhanden ist, wird *statement2* ausgeführt, wenn der Wert von *expression* 0 \(null\) ist.  *expression* muss vom arithmetischen Typ oder vom Zeigertyp sein, oder es muss von einem Klassentyp sein, der eine eindeutige Konvertierung in einen arithmetischen Typ oder Zeigertyp definiert. \(Weitere Informationen über Konvertierungen finden Sie unter [Standardkonvertierungen](../cpp/standard-conversions.md)\).  
  
 In beiden Formen der **if**\-Anweisung wird *expression* \(kann einen beliebigen Wert außer einer Struktur aufweisen\) ausgewertet, einschließlich aller Nebeneffekte.  Das Steuerelement wird von der **if**\-Anweisung an die nächste Anweisung im Programm übergeben, es sei denn, eine der *\-Anweisung*en enthält [break](../cpp/break-statement-cpp.md), [continue](../cpp/continue-statement-cpp.md) oder [goto](../cpp/goto-statement-cpp.md).  
  
 Die **else**\-Klausel einer `if...else`\-Anweisung wird der nächststehenden vorangegangenen **if**\-Anweisung zugewiesen, im gleichen Gültigkeitsbereich, der keine entsprechende **else**\-Anweisung aufweist.  
  
 Damit dieses Beispiel eindeutig ist bezüglich `if...else`\-Kopplung, heben Sie die Auskommentierung der Klammern auf.  
  
## Beispiel  
  
```  
// if_else_statement.cpp  
#include <stdio.h>  
  
int main()   
{  
   int x = 0;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n");  
   }  
   else  
   {  
      printf_s("x is not 0!\n"); // this statement will not be executed  
   }  
  
   x = 1;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n"); // this statement will not be executed  
   }  
   else  
   {  
      printf_s("x is not 0!\n");  
   }  
  
   return 0;  
}  
```  
  
  **x ist 0\!**  
**x ist nicht 0\!**   
## Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [switch\-Anweisung \(C\+\+\)](../cpp/switch-statement-cpp.md)