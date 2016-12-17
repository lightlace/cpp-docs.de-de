---
title: "concurrent_vector-Klasse"
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
  - "concurrent_vector/Concurrency::concurrent_vector"
  - "concurrent_vector/concurrency::concurrent_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_vector-Klasse"
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
caps.latest.revision: 21
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_vector-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `concurrent_vector`\-Klasse ist eine Sequenzcontainerklasse, die zufälligen Zugriff auf jedes Element zulässt.  Sie aktiviert parallelitätssichere Operationen für Anfügen, Elementzugriff, Iteratorzugriff und Iteratordurchlauf.  
  
## Syntax  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_vector: protected details::_Allocator_base<_Ty, _Ax>, private details::_Concurrent_vector_base_v4;  
```  
  
#### Parameter  
 `_Ty`  
 Der Datentyp der Elemente, die im Vektor gespeichert werden sollen.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, das Details zur Speicherbelegung und Aufhebung der Speicherbelegung für den gleichzeitigen Vektor kapselt.  Dieses Argument ist optional, und der Standardwert ist `allocator<``_Ty``>`.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`allocator_type`|Ein Typ, der die Belegungsfunktionsklasse für den gleichzeitigen Vektor darstellt.|  
|`const_iterator`|Ein Typ, der einen Iterator mit beliebigem Zugriff bereitstellt, der ein `const`\-Element in einem gleichzeitigen Vektor lesen kann.|  
|`const_pointer`|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem gleichzeitigen Vektor bereitstellt.|  
|`const_reference`|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem gleichzeitigen Vektor gespeichert ist und `const`\-Operationen durchführt.|  
|`const_reverse_iterator`|Ein Typ, der einen Iterator mit beliebigem Zugriff bereitstellt, der ein beliebiges `const`\-Element im gleichzeitigen Vektor lesen kann.|  
|`difference_type`|Ein Typ, der die vorzeichenbehaftete Entfernung zwischen zwei Elementen in einem gleichzeitigen Vektor bereitstellt.|  
|`iterator`|Ein Typ, der einen Iterator mit beliebigem Zugriff bereitstellt, der ein beliebiges Element in einem gleichzeitigen Vektor lesen kann.  Änderungen eines Elements, die den Iterator verwenden, sind nicht parallelitätssicher.|  
|`pointer`|Ein Typ, der einen Zeiger auf ein Element in einem gleichzeitigen Vektor bereitstellt.|  
|`reference`|Ein Typ, der einen Verweis auf ein Element in einem gleichzeitigen Vektor bereitstellt.|  
|`reverse_iterator`|Ein Typ, der einen Iterator mit beliebigem Zugriff bereitstellt, der ein beliebiges Element in einem reservierten gleichzeitigen Vektor lesen kann.  Änderungen eines Elements, die den Iterator verwenden, sind nicht parallelitätssicher.|  
|`size_type`|Ein Typ, der die Anzahl von Elementen in einem gleichzeitigen Vektor angibt.|  
|`value_type`|Ein Typ, der den in einem gleichzeitigen Vektor gespeicherten Datentyp darstellt.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_vector::concurrent\_vector\-Konstruktor](../Topic/concurrent_vector::concurrent_vector%20Constructor.md)|Überladen.  Erstellt einen gleichzeitigen Vektor.|  
|[concurrent\_vector::~concurrent\_vector\-Destruktor](../Topic/concurrent_vector::~concurrent_vector%20Destructor.md)|Löscht alle Elemente und zerstört diesen gleichzeitigen Vektor.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_vector::assign\-Methode](../Topic/concurrent_vector::assign%20Method.md)|Überladen.  Löscht die Elemente des gleichzeitigen Vektors und weist ihm entweder `_N`\-Kopien von `_Item` oder angegebene Werte aus dem Iteratorbereich zu \[`_Begin`, `_End`\).  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_vector::at\-Methode](../Topic/concurrent_vector::at%20Method.md)|Überladen.  Bietet Zugriff auf das Element am angegebenen Index im gleichzeitigen Vektor.  Diese Methode ist für Lesevorgänge parallelitätssicher, und auch während der Vektorvergrößerung, solange Sie sichergestellt haben, dass der Wert `_Index` kleiner als der parallele Vektor ist.|  
|[concurrent\_vector::back\-Methode](../Topic/concurrent_vector::back%20Method.md)|Überladen.  Gibt einen Verweis oder einen `const`\-Verweis auf das letzte Element im gleichzeitigen Vektor zurück.  Wenn der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::begin\-Methode](../Topic/concurrent_vector::begin%20Method.md)|Überladen.  Gibt einen Iterator vom Typ `iterator` oder `const_iterator` zum Anfang des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::capacity\-Methode](../Topic/concurrent_vector::capacity%20Method.md)|Gibt die maximale Größe zurück, auf die der gleichzeitige Vektor anwachsen kann, ohne zusätzlichen Speicher zu belegen.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::cbegin\-Methode](../Topic/concurrent_vector::cbegin%20Method.md)|Gibt einen Iterator vom Typ `const_iterator` zum Anfang des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::cend\-Methode](../Topic/concurrent_vector::cend%20Method.md)|Gibt einen Iterator vom Typ `const_iterator` zum Ende des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::clear\-Methode](../Topic/concurrent_vector::clear%20Method.md)|Löscht alle Elemente im gleichzeitigen Vektor.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_vector::crbegin\-Methode](../Topic/concurrent_vector::crbegin%20Method.md)|Gibt einen Iterator vom Typ `const_reverse_iterator` zum Anfang des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::crend\-Methode](../Topic/concurrent_vector::crend%20Method.md)|Gibt einen Iterator vom Typ `const_reverse_iterator` zum Ende des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::empty\-Methode](../Topic/concurrent_vector::empty%20Method.md)|Testet, ob der gleichzeitige Vektor beim Aufruf dieser Methode leer ist.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::end\-Methode](../Topic/concurrent_vector::end%20Method.md)|Überladen.  Gibt einen Iterator vom Typ `iterator` oder `const_iterator` zum Ende des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::front\-Methode](../Topic/concurrent_vector::front%20Method.md)|Überladen.  Gibt einen Verweis oder einen `const`\-Verweis auf das erste Element im gleichzeitigen Vektor zurück.  Wenn der gleichzeitige Vektor leer ist, ist der Rückgabewert nicht definiert.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::get\_allocator\-Methode](../Topic/concurrent_vector::get_allocator%20Method.md)|Gibt eine Kopie der Belegungsfunktion zurück, die verwendet wurde, um den gleichzeitigen Vektor zu erstellen.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::grow\_by\-Methode](../Topic/concurrent_vector::grow_by%20Method.md)|Überladen.  Vergrößert diesen gleichzeitigen Vektor um `_Delta` Elemente.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::grow\_to\_at\_least\-Methode](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|Vergrößert diesen gleichzeitigen Vektor, bis es mindestens über `_N` Elemente verfügt.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::max\_size\-Methode](../Topic/concurrent_vector::max_size%20Method.md)|Gibt die maximale Anzahl von Elementen zurück, die der gleichzeitige Vektor aufnehmen kann.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::push\_back\-Methode](../Topic/concurrent_vector::push_back%20Method.md)|Überladen.  Fügt das angegebene Element an das Ende des gleichzeitigen Vektors an.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::rbegin\-Methode](../Topic/concurrent_vector::rbegin%20Method.md)|Überladen.  Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` zum Anfang des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::rend\-Methode](../Topic/concurrent_vector::rend%20Method.md)|Überladen.  Gibt einen Iterator vom Typ `reverse_iterator` oder `const_reverse_iterator` zum Ende des gleichzeitigen Vektors zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::reserve\-Methode](../Topic/concurrent_vector::reserve%20Method.md)|Reserviert ausreichend Speicherplatz, um den gleichzeitigen Vektor auf die Größe `_N` anwachsen zu lassen, ohne später mehr Speicher reservieren zu müssen.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_vector::resize\-Methode](../Topic/concurrent_vector::resize%20Method.md)|Überladen.  Ändert die Größe des gleichzeitigen Vektors in die angeforderte Größe und löscht oder fügt dabei nach Bedarf Elemente hinzu.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_vector::shrink\_to\_fit\-Methode](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|Komprimiert die interne Darstellung des gleichzeitigen Vektors, um Fragmentierung zu reduzieren und die Speicherauslastung zu optimieren.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_vector::size\-Methode](../Topic/concurrent_vector::size%20Method.md)|Gibt die Anzahl von Elementen im gleichzeitigen Vektor zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_vector::swap\-Methode](../Topic/concurrent_vector::swap%20Method.md)|Vertauscht den Inhalt zweier gleichzeitiger Vektoren.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_vector::operatorOperator](../Topic/concurrent_vector::operatorOperator.md)|Überladen.  Bietet Zugriff auf das Element am angegebenen Index im gleichzeitigen Vektor.  Diese Methode ist für Lesevorgänge parallelitätssicher, und auch während der Vektorvergrößerung, solange Sie sichergestellt haben, dass der Wert `_Index` kleiner als der parallele Vektor ist.|  
|[concurrent\_vector::operator\=\-Operator](../Topic/concurrent_vector::operator=%20Operator.md)|Überladen.  Weist den Inhalt eines anderen `concurrent_vector`\-Objekts diesem Objekt zu.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## Hinweise  
 Ausführliche Informationen zur `concurrent_vector`\-Klasse finden Sie unter [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Vererbungshierarchie  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## Anforderungen  
 **Header:** concurrent\_vector.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)