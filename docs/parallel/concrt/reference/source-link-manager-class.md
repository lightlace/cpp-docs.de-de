---
title: Source_link_manager-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67cf15c6681c989a2da2b4e6824fec6012c517bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`const_pointer`|Ein Typ, der ein Zeiger auf eine `const` Element in einem `source_link_manager` Objekt.|  
|`const_reference`|Ein Typ, der einen Verweis auf eine `const` Element gespeichert wird, einem `source_link_manager` Objekt zum Lesen und Ausführen von const-Operationen.|  
|`iterator`|Ein Typ, der einem Iterator bereitstellt, kann lesen oder ändern Sie ein Element in der `source_link_manager` Objekt.|  
|`type`|Der Typ des Link-Registrierung über die `source_link_manager` Objekt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[source_link_manager](#ctor)|Erstellt ein `source_link_manager`-Objekt.|  
|[~ Source_link_manager-Destruktor](#dtor)|Zerstört das `source_link_manager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[add](#add)|Fügt einen Quelllink zu der `source_link_manager` Objekt.|  
|[begin](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.|  
|[enthält](#contains)|Sucht die `network_link_registry` innerhalb dieser `source_link_manager` Objekt für einen angegebenen Block.|  
|[count](#count)|Zählt die Anzahl der verknüpften Blöcke in der `source_link_manager` Objekt.|  
|[Verweis](#reference)|Ruft einen Verweis auf die `source_link_manager` Objekt.|  
|[register_target_block](#register_target_block)|Registriert den Zielblock, das dies enthält `source_link_manager` Objekt.|  
|[release](#release)|Entfernt den Verweis auf die `source_link_manager` Objekt.|  
|[remove](#remove)|Entfernt eine Verknüpfung aus dem `source_link_manager` Objekt.|  
|[set_bound](#set_bound)|Legt die maximale Anzahl von quellverknüpfungen, die zu diesem hinzugefügt werden können `source_link_manager` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Aktuell sind die Quellblöcke Verweis gezählt. Dies ist ein Wrapper auf eine `network_link_registry` -Objekt, das gleichzeitigen Zugriff auf die Links und ermöglicht den Zugriff auf die Links mithilfe von Rückrufen zu verweisen. Meldungsblöcke ( `target_block`s oder `propagator_block`s) sollten diese Klasse für ihren quellverknüpfungen verwenden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `source_link_manager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="add"></a>Hinzufügen 

 Fügt einen Quelllink zu der `source_link_manager` Objekt.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block hinzugefügt werden.  
  
##  <a name="begin"></a>beginnen 

 Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der `source_link_manager` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Endzustand des Iterators erkennbar ist eine `NULL` Link.  
  
##  <a name="contains"></a>enthält 

 Sucht die `network_link_registry` innerhalb dieser `source_link_manager` Objekt für einen angegebenen Block.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf ein Block, der für gesucht werden soll, in der `source_link_manager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der angegebene Block gefunden wurde, `false` andernfalls.  
  
##  <a name="count"></a>Anzahl 

 Zählt die Anzahl der verknüpften Blöcke in der `source_link_manager` Objekt.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der verknüpften Blöcke in der `source_link_manager` Objekt.  
  
##  <a name="reference"></a>Referenz 

 Ruft einen Verweis auf die `source_link_manager` Objekt.  
  
```
void reference();
```  
  
##  <a name="register_target_block"></a>register_target_block 

 Registriert den Zielblock, das dies enthält `source_link_manager` Objekt.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Der Zielblock enthält dieses `source_link_manager` Objekt.  
  
##  <a name="release"></a>Version 

 Entfernt den Verweis auf die `source_link_manager` Objekt.  
  
```
void release();
```  
  
##  <a name="remove"></a>Entfernen 

 Entfernt eine Verknüpfung aus dem `source_link_manager` Objekt.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parameter  
 `_Link`  
 Ein Zeiger auf einen Block, wenn entfernt gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Link wurde gefunden und entfernt, `false` andernfalls.  
  
##  <a name="set_bound"></a>set_bound 

 Legt die maximale Anzahl von quellverknüpfungen, die zu diesem hinzugefügt werden können `source_link_manager` Objekt.  
  
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
