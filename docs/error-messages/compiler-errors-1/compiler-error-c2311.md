---
title: "Compilerfehler C2311"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2311"
ms.assetid: 1aff9bd5-ed0b-4db6-bbc0-01ac89850cf2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Ausnahme': wurde aufgefangen durch '...', in Zeile \<Nummer\>  
  
 Der catch\-Handler für das Auslassungszeichen \(...\) muss der letzte Handler einer ausgelösten Ausnahme sein.  
  
 Im folgenden Beispiel wird C2311 generiert:  
  
```  
// C2311.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( ... ) {}  
   catch( int ) {}   // C2311  ellipsis handler not last catch  
}  
```