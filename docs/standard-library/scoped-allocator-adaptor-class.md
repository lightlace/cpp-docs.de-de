---
title: "scoped_allocator_adaptor-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std.scoped_allocator_adaptor"
  - "scoped_allocator_adaptor"
  - "scoped_allocator/std::scoped_allocator_adaptor"
  - "std::scoped_allocator_adaptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scoped_allocator_adaptor-Klasse"
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
caps.latest.revision: 10
caps.handback.revision: "1"
ms.author: "corob"
manager: "ghogen"
---
# scoped_allocator_adaptor-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Nest von Zuweisungen dar.  
  
## Syntax  
  
```cpp  
template<class Outer, class... Inner>  
    class scoped_allocator_adaptor;  
```  
  
## Hinweise  
 Die Vorlagenklasse kapselt ein Nest mehrere Zuweisungen.  Jede dieser Klasse enthält eine äußerste Zuweisung des Typs `outer_allocator_type`, ein Synonym für `Outer`, die eine öffentliche Basis des `scoped_allocator_adaptor`\-Objekts ist.  `Outer` wird verwendet, um Speicher reserviert, durch einen Container verwendet werden.  Sie können einen Verweis auf dieses Zuweisungsbasisobjekt abrufen, indem Sie `outer_allocator` aufrufen.  
  
 Der Rest des Nestes ist vom Typ `inner_allocator_type`.  Eine interne Zuweisung wird verwendet, um für Elemente innerhalb eines Containers Speicher zu belegen.  Sie können einen Verweis auf dem gespeicherten Objekt dieses Typs abrufen, indem Sie `inner_allocator` aufrufen.  Wenn `Inner...` nicht leer ist, ist `inner_allocator_type` vom Typ `scoped_allocator_adaptor<Inner...>`, und `inner_allocator` legt ein Memberobjekt fest.  Andernfalls ist `inner_allocator_type` vom Typ `scoped_allocator_adaptor<Outer>`, und `inner_allocator` legt das gesamte Objekt fest.  
  
 Das Nest verhält, als ob beliebige Tiefe hat und ggf. repliziert die innerste gekapselte Zuweisung.  
  
 Einige Konzepte, die kein Teil der sichtbaren Schnittstellenhilfe sind, wenn sie das Verhalten dieser Vorlagenklasse beschreiben.  Eine *Zuweisung äußerste* übergibt alle Aufrufe Konstrukt und zerstört Methoden.  Es wird effektiv von der rekursiven Funktion `OUTERMOST(X)` definiert, wobei `OUTERMOST(X)` einen der folgenden ist.  
  
-   Wenn `X.outer_allocator()` wohl geformt ist, wird `OUTERMOST(X)``OUTERMOST(X.outer_allocator())`.  
  
-   Andernfalls ist `OUTERMOST(X)` `X`.  
  
 Drei Typen werden um der Veröffentlichung willen definiert:  
  
|Typ|**Beschreibung**|  
|---------|----------------------|  
|`Outermost`|Der `OUTERMOST(*this)`\-Typ.|  
|`Outermost_traits`|`allocator_traits<Outermost>`|  
|`Outer_traits`|`allocator_traits<Outer>`|  
  
### Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scoped\_allocator\_adaptor::scoped\_allocator\_adaptor\-Konstruktor](../Topic/scoped_allocator_adaptor::scoped_allocator_adaptor%20Constructor.md)|Erstellt ein `scoped_allocator_adaptor`\-Objekt.|  
  
### Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`const_pointer`|Dieser Typ ist ein Synonym für `const_pointer`, das mit der Zuweisung `Outer` zugeordnet ist.|  
|`const_void_pointer`|Dieser Typ ist ein Synonym für `const_void_pointer`, das mit der Zuweisung `Outer` zugeordnet ist.|  
|`difference_type`|Dieser Typ ist ein Synonym für `difference_type`, das mit der Zuweisung `Outer` zugeordnet ist.|  
|`inner_allocator_type`|Dieser Typ ist ein Synonym für den Typ des geschachtelten Adapters `scoped_allocator_adaptor<Inner...>`.|  
|`outer_allocator_type`|Dieser Typ ist ein Synonym für den Typ der Basisklasse Zuweisung `Outer`.|  
|`pointer`|Dieser Typ ist ein Synonym für `pointer`, das mit der Zuweisung `Outer` zugeordnet ist.|  
|`propagate_on_container_copy_assignment`|Die Typgriffe werden nur wenn `Outer_traits::propagate_on_container_copy_assignment` beinhaltet true oder `inner_allocator_type::propagate_on_container_copy_assignment` als "true" aus.|  
|`propagate_on_container_move_assignment`|Die Typgriffe werden nur wenn `Outer_traits::propagate_on_container_move_assignment` beinhaltet true oder `inner_allocator_type::propagate_on_container_move_assignment` als "true" aus.|  
|`propagate_on_container_swap`|Die Typgriffe werden nur wenn `Outer_traits::propagate_on_container_swap` beinhaltet true oder `inner_allocator_type::propagate_on_container_swap` als "true" aus.|  
|`size_type`|Dieser Typ ist ein Synonym für `size_type`, das mit der Zuweisung `Outer` zugeordnet ist.|  
|`value_type`|Dieser Typ ist ein Synonym für `value_type`, das mit der Zuweisung `Outer` zugeordnet ist.|  
|`void_pointer`|Dieser Typ ist ein Synonym für `void_pointer`, das mit der Zuweisung `Outer` zugeordnet ist.|  
  
### Strukturen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scoped\_allocator\_adaptor::rebind\-Struktur](../Topic/scoped_allocator_adaptor::rebind%20Struct.md)|Definiert den Typ `Outer::rebind<Other>::other` als Synonym für `scoped_allocator_adaptor<Other, Inner...>`.|  
  
### Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scoped\_allocator\_adaptor::allocate\-Methode](../Topic/scoped_allocator_adaptor::allocate%20Method.md)|Belegt mithilfe der Zuweisung `Outer` Speicher.|  
|[scoped\_allocator\_adaptor::construct\-Methode](../Topic/scoped_allocator_adaptor::construct%20Method.md)|Erstellt ein Objekt.|  
|[scoped\_allocator\_adaptor::deallocate\-Methode](../Topic/scoped_allocator_adaptor::deallocate%20Method.md)|Gibt Objekte mithilfe der äußeren Zuweisung frei.|  
|[scoped\_allocator\_adaptor::destroy\-Methode](../Topic/scoped_allocator_adaptor::destroy%20Method.md)|Zerstört ein gegebenes Objekt.|  
|[scoped\_allocator\_adaptor::inner\_allocator\-Methode](../Topic/scoped_allocator_adaptor::inner_allocator%20Method.md)|Ruft einen Verweis auf dem gespeicherten Objekt des Typs `inner_allocator_type` ab.|  
|[scoped\_allocator\_adaptor::max\_size\-Methode](../Topic/scoped_allocator_adaptor::max_size%20Method.md)|Bestimmt die maximale Anzahl von Objekten, die von der äußeren Zuweisung zugeordnet werden können.|  
|[scoped\_allocator\_adaptor::outer\_allocator\-Methode](../Topic/scoped_allocator_adaptor::outer_allocator%20Method.md)|Ruft einen Verweis auf dem gespeicherten Objekt des Typs `outer_allocator_type` ab.|  
|[scoped\_allocator\_adaptor::select\_on\_container\_copy\_construction\-Methode](../Topic/scoped_allocator_adaptor::select_on_container_copy_construction%20Method.md)|Erstellt ein neues `scoped_allocator_adaptor`\-Objekt mit jedem gespeicherten Zuweisungsobjekt, das durch Aufrufen von `select_on_container_copy_construction` für jede äquivalente Zuweisung neu initialisiert wird.|  
  
## Anforderungen  
 **Header:** \<scoped\_allocator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)