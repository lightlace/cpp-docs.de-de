---
title: "concurrent_unordered_multiset-Klasse"
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
  - "concurrent_unordered_set/concurrency::concurrent_unordered_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_multiset-Klasse"
ms.assetid: 219d7d67-1ff0-45f4-9400-e9cc272991a4
caps.latest.revision: 12
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_unordered_multiset-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `concurrent_unordered_multiset`\- Klasse ist ein parallelitätssicher Container, mit dem eine Folge von Elementen variierender Länge des Typs "\_Key\_type" gesteuert wird.  Die Sequenz wird so dargestellt, dass parallelitätssichere Vorgänge für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchläufe ermöglicht werden.  
  
## Syntax  
  
```  
template <  
   typename _Key_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<_Key_type>  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<_Key_type> > class concurrent_unordered_multiset : public details::_Concurrent_hash< details::_Concurrent_unordered_set_traits<_Key_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, true> >;  
```  
  
#### Parameter  
 `_Key_type`  
 Der Schlüsseltyp.  
  
 `_Hasher`  
 Der Hashfunktionsobjekttyp.  Dieses Argument ist optional, und der Standardwert ist `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 Der Gleichheitsvergleich\-Funktionsobjekttyp.  Dieses Argument ist optional, und der Standardwert ist `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, das Details zur Speicherbelegung und Aufhebung der Speicherbelegung für den gleichzeitigen Vektor kapselt.  Dieses Argument ist optional, und der Standardwert ist `std::allocator<``_Key_type``>`.  
  
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
|[concurrent\_unordered\_multiset::concurrent\_unordered\_multiset\-Konstruktor](../Topic/concurrent_unordered_multiset::concurrent_unordered_multiset%20Constructor.md)|Überladen.  Erstellt eine gleichzeitige ungeordnete Multimenge.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_multiset::hash\_function\-Methode](../Topic/concurrent_unordered_multiset::hash_function%20Method.md)|Gibt das gespeicherte Hashfunktionsobjekt zurück.|  
|[concurrent\_unordered\_multiset::insert\-Methode](../Topic/concurrent_unordered_multiset::insert%20Method.md)|Überladen.  Fügt dem `concurrent_unordered_multiset`\-Objekt Elemente hinzu.|  
|[concurrent\_unordered\_multiset::key\_eq\-Methode](../Topic/concurrent_unordered_multiset::key_eq%20Method.md)|Das gespeicherte Gleichheitsvergleichsfunktionsobjekt.|  
|[concurrent\_unordered\_multiset::swap\-Methode](../Topic/concurrent_unordered_multiset::swap%20Method.md)|Vertauscht den Inhalt von zwei `concurrent_unordered_multiset`\-Objekten.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_unordered\_multiset::unsafe\_erase\-Methode](../Topic/concurrent_unordered_multiset::unsafe_erase%20Method.md)|Überladen.  Entfernt Elemente aus der `concurrent_unordered_multiset` an angegebenen Positionen.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_unordered\_multiset::operator\=\-Operator](../Topic/concurrent_unordered_multiset::operator=%20Operator.md)|Überladen.  Weist den Inhalt eines anderen `concurrent_unordered_multiset`\-Objekts diesem Objekt zu.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## Hinweise  
 Ausführliche Informationen zur `concurrent_unordered_multiset`\-Klasse finden Sie unter [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Vererbungshierarchie  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multiset`  
  
## Anforderungen  
 **Header:** concurrent\_unordered\_set.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)