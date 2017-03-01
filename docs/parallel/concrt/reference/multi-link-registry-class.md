---
title: Multi_link_registry-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::multi_link_registry
dev_langs:
- C++
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
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
ms.openlocfilehash: 1548d2f920cf5566cced499e189cdcc19bf757ee
ms.lasthandoff: 02/24/2017

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
 Der Block Datentyp gespeichert werden, der `multi_link_registry` Objekt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Multi_link_registry-Konstruktor](#ctor)|Erstellt ein `multi_link_registry`-Objekt.|  
|[~ Multi_link_registry-Destruktor](#dtor)|Zerstört das `multi_link_registry`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Add-Methode](#add)|Fügt einen Link zu der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Add](network-link-registry-class.md#add).)|  
|[Begin-Methode](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Begin](network-link-registry-class.md#begin).)|  
|[Contains-Methode](#contains)|Sucht die `multi_link_registry` -Objekt für einen angegebenen Block. (Überschreibt [network_link_registry:: Contains](network-link-registry-class.md#contains).)|  
|[Count-Methode](#count)|Zählt die Anzahl der Elemente in der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Count](network-link-registry-class.md#count).)|  
|[Remove-Methode](#remove)|Entfernt ein Link aus der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Remove](network-link-registry-class.md#remove).)|  
|[Set_bound-Methode](#set_bound)|Legt eine Obergrenze für die Anzahl der Links, die die `multi_link_registry` -Objekt enthalten kann.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>Hinzufügen 

 Fügt einen Link zu der `multi_link_registry` Objekt.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, der hinzugefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_link_target](invalid-link-target-class.md) Ausnahme, wenn der Link bereits in der Registrierung vorhanden ist oder eine gebundene bereits festgelegt wurde die `set_bound` -Funktion und ein Link inzwischen entfernt wurde.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>beginnen 

 Gibt einen Iterator zurück, auf das erste Element in der `multi_link_registry` Objekt.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `multi_link_registry` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand wird angegeben, indem eine `NULL` Link.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>enthält 

 Sucht die `multi_link_registry` -Objekt für einen angegebenen Block.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block in gesucht werden, die `multi_link_registry` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der angegebene Block gefunden wurde, `false` andernfalls.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>Anzahl 

 Zählt die Anzahl der Elemente in der `multi_link_registry` Objekt.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der `multi_link_registry` Objekt.  
  
##  <a name="a-namectora-multilinkregistry"></a><a name="ctor"></a>multi_link_registry 

 Erstellt ein `multi_link_registry`-Objekt.  
  
```
multi_link_registry();
```  
  
##  <a name="a-namedtora-multilinkregistry"></a><a name="dtor"></a>~ Multi_link_registry 

 Zerstört das `multi_link_registry`-Objekt.  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn Sie aufgerufen wird, bevor alle Links entfernt werden.  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>Entfernen 

 Entfernt ein Link aus der `multi_link_registry` Objekt.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link gefunden und entfernt wurde, `false` andernfalls.  
  
##  <a name="a-namesetbounda-setbound"></a><a name="set_bound"></a>set_bound 

 Legt eine Obergrenze für die Anzahl der Links, die die `multi_link_registry` -Objekt enthalten kann.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Parameter  
 `_MaxLinks`  
 Die maximale Anzahl an links, die `multi_link_registry` -Objekt enthalten kann.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem eine Grenze festgelegt wird, führt ein Einstieg führt dazu, dass die `multi_link_registry` -Objekt, das einen unveränderlichen Zustand wechselt, in dem nachfolgende Aufrufe von `add` löst eine `invalid_link_target` Ausnahme.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Single_link_registry-Klasse](single-link-registry-class.md)

