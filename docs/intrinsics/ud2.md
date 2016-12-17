---
title: "__ud2"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "__ud2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UD2-Anweisung"
  - "__ud2 (systemintern)"
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# __ud2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert eine nicht definierte Anweisung.  
  
## Syntax  
  
```  
void __ud2();  
```  
  
## Hinweise  
 Der Prozessor löst eine ungültige Opcode\-Ausnahme aus, wenn Sie eine nicht definierte Anweisung ausführen.  
  
 Die `__ud2`\-Funktion ähnelt dem `UD2` Computeranweisung, und ist nur im Kernelmodus verfügbar.  Weitere Informationen Suche nach dem Dokument, das Handbuch „des Intel\-Architektur\-Softwareentwicklers, Volume 2: Anweisungs\-festgelegter Verweis“ auf der Website [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) .  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__ud2`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## BEENDEN Sie Microsoft\-Besonderen  
  
## Beispiel  
 Das folgende Beispiel führt eine nicht definierte Anweisung aus, die eine Ausnahme auslöst.  Der Ausnahmehandler ändert dann den Rückgabecode von Null in einen anderen.  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
  **Vor \_\_ud2 \(\).  Rückgabecode \= 0.  Im Ausnahmehandler.  Nach \_\_ud2 \(\).  Rückgabecode \= 1.**    
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)