---
title: Network_link_registry-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
dev_langs: C++
helpviewer_keywords: network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 116c36b5c0b990672a455e1419c92d60ec992845
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="networklinkregistry-class"></a>network_link_registry-Klasse
Die abstrakte `network_link_registry`-Basisklasse verwaltet die Verknüpfung zwischen Quell- und Zielblöcken.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class _Block>
class network_link_registry;
```  
  
#### <a name="parameters"></a>Parameter  
 `_Block`  
 Geben Sie die Blockdaten gespeichert werden, der `network_link_registry`.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`const_pointer`|Ein Typ, der ein Zeiger auf eine `const` Element in einem `network_link_registry` Objekt.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` Element gespeichert wird, einem `network_link_registry` Objekt zum Lesen und Ausführen von const-Operationen.|  
|`iterator`|Ein Typ, der einem Iterator bereitstellt, kann lesen oder ändern Sie ein Element in einem `network_link_registry` Objekt.|  
|`type`|Ein Typ, der den Blocktyp, die in gespeicherten stellt die `network_link_registry` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[add](#add)|Ruft beim Überschreiben in einer abgeleiteten Klasse fügt einen Link zu der `network_link_registry` Objekt.|  
|[begin](#begin)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt einen Iterator auf das erste Element in der `network_link_registry` Objekt.|  
|[enthält](#contains)|Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` Objekt für einen angegebenen Block.|  
|[count](#count)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Anzahl der Elemente in der `network_link_registry` Objekt.|  
|[remove](#remove)|Ruft beim Überschreiben in einer abgeleiteten Klasse entfernt einen angegebenen Block aus der `network_link_registry` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `network link registry` ist nicht für den gleichzeitigen Zugriff sicher.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `network_link_registry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="add"></a>Hinzufügen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse fügt einen Link zu der `network_link_registry` Objekt.  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block hinzugefügt werden.  
  
##  <a name="begin"></a>beginnen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt einen Iterator auf das erste Element in der `network_link_registry` Objekt.  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `network_link_registry` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand des Iterators erkennbar ist eine `NULL` Link.  
  
##  <a name="contains"></a>enthält 

 Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` Objekt für einen angegebenen Block.  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Speicherblock, der für in durchsucht wird die `network_link_registry` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Block gefunden wurde, `false` andernfalls.  
  
##  <a name="count"></a>Anzahl 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Anzahl der Elemente in der `network_link_registry` Objekt.  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der `network_link_registry` Objekt.  
  
##  <a name="remove"></a>Entfernen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse entfernt einen angegebenen Block aus der `network_link_registry` Objekt.  
  
```
virtual bool remove(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link wurde gefunden und entfernt, `false` andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Single_link_registry-Klasse](single-link-registry-class.md)   
 [multi_link_registry-Klasse](multi-link-registry-class.md)
