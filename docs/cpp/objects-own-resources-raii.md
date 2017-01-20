---
title: "Objekteigene Ressourcen (RAII)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Objekteigene Ressourcen (RAII)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Überprüfen Sie ob Objekte eigene Ressourcen.  Dieses Prinzip wird auch als "Ressourcendatenerfassung ist Initialisierung" oder "RAII."  
  
## Beispiel  
 Führen Sie jedes "neue" Objekt als Konstruktorargument in einen anderen benannten Objekt, das es besitzt \(fast immer unique\_ptr\).  
  
```cpp  
void f() {  
  unique_ptr<widget> p( new widget(…) );  
  my_class x( new widget() );  
  …  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if “finally { p->dispose(); x.w.dispose(); }”  
  
```  
  
 Führen Sie stets direkt jede neue Ressource auf ein anderes Objekt, das dieser besitzt.  
  
```cpp  
void g() {  
  other_class y( OpenFile() );  
  …  
} // automatic closing and release for file resource  
  // automatic exception safety, as if “finally { y.file.dispose(); }”  
  
```  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)