---
title: "Compilerfehler C2051"
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
  - "C2051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2051"
ms.assetid: 81c0469a-78e2-49fa-bd76-97cdb135e3ea
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

case\-Ausdruck ist keine Konstante  
  
 **Case**\-Ausdrücke müssen ganzzahlige Konstanten sein.  
  
 Im folgenden Beispiel wird C2051 generiert:  
  
```  
// C2051.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case x:   // C2051 use constant expression to resolve error  
         break;  
      default:  
         break;  
   }  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2051b.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```