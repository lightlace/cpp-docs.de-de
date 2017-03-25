---
title: Scheduler_ptr-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
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
ms.openlocfilehash: 4bef1995724d078c9702669806ff61d5563ac465
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerptr-structure"></a>Scheduler_ptr-Struktur
Stellt einen Zeiger auf einen Planer dar. Diese Klasse ist vorhanden, um die Spezifikation einer freigegebenen Lebensdauer mithilfe von "shared_ptr" oder nur eines einfachen Verweises und eines unformatierten Zeigers zu ermöglichen.  
  
## <a name="syntax"></a>Syntax  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr:: scheduler_ptr](#ctor)|Überladen. Erstellt einen scheduler-Zeiger von "shared_ptr" auf "scheduler".|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr Get-Method](#get)|Gibt den Rohzeiger auf den Planer zurück.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr:: Operator bool](#operator_bool)|Testet, dass der scheduler-Zeiger nicht NULL ist.|  
|[scheduler_ptr::-&gt;](#operator_ptr)|Verhält sich wie ein Zeiger.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** pplinterface.h  
  
 **Namespace:** Parallelität  
  
##  <a name="get"></a>scheduler_ptr-Methode für Get-Method  
 Gibt den Rohzeiger auf den Planer zurück.  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_bool"></a>scheduler_ptr:: Operator bool   
 Testet, dass der scheduler-Zeiger nicht NULL ist.  
  
'''Operator bool() const;
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
Scheduler_interface * const operator->();
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
explizite scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);</scheduler_interface>

explizite Scheduler_ptr (_In_opt_ Scheduler_interface * pScheduler);
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)

