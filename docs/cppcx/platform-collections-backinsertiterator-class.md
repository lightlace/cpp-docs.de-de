---
title: "Platform::Collections::BackInsertIterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator-Klasse"
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::BackInsertIterator-Klasse
Stellt einen Iterator dar, der Elemente am Ende einer sequenziellen Auflistung einfügt, anstatt sie zu überschreiben.  
  
## Syntax  
  
```  
template <  
   typename T  
>  
class BackInsertIterator : public ::std::iterator< ::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### Parameter  
 `T`  
 Der Elementtyp in der aktuellen Auflistung.  
  
## Hinweise  
 Die BackInsertIterator\-Klasse implementiert die Regeln, die für die [back\_insert\_iterator\-Klasse](../standard-library/back-insert-iterator-class.md) erforderlich sind.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[BackInsertIterator::BackInsertIterator\-Konstruktor](../cppcx/backinsertiterator-backinsertiterator-constructor.md)|Initialisiert eine neue Instanz der BackInsertIterator\-Klasse.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[BackInsertIterator::operator\*\-Operator](../cppcx/backinsertiterator-operator-dereference-operator.md)|Ruft einen Verweis auf den aktuellen BackInsertIterator ab.|  
|[BackInsertIterator::operator\+\+\-Operator](../cppcx/backinsertiterator-operator-increment-operator.md)|Gibt einen Verweis auf den aktuellen BackInsertIterator zurück. Der Iterator ist unverändert.|  
|[BackInsertIterator::operator\=\-Operator](../cppcx/backinsertiterator-operator-assign-operator.md)|Fügt das angegebene Objekt am Ende der aktuellen sequenziellen Auflistung an.|  
  
## Vererbungshierarchie  
 `BackInsertIterator`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)