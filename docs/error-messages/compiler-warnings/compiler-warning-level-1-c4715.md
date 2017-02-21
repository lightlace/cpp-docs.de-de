---
title: "Compilerwarnung (Stufe 1) C4715 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4715"
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Nicht alle Steuerelementpfade geben einen Wert zurück  
  
 Die angegebene Funktion kann unter gewissen Umständen kein Ergebnis zurückgeben.  
  
## Beispiel  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 Um diese Warnung zu verhindern, ändern Sie den Code so, dass der Funktion durch alle Pfade ein Rückgabewert zugewiesen wird:  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 Der Code kann aber auch den Aufruf einer Funktion enthalten, durch die niemals ein Wert zurückgegeben wird. Siehe folgendes Beispiel:  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 Dieser Code generiert ebenfalls eine Warnung, da der Compiler nicht weiß, dass `fatal` niemals zurückgegeben wird.  Um zu verhindern, dass dieser Code eine Fehlermeldung erzeugt, deklarieren Sie `fatal` unter Verwendung von [\_\_declspec\(noreturn\)](../../cpp/noreturn.md).