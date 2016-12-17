---
title: "Compilerwarnung (Stufe 1) C4144"
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
  - "C4144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4144"
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Ausdruck': Relationaler Ausdruck als Schalterausdruck  
  
 Der angegebene relationale Ausdruck wurde als steuernder Ausdruck einer [switch](../../cpp/switch-statement-cpp.md)\-Anweisung verwendet.  Die verknüpften **case**\-Anweisungen erhalten boolesche Werte.  Im folgenden Beispiel wird C4144 generiert:  
  
```  
// C4144.cpp  
// compile with: /W1  
int main()  
{  
   int i = 0;  
   switch(!i) {   // C4144, remove the ! to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```