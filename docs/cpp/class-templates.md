---
title: "Klassenvorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassenvorlagen"
  - "Klassen [C++], Anwenden auf Typ"
  - "Vorlagen, Klassenvorlagen"
ms.assetid: 633a53c8-24ee-4c23-8c88-e7c3cb0b7ac3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Klassenvorlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie Klassenvorlagen, um eine Gruppe von Klassen zu erstellen, die für einen Typ angewendet werden.  Klassenvorlagen sind parametrisierte Typen.  Sie beinhalten, dass für jeden denkbaren Wert der übergebenen Parameter \(bezeichnet als Vorlagenargumente\) eine separate Klasse erstellt werden kann.  
  
 Vorlagenargumente können Typen oder konstante Werte eines bestimmten Typs sein.  Beispiel:  
  
```  
// class_templates.cpp  
template <class T, int i> class TempClass   
{  
public:  
    TempClass( void );  
    ~TempClass( void );  
    int MemberSet( T a, int b );  
private:  
    T Tarray[i];  
    int arraysize;  
};  
  
int main()  
{  
}  
```  
  
 In diesem Beispiel verwendet die auf Vorlagen basierende Klasse zwei Parameter, den Typ `T` und die "int" `i`.  Dem `T`\-Parameter können beliebige Typen übergeben werden, einschließlich Strukturen und Klassen.  Dem `i`\-Parameter muss eine Ganzzahlkonstante übergeben werden.  Da `i` eine Konstante ist, die zur Kompilierzeit definiert wird, können Sie ein Memberarray der Größe `i` mithilfe einer standardmäßigen Arraydeklaration definieren.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Member von Klassenvorlagen](../Topic/Members%20of%20Class%20Templates.md)  
  
-   [Vorlagen für Klassenmember](../Topic/Templates%20for%20Class%20Members.md)  
  
-   [Memberfunktionen von Vorlagenklassen](../Topic/Member%20Functions%20of%20Template%20Classes.md)  
  
-   [Geschachtelte Klassenvorlagen](../Topic/Nested%20Class%20Templates.md)  
  
-   [Klassenvorlageninstanziierung](../Topic/Class%20Template%20Instantiation.md)  
  
-   [Explizite Spezialisierung von Klassenvorlagen](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)  
  
-   [Partielle Spezialisierung von Klassenvorlagen](../cpp/template-specialization-cpp.md)  
  
-   [Standardargumente für Klassenvorlagen](../Topic/Default%20Arguments%20for%20Class%20Templates.md)  
  
-   [Friend\-Vorlagen](../cpp/template-friends.md)  
  
## Siehe auch  
 [Vorlagen](../cpp/templates-cpp.md)