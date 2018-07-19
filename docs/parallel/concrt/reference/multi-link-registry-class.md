---
title: Multi_link_registry-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
dev_langs:
- C++
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fbe52298f267fabb2ba326e3e1c7b66f4ad49ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688933"
---
# <a name="multilinkregistry-class"></a>multi_link_registry-Klasse
Das `multi_link_registry`-Objekt ist eine `network_link_registry`, die mehrere Quellblöcke oder mehrere Zielblöcke verwaltet.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Parameter  
 `_Block`  
 Geben Sie die Blockdaten gespeichert werden, der `multi_link_registry` Objekt.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[multi_link_registry](#ctor)|Erstellt ein `multi_link_registry`-Objekt.|  
|[~ Multi_link_registry-Destruktor](#dtor)|Zerstört das `multi_link_registry`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[add](#add)|Fügt einen Link zu der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Add](network-link-registry-class.md#add).)|  
|[begin](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Begin](network-link-registry-class.md#begin).)|  
|[Enthält](#contains)|Sucht die `multi_link_registry` Objekt für einen angegebenen Block. (Überschreibt [network_link_registry:: Contains](network-link-registry-class.md#contains).)|  
|[count](#count)|Zählt die Anzahl der Elemente in der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Entfernt eine Verknüpfung aus dem `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Remove](network-link-registry-class.md#remove).)|  
|[set_bound](#set_bound)|Legt eine Obergrenze für die Anzahl der Links, die die `multi_link_registry` Objekt aufnehmen kann.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="add"></a> Hinzufügen 

 Fügt einen Link zu der `multi_link_registry` Objekt.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Löst die Methode eine [Invalid_link_target](invalid-link-target-class.md) Ausnahme, wenn der Link bereits in der Registrierung vorhanden ist oder wenn eine Grenze wurde bereits festgelegt mit der `set_bound` -Funktion und einen Link Zwischenzeit entfernt wurde.  
  
##  <a name="begin"></a> Beginnen 

 Gibt einen Iterator zurück, auf das erste Element in der `multi_link_registry` Objekt.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `multi_link_registry` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand erkennbar ist eine `NULL` Link.  
  
##  <a name="contains"></a> Enthält 

 Sucht die `multi_link_registry` Objekt für einen angegebenen Block.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf ein Block, der für gesucht werden soll, in der `multi_link_registry` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der angegebene Block gefunden wurde, `false` andernfalls.  
  
##  <a name="count"></a> Anzahl 

 Zählt die Anzahl der Elemente in der `multi_link_registry` Objekt.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der `multi_link_registry` Objekt.  
  
##  <a name="ctor"></a> multi_link_registry 

 Erstellt ein `multi_link_registry`-Objekt.  
  
```
multi_link_registry();
```  
  
##  <a name="dtor"></a> ~ Multi_link_registry 

 Zerstört das `multi_link_registry`-Objekt.  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn Sie aufgerufen wird, bevor alle Links entfernt werden.  
  
##  <a name="remove"></a> Entfernen 

 Entfernt eine Verknüpfung aus dem `multi_link_registry` Objekt.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der Link wurde gefunden und entfernt, `false` andernfalls.  
  
##  <a name="set_bound"></a> set_bound 

 Legt eine Obergrenze für die Anzahl der Links, die die `multi_link_registry` Objekt aufnehmen kann.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Parameter  
 `_MaxLinks`  
 Die maximale Anzahl von links, die die `multi_link_registry` Objekt aufnehmen kann.  
  
### <a name="remarks"></a>Hinweise  
 Nach eine Grenze festgelegt ist, Aufheben der Verknüpfung eines Eintrags führt dazu, dass die `multi_link_registry` Objekt einen unveränderlichen Zustand eingeben, in denen nachfolgende Aufrufe von `add` löst eine `invalid_link_target` Ausnahme.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [single_link_registry-Klasse](single-link-registry-class.md)
