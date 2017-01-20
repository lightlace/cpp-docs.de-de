---
title: "initializer_list Class"
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
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
caps.latest.revision: 17
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# initializer_list Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bietet Zugriff auf ein Array von Elementen, in dem jedes Mitglied von einem angegebenen Typ ist.  
  
## Syntax  
  
```cpp  
template<  
    class Type >  
    class initializer_list  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`_Elem`|Der in `initializer_list` zu speichernde Elementdatentyp.|  
|`_First`|Der Zeiger auf das erste Element der `initializer_list`.|  
|`_Last`|Der Zeiger auf das letzte Element der `initializer_list`.|  
  
## Hinweise  
 Ein `initializer_list`\-Element kann mit einer Initialisiererliste in Klammern erstellt werden:  
  
```cpp  
initializer_list<int> i1{ 1, 2, 3, 4 };  
```  
  
 Der Compiler transformiert in Klammern gesetzte Initialisiererlisten mit homogenen Elementen in `initializer_list`, wenn für die Funktionssignatur `initializer_list` erforderlich ist.  Ausführlichere Informationen zum Verwenden von `initializer_list` finden Sie unter [Einheitliche Initialisierung und Delegierung von Konstruktoren](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[initializer\_list](../Topic/forward_list::forward_list.md)|Konstruiert ein Objekt vom Typ `initializer_list`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|value\_type|Der Typ der Elemente im `initializer_list`.|  
|Verweis|Ein Typ, der einen Verweis auf ein in der `initializer_list` gespeichertes Element bereitstellt.|  
|const\_reference|Ein Typ, der einen Konstantenverweis auf ein in der `initializer_list` gespeichertes Element bereitstellt.|  
|size\_type|Ein Typ, der die Anzahl von Elementen in der `initializer_list` darstellt.|  
|Iterator|Ein Typ, der einen Iterator für die `initializer_list` bereitstellt.|  
|const\_iterator|Ein Typ, der einen konstanten Iterator für die `initializer_list` bereitstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[begin](../Topic/initializer_list::begin.md)|Gibt einen Zeiger auf das erste Element in einer `initializer_list` zurück.|  
|[end](../Topic/initializer_list::end.md)|Gibt einen Zeiger auf das Element hinter dem letzten Element in einer `initializer_list` zurück.|  
|[size](../Topic/initializer_list::size.md)|Gibt die Anzahl von Elementen in der `initializer_list` zurück.|  
  
## Anforderungen  
 **Header:** \<initializer\_list\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<forward\_list\>](../standard-library/forward-list.md)