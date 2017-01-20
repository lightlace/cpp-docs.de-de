---
title: "Compilerfehler C2050"
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
  - "C2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2050"
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Switch\-Ausdruck ist keine Ganzzahl  
  
 Der `switch`\-Ausdruck ergibt keine ganze Zahl.  Um den Fehler zu beheben, verwenden Sie in `switch`\-Anweisungen ausschließlich ganzzahlige Werte.  
  
 Im folgenden Beispiel wird C2050 generiert:  
  
```  
// C2050.cpp  
int main() {  
   int a = 1;  
   switch ("a") {   // C2050  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2050b.cpp  
int main() {  
   int a = 1;  
   switch (a) {  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```