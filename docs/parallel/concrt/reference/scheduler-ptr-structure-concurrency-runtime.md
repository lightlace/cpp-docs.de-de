---
title: Scheduler_ptr-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 257dcae6df4deb0a52f7dee4db98adba2b2b4f29
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="schedulerptr-structure"></a>Scheduler_ptr-Struktur
Stellt einen Zeiger auf einen Planer dar. Diese Klasse ist vorhanden, um die Spezifikation einer freigegebenen Lebensdauer mithilfe von "shared_ptr" oder nur eines einfachen Verweises und eines unformatierten Zeigers zu ermöglichen.  
  
## <a name="syntax"></a>Syntax  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr::scheduler_ptr](#ctor)|Überladen. Erstellt einen scheduler-Zeiger von "shared_ptr" auf "scheduler".|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr::get](#get)|Gibt den Rohzeiger auf den Planer zurück.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr::operator bool](#operator_bool)|Testet, dass der scheduler-Zeiger nicht NULL ist.|  
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Verhält sich wie ein Zeiger.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** pplinterface.h  
  
 **Namespace:** Parallelität  
  
##  <a name="get"></a>  scheduler_ptr::Get-Methode  
 Gibt den Rohzeiger auf den Planer zurück.  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_bool"></a>  scheduler_ptr:: Operator bool   
 Testet, dass der scheduler-Zeiger nicht NULL ist.  
  
```operator bool() const;
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
Scheduler_interface * Operator -> (const);
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);

explizite Scheduler_ptr (_In_opt_ Scheduler_interface * pScheduler);
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)
