---
title: "concurrent_unordered_map-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_unordered_map/concurrency::concurrent_unordered_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_map-Klasse"
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# concurrent_unordered_map-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `concurrent_unordered_map`\- Klasse ist ein parallelitätssicherer Container, mit dem eine Folge von Elementen variierender Länge des Typs `std::pair<const _Key_type, _Element_type>` gesteuert wird.  Die Sequenz wird so dargestellt, dass parallelitätssichere Vorgänge für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe ermöglicht werden.  
  
## Syntax  
  
```  
template <  
   typename _Key_type,  
   typename _Element_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<std::pair<const _Key_type,  
   _Element_type> >  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<std::pair<const _Key_type, _Element_type> > > class concurrent_unordered_map : public details::_Concurrent_hash< details::_Concurrent_unordered_map_traits<_Key_type, _Element_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
```  
  
#### Parameter  
 `_Key_type`  
 Der Schlüsseltyp.  
  
 `_Element_type`  
 Der zugeordnete Typ.  
  
 `_Hasher`  
 Der Hashfunktionsobjekttyp.  Dieses Argument ist optional, und der Standardwert ist `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 Der Gleichheitsvergleich\-Funktionsobjekttyp.  Dieses Argument ist optional, und der Standardwert ist `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und zur Freigabe des Arbeitsspeichers für die gleichzeitige ungeordnete Zuordnung kapselt.  Dieses Argument ist optional, und der Standardwert ist `std::allocator<std::pair<``_Key_type`, `_Element_type``>>`.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`allocator_type`|Der Typ einer Zuweisung für die Speicherverwaltung.|  
|`const_iterator`|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|`const_local_iterator`|Der Typ eines konstanten Bucketiterators für die gesteuerte Sequenz.|  
|`const_pointer`|Der Typ eines konstanten Zeigers auf ein Element.|  
|`const_reference`|Der Typ eines konstanten Verweises auf ein Element.|  
|`difference_type`|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|`hasher`|Der Typ der Hashfunktion.|  
|`iterator`|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|`key_equal`|Der Typ der Vergleichsfunktion.|  
|`key_type`|Der Typ eines Sortierschlüssels.|  
|`local_iterator`|Der Typ eines Bucketiterators für die gesteuerte Sequenz.|  
|`mapped_type`|Der Typ eines zugeordneten Werts, der jedem Schlüssel zugeordnet ist.|  
|`pointer`|Der Typ eines Zeigers auf ein Element.|  
|`reference`|Der Typ eines Verweises auf ein Element.|  
|`size_type`|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|`value_type`|Der Typ eines Elements.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_map::concurrent\_unordered\_map\-Konstruktor](../Topic/concurrent_unordered_map::concurrent_unordered_map%20Constructor.md)|Überladen.  Erstellt eine parallele ungeordneten Zuordnung.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_map::at\-Methode](../Topic/concurrent_unordered_map::at%20Method.md)|Überladen.  Sucht ein Element in der `concurrent_unordered_map` mit einem angegebenen Schlüsselwert.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_unordered\_map::hash\_function\-Methode](../Topic/concurrent_unordered_map::hash_function%20Method.md)|Ruft das gespeicherte Hashfunktionsobjekt ab.|  
|[concurrent\_unordered\_map::insert\-Methode](../Topic/concurrent_unordered_map::insert%20Method.md)|Überladen.  Fügt dem `concurrent_unordered_map`\-Objekt Elemente hinzu.|  
|[concurrent\_unordered\_map::key\_eq\-Methode](../Topic/concurrent_unordered_map::key_eq%20Method.md)|Ruft das gespeicherte Gleichheits\-Vergleichsfunktionsobjekt ab.|  
|[concurrent\_unordered\_map::swap\-Methode](../Topic/concurrent_unordered_map::swap%20Method.md)|Vertauscht den Inhalt von zwei `concurrent_unordered_map`\-Objekten.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_unordered\_map::unsafe\_erase\-Methode](../Topic/concurrent_unordered_map::unsafe_erase%20Method.md)|Überladen.  Entfernt Elemente aus der `concurrent_unordered_map` an angegebenen Positionen.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_map::operatorOperator](../Topic/concurrent_unordered_map::operatorOperator.md)|Überladen.  Sucht ein Element mit dem angegebenen Schlüssel oder fügt es ein.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_unordered\_map::operator\=\-Operator](../Topic/concurrent_unordered_map::operator=%20Operator.md)|Überladen.  Weist den Inhalt eines anderen `concurrent_unordered_map`\-Objekts diesem Objekt zu.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## Hinweise  
 Ausführliche Informationen zur `concurrent_unordered_map`\-Klasse finden Sie unter [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Vererbungshierarchie  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## Anforderungen  
 **Header:** concurrent\_unordered\_map.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)