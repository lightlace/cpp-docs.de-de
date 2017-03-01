---
title: Source_link_manager-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::source_link_manager
dev_langs:
- C++
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
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
ms.openlocfilehash: b9323da4d2ccefe09ba38df088e546828d41f2ee
ms.lasthandoff: 02/24/2017

---
# <a name="sourcelinkmanager-class"></a>source_link_manager-Klasse
Das `source_link_manager`-Objekt verwaltet Meldungsblock-Netzwerklinks zu `ISource`-Blöcken.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class _LinkRegistry>
class source_link_manager;
```  
  
#### <a name="parameters"></a>Parameter  
 `_LinkRegistry`  
 Die Registrierung des Netzwerk-Link.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`const_pointer`|Ein Typ, der ein Zeiger auf eine `const` Element in einem `source_link_manager` Objekt.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` Element gespeichert, ein `source_link_manager` -Objekt zum Lesen und const-Operationen durchführt.|  
|`iterator`|Eine Typ, der einem Iterator bereitstellt, kann lesen oder ändern Sie ein Element in der `source_link_manager` Objekt.|  
|`type`|Der Typ des Link-Registrierung, die von verwaltet die `source_link_manager` Objekt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Source_link_manager-Konstruktor](#ctor)|Erstellt ein `source_link_manager`-Objekt.|  
|[~ Source_link_manager-Destruktor](#dtor)|Zerstört das `source_link_manager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Add-Methode](#add)|Fügt einen Link "Quelle" auf die `source_link_manager` Objekt.|  
|[Begin-Methode](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.|  
|[Contains-Methode](#contains)|Sucht die `network_link_registry` innerhalb dieses `source_link_manager` -Objekt für einen angegebenen Block.|  
|[Count-Methode](#count)|Zählt die Anzahl der verknüpften Blocks in der `source_link_manager` Objekt.|  
|[Reference-Methode](#reference)|Ruft einen Verweis auf die `source_link_manager` Objekt.|  
|[Register_target_block-Methode](#register_target_block)|Registriert den Zielblock, der diese enthält `source_link_manager` Objekt.|  
|[Release-Methode](#release)|Gibt den Verweis auf die `source_link_manager` Objekt.|  
|[Remove-Methode](#remove)|Entfernt ein Link aus der `source_link_manager` Objekt.|  
|[Set_bound-Methode](#set_bound)|Legt die maximale Anzahl von Quellenlinks, die zu diesem hinzugefügt werden können `source_link_manager` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Derzeit werden die Quellblöcke Verweis gezählt. Dies ist ein Wrapper für ein `network_link_registry` -Objekt, das gleichzeitigen Zugriff auf die Links und bietet die Möglichkeit, die Links mithilfe von Rückrufen zu verweisen. Meldungsblöcke ( `target_block`s oder `propagator_block`s) sollten diese Klasse für deren Quellenlinks verwenden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `source_link_manager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>Hinzufügen 

 Fügt einen Link "Quelle" auf die `source_link_manager` Objekt.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, der hinzugefügt werden soll.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>beginnen 

 Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `source_link_manager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand des Iterators sind durch ein `NULL` Link.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>enthält 

 Sucht die `network_link_registry` innerhalb dieses `source_link_manager` -Objekt für einen angegebenen Block.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block in gesucht werden, die `source_link_manager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der angegebene Block gefunden wurde, `false` andernfalls.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>Anzahl 

 Zählt die Anzahl der verknüpften Blocks in der `source_link_manager` Objekt.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der verknüpften Blocks in der `source_link_manager` Objekt.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>Referenz 

 Ruft einen Verweis auf die `source_link_manager` Objekt.  
  
```
void reference();
```  
  
##  <a name="a-nameregistertargetblocka-registertargetblock"></a><a name="register_target_block"></a>register_target_block 

 Registriert den Zielblock, der diese enthält `source_link_manager` Objekt.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Der Zielblock enthält dieses `source_link_manager` Objekt.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>Version 

 Gibt den Verweis auf die `source_link_manager` Objekt.  
  
```
void release();
```  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>Entfernen 

 Entfernt ein Link aus der `source_link_manager` Objekt.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link gefunden und entfernt wurde, `false` andernfalls.  
  
##  <a name="a-namesetbounda-setbound"></a><a name="set_bound"></a>set_bound 

 Legt die maximale Anzahl von Quellenlinks, die zu diesem hinzugefügt werden können `source_link_manager` Objekt.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Parameter  
 `_MaxLinks`  
 Die maximale Anzahl von Links.  
  
##  <a name="a-namectora-sourcelinkmanager"></a><a name="ctor"></a>source_link_manager 

 Erstellt ein `source_link_manager`-Objekt.  
  
```
source_link_manager();
```  
  
##  <a name="a-namedtora-sourcelinkmanager"></a><a name="dtor"></a>~ Source_link_manager 

 Zerstört das `source_link_manager`-Objekt.  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Single_link_registry-Klasse](single-link-registry-class.md)   
 [Multi_link_registry-Klasse](multi-link-registry-class.md)

