---
title: Source_link_manager-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 8e875fdd02a42e1cb1c144b0b7da07a1f4e9a184
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
|[source_link_manager](#ctor)|Erstellt ein `source_link_manager`-Objekt.|  
|[~ Source_link_manager-Destruktor](#dtor)|Zerstört das `source_link_manager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[add](#add)|Fügt einen Link "Quelle" auf die `source_link_manager` Objekt.|  
|[begin](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.|  
|[enthält](#contains)|Sucht die `network_link_registry` innerhalb dieses `source_link_manager` -Objekt für einen angegebenen Block.|  
|[count](#count)|Zählt die Anzahl der verknüpften Blocks in der `source_link_manager` Objekt.|  
|[Verweis](#reference)|Ruft einen Verweis auf die `source_link_manager` Objekt.|  
|[register_target_block](#register_target_block)|Registriert den Zielblock, der diese enthält `source_link_manager` Objekt.|  
|[release](#release)|Gibt den Verweis auf die `source_link_manager` Objekt.|  
|[remove](#remove)|Entfernt ein Link aus der `source_link_manager` Objekt.|  
|[set_bound](#set_bound)|Legt die maximale Anzahl von Quellenlinks, die zu diesem hinzugefügt werden können `source_link_manager` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Derzeit werden die Quellblöcke Verweis gezählt. Dies ist ein Wrapper für ein `network_link_registry` -Objekt, das gleichzeitigen Zugriff auf die Links und bietet die Möglichkeit, die Links mithilfe von Rückrufen zu verweisen. Meldungsblöcke ( `target_block`s oder `propagator_block`s) sollten diese Klasse für deren Quellenlinks verwenden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `source_link_manager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="add"></a>Hinzufügen 

 Fügt einen Link "Quelle" auf die `source_link_manager` Objekt.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, der hinzugefügt werden soll.  
  
##  <a name="begin"></a>beginnen 

 Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `source_link_manager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand des Iterators sind durch ein `NULL` Link.  
  
##  <a name="contains"></a>enthält 

 Sucht die `network_link_registry` innerhalb dieses `source_link_manager` -Objekt für einen angegebenen Block.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block in gesucht werden, die `source_link_manager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der angegebene Block gefunden wurde, `false` andernfalls.  
  
##  <a name="count"></a>Anzahl 

 Zählt die Anzahl der verknüpften Blocks in der `source_link_manager` Objekt.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der verknüpften Blocks in der `source_link_manager` Objekt.  
  
##  <a name="reference"></a>Referenz 

 Ruft einen Verweis auf die `source_link_manager` Objekt.  
  
```
void reference();
```  
  
##  <a name="register_target_block"></a>register_target_block 

 Registriert den Zielblock, der diese enthält `source_link_manager` Objekt.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Der Zielblock enthält dieses `source_link_manager` Objekt.  
  
##  <a name="release"></a>Version 

 Gibt den Verweis auf die `source_link_manager` Objekt.  
  
```
void release();
```  
  
##  <a name="remove"></a>Entfernen 

 Entfernt ein Link aus der `source_link_manager` Objekt.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link gefunden und entfernt wurde, `false` andernfalls.  
  
##  <a name="set_bound"></a>set_bound 

 Legt die maximale Anzahl von Quellenlinks, die zu diesem hinzugefügt werden können `source_link_manager` Objekt.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Parameter  
 `_MaxLinks`  
 Die maximale Anzahl von Links.  
  
##  <a name="ctor"></a>source_link_manager 

 Erstellt ein `source_link_manager`-Objekt.  
  
```
source_link_manager();
```  
  
##  <a name="dtor"></a>~ Source_link_manager 

 Zerstört das `source_link_manager`-Objekt.  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Single_link_registry-Klasse](single-link-registry-class.md)   
 [multi_link_registry-Klasse](multi-link-registry-class.md)

