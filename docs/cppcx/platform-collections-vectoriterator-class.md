---
title: "Platform::Collections::VectorIterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator-Klasse"
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Collections::VectorIterator-Klasse
Stellt einen Standardvorlagenbibliotheksiterator für die Objekte bereit, die von der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-IVector\-Schnittstelle abgeleitet werden.  
  
 VectorIterator ist ein Proxyiterator, der Elemente des Typs VectorProxy\<T\> speichert. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Syntax  
  
```  
template <  
   typename T  
>  
class VectorIterator;  
```  
  
#### Parameter  
 `T`  
 Der Typname der VectorIterator\-Vorlagenklasse.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|------------------|  
|`difference_type`|Ein Zeigerunterschied \(ptrdiff\_t\).|  
|`iterator_category`|Die Kategorie eines direkten Iterators \(::std::random\_access\_iterator\_tag\).|  
|`pointer`|Ein Zeiger auf einen internen Typ, Platform::Collections::Details::VectorProxy\<T\>, der für die Implementierung von VectorIterator erforderlich ist.|  
|`reference`|Ein Verweis auf einen internen Typ, Platform::Collections::Details::VectorProxy\<T\>, der für die Implementierung von VectorIterator erforderlich ist.|  
|`value_type`|Der `T`\-Typname.|  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[VectorIterator::VectorIterator\-Konstruktor](../cppcx/vectoriterator-vectoriterator-constructor.md)|Initialisiert eine neue Instanz der VectorIterator\-Klasse.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[VectorIterator::operator\-\-Operator](../cppcx/vectoriterator-operator-minus-operator.md)|Subtrahiert entweder eine angegebene Anzahl von Elementen vom aktuellen Iterator und bildet einen neuen Iterator, oder subtrahiert einen angegebenen Iterator vom aktuellen Iterator, und gibt die Anzahl von Elementen zwischen den Iteratoren zurück.|  
|[VectorIterator::operator\-\-\-Operator](../cppcx/vectoriterator-operator-decrement-operator.md)|Dekrementiert den aktuellen VectorIterator.|  
|[VectorIterator::operator\!\=\-Operator](../cppcx/vectoriterator-operator-inequality-operator.md)|Gibt an, ob der aktuelle VectorIterator ungleich einem angegebenen VectorIterator ist.|  
|[VectorIterator::operator\*\-Operator](../cppcx/vectoriterator-operator-dereference-operator.md)|Ruft einen Verweis auf das Element ab, das vom aktuellen VectorIterator angegeben wird.|  
|[VectorIterator::operatorOperator](../cppcx/vectoriterator-operatoroperator.md)|Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorIterator ist.|  
|[\(DELETE\) VectorIterator::operator\+\-Operator](http://msdn.microsoft.com/de-de/b0b1af2c-e2a8-4876-99dc-7351bfc46ce4)|Gibt einen VectorIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorIterator verweist.|  
|[VectorIterator::operator\+\+\-Operator](../cppcx/vectoriterator-operator-increment-operator.md)|Inkrementiert den aktuellen VectorIterator.|  
|[VectorIterator::operator\+\=\-Operator](../cppcx/vectoriterator-operator-plus-assign-operator.md)|Inkrementiert den aktuellen VectorIterator um die angegebene Verschiebung.|  
|[VectorIterator::operator\<\-Operator](../cppcx/vectoriterator-operator-less-than-operator.md)|Gibt an, ob der aktuelle VectorIterator kleiner einem angegebenen VectorIterator ist.|  
|[VectorIterator::operator\<\=\-Operator](../cppcx/vectoriterator-operator-less-than-or-equals-operator.md)|Gibt an, ob der aktuelle VectorIterator kleiner oder gleich einem angegebenen VectorIterator ist.|  
|[VectorIterator::operator\-\=\-Operator](../cppcx/vectoriterator-operator-subtract-assign-operator.md)|Dekrementiert den aktuellen VectorIterator um die angegebene Verschiebung.|  
|[VectorIterator::operator\=\=\-Operator](../cppcx/vectoriterator-operator-equality-operator.md)|Gibt an, ob der aktuelle VectorIterator gleich einem angegebenen VectorIterator ist.|  
|[VectorIterator::operator\>\-Operator](../cppcx/vectoriterator-operator-greater-than-operator.md)|Gibt an, ob der aktuelle VectorIterator größer als ein angegebener VectorIterator ist.|  
|[VectorIterator::operator\-\>\-Operator](../cppcx/vectoriterator-operator-arrow-operator.md)|Ruft die Adresse des Elements ab, auf das vom aktuellen VectorIterator verwiesen wird.|  
|[VectorIterator::operator\>\=\-Operator](../cppcx/vectoriterator-operator-greater-than-or-equal-operator.md)|Gibt an, ob der aktuelle VectorIterator größer oder gleich einem angegebenen VectorIterator ist.|  
  
## Vererbungshierarchie  
 `VectorIterator`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)