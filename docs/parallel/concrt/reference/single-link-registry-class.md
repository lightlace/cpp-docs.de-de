---
title: Single_link_registry-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
dev_langs: C++
helpviewer_keywords: single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 18e0ebe846a8ee0bf583ad342e43959e4996cd87
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="singlelinkregistry-class"></a>single_link_registry-Klasse
Das `single_link_registry`-Objekt ist eine `network_link_registry`, die nur eine einzige Quelle oder einen einzigen Zielblock verwaltet.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Parameter  
 `_Block`  
 Geben Sie die Blockdaten gespeichert werden, der `single_link_registry` Objekt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[single_link_registry](#ctor)|Erstellt ein `single_link_registry`-Objekt.|  
|[~ Single_link_registry-Destruktor](#dtor)|Zerstört das `single_link_registry`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[add](#add)|Fügt einen Link zu der `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Add](network-link-registry-class.md#add).)|  
|[begin](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Begin](network-link-registry-class.md#begin).)|  
|[enthält](#contains)|Sucht die `single_link_registry` Objekt für einen angegebenen Block. (Überschreibt [network_link_registry:: Contains](network-link-registry-class.md#contains).)|  
|[count](#count)|Zählt die Anzahl der Elemente in der `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Entfernt eine Verknüpfung aus dem `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="add"></a>Hinzufügen 

 Fügt einen Link zu der `single_link_registry` Objekt.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_link_target](invalid-link-target-class.md) -Ausnahme aus, wenn bereits eine Verknüpfung in der Registrierung vorhanden ist.  
  
##  <a name="begin"></a>beginnen 

 Gibt einen Iterator zurück, auf das erste Element in der `single_link_registry` Objekt.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `single_link_registry` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand erkennbar ist eine `NULL` Link.  
  
##  <a name="contains"></a>enthält 

 Sucht die `single_link_registry` Objekt für einen angegebenen Block.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf ein Block, der für gesucht werden soll, in der `single_link_registry` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link gefunden wurde, `false` andernfalls.  
  
##  <a name="count"></a>Anzahl 

 Zählt die Anzahl der Elemente in der `single_link_registry` Objekt.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der `single_link_registry` Objekt.  
  
##  <a name="remove"></a>Entfernen 

 Entfernt eine Verknüpfung aus dem `single_link_registry` Objekt.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link wurde gefunden und entfernt, `false` andernfalls.  
  
##  <a name="ctor"></a>single_link_registry 

 Erstellt ein `single_link_registry`-Objekt.  
  
```
single_link_registry();
```  
  
##  <a name="dtor"></a>~ Single_link_registry 

 Zerstört das `single_link_registry`-Objekt.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn sie aufgerufen wird, bevor der Link entfernt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [multi_link_registry-Klasse](multi-link-registry-class.md)
