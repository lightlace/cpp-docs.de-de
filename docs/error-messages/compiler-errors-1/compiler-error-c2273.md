---
title: "Compilerfehler C2273 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2273"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2273"
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2273
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Unzulässig auf der rechten Seite '\-\>' des Operators  
  
 Als rechter Operand des Operators `->` wird ein Typ angezeigt.  
  
 Dieser Fehler kann auftreten, wenn auf eine benutzerdefinierte Typkonvertierung zugegriffen wird.  Verwenden Sie das `operator`\-Schlüsselwort zwischen \-\> und `type`.  
  
 Im folgenden Beispiel wird C2273 generiert:  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```