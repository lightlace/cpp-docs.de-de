---
title: "Compilerfehler C2274 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2274"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2274"
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2274
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Unzulässig auf der rechten Seite des Operators "."  
  
 Als rechter Operand des Memberzugriffsoperators \(.\) wird ein Typ angezeigt.  
  
 Dieser Fehler kann auftreten, wenn auf eine benutzerdefinierte Typkonvertierung zugegriffen wird.  Fügen Sie das Schlüsselwort `operator` zwischen dem Punkt und `type` ein.  
  
 Im folgenden Beispiel wird C2286 generiert:  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```