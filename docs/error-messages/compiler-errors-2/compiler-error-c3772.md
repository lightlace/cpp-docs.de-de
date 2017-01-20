---
title: "Compilerfehler C3772"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3772"
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Name": Ungültige Friend\-Vorlagendeklaration.  
  
 Es ist unzulässig, einen "Friend" einer Spezialisierung einer Klassenvorlage zu deklarieren. Sie können keine explizite oder partielle Spezialisierung einer Klassenvorlage deklarieren und in derselben Anweisung einen "Friend" dieser Spezialisierung deklarieren. Die *Name*\-Platzhalter identifiziert die ungültige Deklaration.  
  
### So beheben Sie diesen Fehler  
  
-   Sie sollten keinen "Friend" der Spezialisierung einer Klassenvorlage deklarieren.  
  
-   Deklarieren Sie einen "Friend" der Klassenvorlage oder einen "Friend" einer bestimmten partiellen oder expliziten Spezialisierung, sofern dies für Ihre Anwendung geeignet ist.  
  
## Beispiel  
 Im folgenden Codebeispiel tritt ein Fehler auf, da ein "Friend" einer partiellen Spezialisierung einer Klassenvorlage deklariert wird.  
  
```  
// c3772.cpp // compile with: /c // A class template. template<class T> class A {}; // A partial specialization of the class template. template<class T> class A<T*> {}; // An explicit specialization. template<> class A<char>; class X { // Invalid declaration of a friend of a partial specialization. template<class T> friend class A<T*>; // C3772 // Instead, if it is appropriate for your application, declare a // friend of the class template. Consequently, all specializations // of the class template are friends: //    template<class T> friend class A; // Or declare a friend of a particular partial specialization: //    friend class A<int*>; // Or declare a friend of a particular explicit specialization: //    friend class A<char>; };  
```  
  
## Siehe auch  
 [Vorlagenspezifikationen](../Topic/Template%20Specifications.md)   
 [Partielle Spezialisierung von Klassenvorlagen](../../cpp/template-specialization-cpp.md)   
 [Explizite Spezialisierung von Klassenvorlagen](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)