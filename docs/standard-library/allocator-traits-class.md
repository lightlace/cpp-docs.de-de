---
title: "allocator_traits-Klasse"
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
  - "memory/std::allocator_traits"
  - "memory/std::allocator_traits::propagate_on_container_move_assignment"
  - "memory/std::allocator_traits::const_pointer"
  - "memory/std::allocator_traits::propagate_on_container_swap"
  - "memory/std::allocator_traits::propagate_on_container_copy_assignment"
  - "memory/std::allocator_traits::difference_type"
  - "memory/std::allocator_traits::allocator_type"
  - "memory/std::allocator_traits::value_type"
  - "memory/std::allocator_traits::pointer"
  - "memory/std::allocator_traits::size_type"
  - "memory/std::allocator_traits::const_void_pointer"
  - "memory/std::allocator_traits::void_pointer"
dev_langs: 
  - "C++"
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
caps.latest.revision: 12
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# allocator_traits-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das einen *Zuweisungstyp* ergänzt.  Ein Zuweisungstyp ist jeder Typ, der ein Zuweisungsobjekt beschrieben, die zum Verwalten des zugeordneten Speicher verwendet wird.  Insbesondere für jeden Zuweisungstyp `Alloc`, können Sie `allocator_traits<Alloc>` verwenden, um alle Informationen zu bestimmen, die durch einen Zuweisung\-aktivierten Container erfordert wird.  Weitere Informationen finden Sie im Standard [allocator\-Klasse](../standard-library/allocator-class.md).  
  
## Syntax  
  
```cpp  
template<class Alloc>  
    class allocator_traits;  
```  
  
### Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`allocator_traits::allocator_type`|Dieser Typ ist ein Synonym für den Vorlagenparameter `Alloc`.|  
|`allocator_traits::const_pointer`|Dieser Typ ist `Alloc::const_pointer`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `pointer_traits<pointer>::rebind<const value_type>`.|  
|`allocator_traits::const_void_pointer`|Dieser Typ ist `Alloc::const_void_pointer`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `pointer_traits<pointer>::rebind<const void>`.|  
|`allocator_traits::difference_type`|Dieser Typ ist `Alloc::difference_type`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `pointer_traits<pointer>::difference_type`.|  
|`allocator_traits::pointer`|Dieser Typ ist `Alloc::pointer`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `value_type *`.|  
|`allocator_traits::propagate_on_container_copy_assignment`|Dieser Typ ist `Alloc::propagate_on_container_copy_assignment`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `false_type`.|  
|`allocator_traits::propagate_on_container_move_assignment`|Dieser Typ ist `Alloc::propagate_on_container_move_assignment`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `false_type`.  Wenn die Typgriffe true, ein Zuweisung\-aktivierter Container die gespeicherte Zuweisung auf einer Verschiebungszuweisung kopiert.|  
|`allocator_traits::propagate_on_container_swap`|Dieser Typ ist `Alloc::propagate_on_container_swap`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `false_type`.  Wenn die Typgriffe true, ein Zuweisung\-aktivierter Container die gespeicherte Zuweisung auf einem Austausch austauscht.|  
|`allocator_traits::size_type`|Dieser Typ ist `Alloc::size_type`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `make_unsigned<difference_type>::type`.|  
|`allocator_traits::value_type`|Dieser Typ ist ein Synonym für `Alloc::value_type`.|  
|`allocator_traits::void_pointer`|Dieser Typ ist `Alloc::void_pointer`, wenn dieser Typ wohl geformt ist; Andernfalls kann dieser Typ `pointer_traits<pointer>::rebind<void>`.|  
  
### Statische Methoden  
 Die folgenden statischen Methoden wird die entsprechende Methode für ein angegebenes Zuweisungsparameter auf.  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[allocator\_traits::allocate\-Methode](../Topic/allocator_traits::allocate%20Method.md)|Statische Methode, die belegt, indem den angegebenen Zuweisungsparameter verwendet.|  
|[allocator\_traits::construct\-Methode](../Topic/allocator_traits::construct%20Method.md)|Statische Methode, die eine angegebene Zuordnung verwendet, um ein Objekt zu erstellen.|  
|[allocator\_traits::deallocate\-Methode](../Topic/allocator_traits::deallocate%20Method.md)|Statische Methode, die eine angegebene Zuordnung verwendet, um eine bestimmte Anzahl Objekte freizugeben.|  
|[allocator\_traits::destroy\-Methode](../Topic/allocator_traits::destroy%20Method.md)|Statische Methode, die eine angegebene Zuordnung verwendet, um den Destruktor auf ein Objekt aufzurufen, ohne den Speicher freigeben.|  
|[allocator\_traits::max\_size\-Methode](../Topic/allocator_traits::max_size%20Method.md)|Statische Methode, die eine angegebene Zuordnung verwendet, um die maximale Anzahl von Objekten zu bestimmen, die zugeordnet werden können.|  
|[allocator\_traits::select\_on\_container\_copy\_construction\-Methode](../Topic/allocator_traits::select_on_container_copy_construction%20Method.md)|Statische Methode, die `select_on_container_copy_construction` in der angegebenen Zuweisung aufruft.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<memory\>](../standard-library/memory.md)   
 [pointer\_traits\-Struktur](../standard-library/pointer-traits-struct.md)   
 [scoped\_allocator\_adaptor\-Klasse](../standard-library/scoped-allocator-adaptor-class.md)