---
title: "Compilerwarnung (Stufe 4) C4706 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4706"
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zuweisung in bedingtem Ausdruck  
  
 Der Testwert in einem bedingten Ausdruck war das Ergebnis einer Zuweisung.  
  
 Eine Zuweisung hat einen Wert \(den Wert auf der linken Seite einer Zuweisung\), der auch in einem anderen Ausdruck verwendet werden kann, z. B. in einem Testausdruck.  
  
 Im folgenden Beispiel wird C4706 generiert:  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 Die Warnung wird selbst dann ausgegeben, wenn Sie die Testbedingung in doppelte Klammern setzen:  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 Wenn lediglich eine Beziehung getestet werden und keine Zuweisung erfolgen soll, verwenden Sie den Operator `==`.  In der folgenden Zeile wird getestet, ob "a" und "b" gleich sind:  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 Falls der Testwert zum Ergebnis einer Zuweisung werden soll, sollten Sie die Zuweisung auch darauf testen, dass sie ungleich 0 oder nicht NULL ist.  Im folgenden Code wird diese Warnung z. B. nicht generiert:  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```