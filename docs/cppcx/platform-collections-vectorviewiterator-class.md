---
title: "Platform::Collections::VectorViewIterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator-Klasse"
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Collections::VectorViewIterator-Klasse
Stellt einen Standardvorlagenbibliotheksiterator für die Objekte bereit, die von der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] `IVectorView`\-Schnittstelle abgeleitet werden.  
  
 `ViewVectorIterator` ist ein Proxyiterator, der Elemente des Typs `VectorProxy<T>` speichert. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Syntax  
  
```  
template <  
   typename T  
>  
class VectorViewIterator;  
```  
  
#### Parameter  
 `T`  
 Der Typname der VectorViewIterator\-Vorlagenklasse.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|------------------|  
|`difference_type`|Ein Zeigerunterschied \(ptrdiff\_t\).|  
|`iterator_category`|Die Kategorie eines direkten Iterators \(::std::random\_access\_iterator\_tag\).|  
|`pointer`|Ein Zeiger auf einen internen Typ, der für die Implementierung von VectorViewIterator erforderlich ist.|  
|`reference`|Ein Verweis auf einen internen Typ, der für die Implementierung von VectorViewIterator erforderlich ist.|  
|`value_type`|Der `T`\-Typname.|  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[VectorViewIterator::VectorViewIterator\-Konstruktor](../cppcx/vectorviewiterator-vectorviewiterator-constructor.md)|Initialisiert eine neue Instanz der VectorViewIterator\-Klasse.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[VectorViewIterator::operator\-Operator](../cppcx/vectorviewiterator-operator-minus-operator.md)|Subtrahiert entweder eine angegebene Anzahl von Elementen vom aktuellen Iterator und bildet einen neuen Iterator, oder subtrahiert einen angegebenen Iterator vom aktuellen Iterator, und gibt die Anzahl von Elementen zwischen den Iteratoren zurück.|  
|[VectorViewIterator::operator\-\-\-Operator](../cppcx/vectorviewiterator-operator-decrement-operator.md)|Dekrementiert den aktuellen VectorViewIterator.|  
|[VectorViewIterator::operator\!\=\-Operator](../cppcx/vectorviewiterator-operator-inequality-operator.md)|Gibt an, ob der aktuelle VectorViewIterator ungleich einem angegebenen VectorViewIterator ist.|  
|[VectorViewIterator::operator\*\-Operator](../cppcx/vectorviewiterator-operator-dereference-operator.md)|Ruft einen Verweis auf das Element ab, das vom aktuellen VectorViewIterator angegeben wird.|  
|[VectorViewIterator::operatorOperator](../cppcx/vectorviewiterator-operatoroperator.md)|Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorViewIterator ist.|  
|[VectorViewIterator::operator\+\-Operator](../cppcx/vectorviewiterator-operator-plus-operator.md)|Gibt einen VectorViewIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorViewIterator verweist.|  
|[VectorViewIterator::operator\+\+\-Operator](../cppcx/vectorviewiterator-operator-increment-operator.md)|Inkrementiert den aktuellen VectorViewIterator.|  
|[VectorViewIterator::operator\+\=\-Operator](../cppcx/vectorviewiterator-operator-plus-assign-operator.md)|Inkrementiert den aktuellen VectorViewIterator um die angegebene Verschiebung.|  
|[VectorViewIterator::operator\<\-Operator](../cppcx/vectorviewiterator-operator-less-than-operator.md)|Gibt an, ob der aktuelle VectorViewIterator kleiner einem angegebenen VectorViewIterator ist.|  
|[VectorViewIterator::operator\<\=\-Operator](../cppcx/vectorviewiterator-operator-less-than-or-equals-operator.md)|Gibt an, ob der aktuelle VectorViewIterator kleiner oder gleich einem angegebenen VectorViewIterator ist.|  
|[VectorViewIterator::operator\-\=\-Operator](../cppcx/vectorviewiterator-operator-subtract-assign-operator.md)|Dekrementiert den aktuellen VectorViewIterator durch die angegebene Verschiebung.|  
|[VectorViewIterator::operator\=\=\-Operator](../cppcx/vectorviewiterator-operator-equality-operator.md)|Gibt an, ob der aktuelle VectorViewIterator gleich einem angegebenen VectorViewIterator ist.|  
|[VectorViewIterator::operator\>\-Operator](../cppcx/vectorviewiterator-operator-greater-than-operator.md)|Gibt an, ob der aktuelle VectorViewIterator größer einem angegebenen VectorViewIterator ist.|  
|[VectorViewIterator::operator\-\>\-Operator](../cppcx/vectorviewiterator-operator-arrow-operator.md)|Ruft die Adresse des Elements ab, auf das vom aktuellen VectorViewIterator verwiesen wird.|  
|[VectorViewIterator::operator\>\=\-Operator](../cppcx/vectorviewiterator-operator-greater-than-or-equals-operator.md)|Gibt an, ob der aktuelle VectorViewIterator größer oder gleich einem angegebenen VectorViewIterator ist.|  
  
## Vererbungshierarchie  
 `VectorViewIterator`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)