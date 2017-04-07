---
title: Network_link_registry-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 28c13f1e2bf80624da3a7aba441944c051790d27
ms.lasthandoff: 03/17/2017

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
 Der Block Datentyp gespeichert werden, der `network_link_registry`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`const_pointer`|Ein Typ, der ein Zeiger auf eine `const` Element in einem `network_link_registry` Objekt.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` Element gespeichert, ein `network_link_registry` -Objekt zum Lesen und const-Operationen durchführt.|  
|`iterator`|Eine Typ, der einem Iterator bereitstellt, kann lesen oder ändern Sie ein Element in einem `network_link_registry` Objekt.|  
|`type`|Ein Typ, der gespeicherten Blocktyp darstellt, der `network_link_registry` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[add](#add)|Ruft beim Überschreiben in einer abgeleiteten Klasse fügt einen Link zu der `network_link_registry` Objekt.|  
|[begin](#begin)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt einen Iterator auf das erste Element in der `network_link_registry` Objekt.|  
|[enthält](#contains)|Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` -Objekt für einen angegebenen Block.|  
|[count](#count)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Anzahl der Elemente in der `network_link_registry` Objekt.|  
|[remove](#remove)|Ruft beim Überschreiben in einer abgeleiteten Klasse entfernt einen angegebenen Block aus der `network_link_registry` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `network link registry` ist für gleichzeitigen Zugriff nicht sicher.  
  
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
 Ein Zeiger auf einen Block, der hinzugefügt werden soll.  
  
##  <a name="begin"></a>beginnen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt einen Iterator auf das erste Element in der `network_link_registry` Objekt.  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `network_link_registry` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand des Iterators sind durch ein `NULL` Link.  
  
##  <a name="contains"></a>enthält 

 Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` -Objekt für einen angegebenen Block.  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, der in gesucht wird die `network_link_registry` Objekt.  
  
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
 `true`Wenn der Link gefunden und entfernt wurde, `false` andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Single_link_registry-Klasse](single-link-registry-class.md)   
 [multi_link_registry-Klasse](multi-link-registry-class.md)

