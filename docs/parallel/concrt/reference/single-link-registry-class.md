---
title: Single_link_registry-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::single_link_registry
dev_langs:
- C++
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
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
ms.openlocfilehash: 3f4719881fac882611f68b36d410c0611f99ba01
ms.lasthandoff: 02/24/2017

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
 Der Block Datentyp gespeichert werden, der `single_link_registry` Objekt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Single_link_registry-Konstruktor](#ctor)|Erstellt ein `single_link_registry`-Objekt.|  
|[~ Single_link_registry-Destruktor](#dtor)|Zerstört das `single_link_registry`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Add-Methode](#add)|Fügt einen Link zu der `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Add](network-link-registry-class.md#add).)|  
|[Begin-Methode](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Begin](network-link-registry-class.md#begin).)|  
|[Contains-Methode](#contains)|Sucht die `single_link_registry` -Objekt für einen angegebenen Block. (Überschreibt [network_link_registry:: Contains](network-link-registry-class.md#contains).)|  
|[Count-Methode](#count)|Zählt die Anzahl der Elemente in der `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Count](network-link-registry-class.md#count).)|  
|[Remove-Methode](#remove)|Entfernt ein Link aus der `single_link_registry` Objekt. (Überschreibt [network_link_registry:: Remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>Hinzufügen 

 Fügt einen Link zu der `single_link_registry` Objekt.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, der hinzugefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_link_target](invalid-link-target-class.md) -Ausnahme aus, wenn Sie bereits ein Link in dieser Registrierung vorhanden ist.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>beginnen 

 Gibt einen Iterator zurück, auf das erste Element in der `single_link_registry` Objekt.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `single_link_registry` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand wird angegeben, indem eine `NULL` Link.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>enthält 

 Sucht die `single_link_registry` -Objekt für einen angegebenen Block.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block in gesucht werden, die `single_link_registry` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link gefunden wurde, `false` andernfalls.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>Anzahl 

 Zählt die Anzahl der Elemente in der `single_link_registry` Objekt.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der `single_link_registry` Objekt.  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>Entfernen 

 Entfernt ein Link aus der `single_link_registry` Objekt.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link gefunden und entfernt wurde, `false` andernfalls.  
  
##  <a name="a-namectora-singlelinkregistry"></a><a name="ctor"></a>single_link_registry 

 Erstellt ein `single_link_registry`-Objekt.  
  
```
single_link_registry();
```  
  
##  <a name="a-namedtora-singlelinkregistry"></a><a name="dtor"></a>~ Single_link_registry 

 Zerstört das `single_link_registry`-Objekt.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn sie aufgerufen wird, bevor der Link entfernt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Multi_link_registry-Klasse](multi-link-registry-class.md)

