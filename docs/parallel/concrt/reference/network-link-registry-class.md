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
- agents/concurrency::network_link_registry
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 8b39ab676db0072d279ee4058693769ef6f7eb3f
ms.lasthandoff: 02/24/2017

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
|[Add-Methode](#add)|Ruft beim Überschreiben in einer abgeleiteten Klasse fügt einen Link zu der `network_link_registry` Objekt.|  
|[Begin-Methode](#begin)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt einen Iterator auf das erste Element in der `network_link_registry` Objekt.|  
|[Contains-Methode](#contains)|Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` -Objekt für einen angegebenen Block.|  
|[Count-Methode](#count)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Anzahl der Elemente in der `network_link_registry` Objekt.|  
|[Remove-Methode](#remove)|Ruft beim Überschreiben in einer abgeleiteten Klasse entfernt einen angegebenen Block aus der `network_link_registry` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `network link registry` ist für gleichzeitigen Zugriff nicht sicher.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `network_link_registry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>Hinzufügen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse fügt einen Link zu der `network_link_registry` Objekt.  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, der hinzugefügt werden soll.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>beginnen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt einen Iterator auf das erste Element in der `network_link_registry` Objekt.  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `network_link_registry` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand des Iterators sind durch ein `NULL` Link.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>enthält 

 Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` -Objekt für einen angegebenen Block.  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, der in gesucht wird die `network_link_registry` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Block gefunden wurde, `false` andernfalls.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>Anzahl 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Anzahl der Elemente in der `network_link_registry` Objekt.  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der `network_link_registry` Objekt.  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>Entfernen 

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
 [Multi_link_registry-Klasse](multi-link-registry-class.md)

