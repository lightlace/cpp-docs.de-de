---
title: "allocator_base-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators.allocator_base"
  - "stdext.allocators.allocator_base"
  - "allocator_base"
  - "allocators/stdext::allocator_base"
  - "stdext::allocator_base"
  - "stdext::allocators::allocator_base"
  - "allocators/stdext::allocators::allocator_base"
  - "allocators::allocator_base"
  - "stdext.allocator_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_base-Klasse"
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# allocator_base-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Basisklasse und allgemeine Funktionen, die zum Erstellen einer benutzerdefinierten Zuweisung von einem Synchronisierungsfilter erforderlich sind.  
  
## Syntax  
  
```  
template <class Type, class Sync> class allocator_base  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Type`|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|  
|`Sync`|Die Synchronisierungsrichtlinie für die Zuweisung: [sync\_none\-Klasse](../standard-library/sync-none-class.md), [sync\_per\_container\-Klasse](../standard-library/sync-per-container-class.md), [sync\_per\_thread\-Klasse](../standard-library/sync-per-thread-class.md) oder [sync\_shared\-Klasse](../standard-library/sync-shared-class.md).|  
  
### Konstruktoren  
  
|||  
|-|-|  
|[allocator\_base](../Topic/allocator_base::allocator_base.md)|Konstruiert ein Objekt vom Typ `allocator_base`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator_base::const_pointer.md)|Ein Typ, der einen konstanten Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[const\_reference](../Topic/allocator_base::const_reference.md)|Ein Typ, der einen konstanten Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[difference\_type](../Topic/allocator_base::difference_type.md)|Ein ganzzahliger Typ mit Vorzeichen, der die Differenz zwischen Werten von Zeigern und dem Typ des Objekts, das von der Zuweisung verwaltet wird, darstellen kann.|  
|[pointer](../Topic/allocator_base::pointer.md)|Ein Typ, der einen Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[Verweis](../Topic/allocator_base::reference.md)|Ein Typ, der einen Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|  
|[size\_type](../Topic/allocator_base::size_type.md)|Ein ganzzahliger Typ ohne Vorzeichen, der die Länge einer beliebigen Sequenz darstellen kann, die ein Objekt der Vorlagenklasse `allocator_base` zuordnen kann.|  
|[value\_type](../Topic/allocator_base::value_type.md)|Ein Typ, der von der Zuweisung verwaltet wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[\_Charalloc](../Topic/allocator_base::_Charalloc.md)|Ordnet einem Array des Typs `char` Speicherplatz zu.|  
|[\_Chardealloc](../Topic/allocator_base::_Chardealloc.md)|Gibt für das Array mit Elementen vom Typ `char` Speicherplatz frei.|  
|[Adresse](../Topic/allocator_base::address.md)|Sucht die Adresse eines Objekts, dessen Wert angegeben wird.|  
|[allocate](../Topic/allocator_base::allocate.md)|Ordnet einen Speicherblock zu, der groß genug ist, um mindestens eine angegebene Anzahl von Elementen zu speichern.|  
|[Konstrukt](../Topic/allocator_base::construct.md)|Erstellt eine bestimmte Art von Objekt an einer bestimmten Adresse, die mit einem angegebenen Wert initialisiert wird.|  
|[Aufheben der Zuordnung](../Topic/allocator_base::deallocate.md)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
|[destroy](../Topic/allocator_base::destroy.md)|Ruft einen Objektdestruktor auf, ohne die Zuordnung des Speicherplatzes aufzuheben, an dem Objekt gespeichert wurde.|  
|[max\_size](../Topic/allocator_base::max_size.md)|Gibt die Anzahl der Elemente vom Typ `Type` zurück, die von einem Objekt der Klassenzuweisung zugeordnet werden konnten, bevor der freie Speicherplatz verbraucht ist.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)