---
title: "pointer_traits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::pointer_traits::element_type"
  - "memory/std::pointer_traits::pointer"
  - "memory/std::pointer_traits"
  - "memory/std::pointer_traits::difference_type"
  - "memory/std::pointer_traits::rebind"
  - "xmemory0/std::pointer_traits::element_type"
  - "xmemory0/std::pointer_traits::pointer"
  - "xmemory0/std::pointer_traits"
  - "xmemory0/std::pointer_traits::difference_type"
  - "xmemory0/std::pointer_traits::rebind"
dev_langs: 
  - "C++"
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# pointer_traits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt Informationen bereit, die für ein Objekt der Vorlagenklasse `allocator_traits` erforderlich sind, um eine Zuweisung mit Zeigertyp `Ptr` zu beschreiben.  
  
## Syntax  
  
```cpp  
template<class Ptr>  
    struct pointer_traits;  
```  
  
## Hinweise  
 PTR kann ein unformatierter Zeiger des Typs `Ty *` oder der Klasse mit den folgenden Eigenschaften sein.  
  
```  
template<class Ty, class... Rest>  
    struct Ptr  
    { // describes a pointer type usable by allocators  
    typedef Ptr pointer;  
    typedef T1 element_type; // optional  
    typedef T2 difference_type; // optional  
    template<class Other>  
        using rebind = typename Ptr<Other, Rest...>; // optional  
  
    static pointer pointer_to(element_type& obj); // optional  
    };  
```  
  
> [!WARNING]
>  Während der C\+\+\-Standard dem `rebind` als Member Aliasvorlage angibt, binden Visual C\+\+\-Werkzeuge als `struct` erneut.  
  
### Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`typedef T2 difference_type`|Der Typ `T2` ist `Ptr::difference_type`, wenn dieser Typ vorhanden ist; andernfalls `ptrdiff_t`.  Wenn `Ptr` unformatierter ein Zeiger ist, ist der Typ `ptrdiff_t`.|  
|`typedef T1 element_type`|Der Typ `T1` ist `Ptr::element_type`, wenn dieser Typ vorhanden ist; andernfalls `Ty`.  Wenn `Ptr` unformatierter ein Zeiger ist, ist der Typ `Ty`.|  
|`typedef Ptr pointer`|Der Typ ist `Ptr`.|  
  
### Strukturen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`pointer_traits::rebind`|Versucht, den zugrunde liegenden Zeigertyp zu einem angegebenen Typ zu konvertieren.|  
  
### Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[pointer\_traits::pointer\_to\-Methode](../Topic/pointer_traits::pointer_to%20Method.md)|Konvertiert einen bestimmten Verweis auf ein Objekt der Klasse `Ptr`.|  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<memory\>](../standard-library/memory.md)   
 [allocator\_traits\-Klasse](../standard-library/allocator-traits-class.md)