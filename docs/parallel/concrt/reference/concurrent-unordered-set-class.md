---
title: "concurrent_unordered_set-Klasse"
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
  - "concurrent_unordered_set/concurrency::concurrent_unordered_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_set-Klasse"
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
caps.latest.revision: 12
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_unordered_set-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `concurrent_unordered_set`\- Klasse ist ein parallelitätssicher Container, mit dem eine Folge von Elementen variierender Länge des Typs "\_Key\_type" gesteuert wird.  Die Sequenz wird so dargestellt, dass parallelitätssichere Vorgänge für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe ermöglicht werden.  
  
## Syntax  
  
```  
template <  
   typename _Key_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<_Key_type>  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<_Key_type> > class concurrent_unordered_set : public details::_Concurrent_hash< details::_Concurrent_unordered_set_traits<_Key_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
```  
  
#### Parameter  
 `_Key_type`  
 Der Schlüsseltyp.  
  
 `_Hasher`  
 Der Hashfunktionsobjekttyp.  Dieses Argument ist optional, und der Standardwert ist `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 Der Gleichheitsvergleich\-Funktionsobjekttyp.  Dieses Argument ist optional, und der Standardwert ist `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und zur Freigabe des Arbeitsspeichers für den gleichzeitigen ungeordneten Satz kapselt.  Dieses Argument ist optional, und der Standardwert ist `std::allocator<``_Key_type``>`.  
  
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
|`pointer`|Der Typ eines Zeigers auf ein Element.|  
|`reference`|Der Typ eines Verweises auf ein Element.|  
|`size_type`|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|`value_type`|Der Typ eines Elements.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_set::concurrent\_unordered\_set\-Konstruktor](../Topic/concurrent_unordered_set::concurrent_unordered_set%20Constructor.md)|Überladen.  Erstellt einen parallelen ungeordneten Satz.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_set::hash\_function\-Methode](../Topic/concurrent_unordered_set::hash_function%20Method.md)|Gibt das gespeicherte Hashfunktionsobjekt zurück.|  
|[concurrent\_unordered\_set::insert\-Methode](../Topic/concurrent_unordered_set::insert%20Method.md)|Überladen.  Fügt dem `concurrent_unordered_set`\-Objekt Elemente hinzu.|  
|[concurrent\_unordered\_set::key\_eq\-Methode](../Topic/concurrent_unordered_set::key_eq%20Method.md)|Gibt das gespeicherte Gleichheitsvergleich\-Funktionsobjekt zurück.|  
|[concurrent\_unordered\_set::swap\-Methode](../Topic/concurrent_unordered_set::swap%20Method.md)|Vertauscht den Inhalt von zwei `concurrent_unordered_set`\-Objekten.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_unordered\_set::unsafe\_erase\-Methode](../Topic/concurrent_unordered_set::unsafe_erase%20Method.md)|Überladen.  Entfernt Elemente aus der `concurrent_unordered_set` an angegebenen Positionen.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_set::operator\=\-Operator](../Topic/concurrent_unordered_set::operator=%20Operator.md)|Überladen.  Weist den Inhalt eines anderen `concurrent_unordered_set`\-Objekts diesem Objekt zu.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## Hinweise  
 Ausführliche Informationen zur `concurrent_unordered_set`\-Klasse finden Sie unter [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Vererbungshierarchie  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_set`  
  
## Anforderungen  
 **Header:** concurrent\_unordered\_set.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)