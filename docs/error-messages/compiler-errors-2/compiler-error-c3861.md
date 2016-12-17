---
title: "Compilerfehler C3861"
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
  - "C3861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3861"
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': Bezeichner nicht gefunden  
  
 Der Compiler konnte einen Verweis sogar mit der Suche „argument\-dependent“ zu einem Bezeichner nicht auflösen.  
  
 Prüfen Sie zum Beheben dieses Fehlers die Identifziererdeklaration hinsichtlich Groß\-\/Kleinschreibung und Rechtschreibung.  Stellen Sie sicher, dass die [Bereichsauflösungsoperatoren](../../cpp/scope-resolution-operator.md) und Namespace [mithilfe von Direktiven](../../misc/using-directive-cpp.md) ordnungsgemäß verwendet werden.  Wenn der Bezeichner in einer Headerdatei deklariert wird, muss der Header einbezogen werden, bevor er referenziert wird.  Prüfen Sie zudem, dass der Identifizierer durch die [Direktiven für die bedingte Kompilierung](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) nicht ausgeschlossen wird.  
  
## Beispiel  
 Im folgenden Beispiel wird C3861 generiert:  
  
```  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## Beispiel  
 Ausnahmeklassen in der C\+\+\-Standardbibliothek sind jetzt im `std`\-Namespace.  
  
```  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```