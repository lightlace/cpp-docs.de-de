---
title: Scheduler_ptr-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
dev_langs: C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bdb47301f890cc96d21bf797444c44b48da3761b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[scheduler_ptr:: scheduler_ptr](#ctor)|Überladen. Erstellt einen scheduler-Zeiger von "shared_ptr" auf "scheduler".|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr::Get](#get)|Gibt den Rohzeiger auf den Planer zurück.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_ptr:: Operator bool](#operator_bool)|Testet, dass der scheduler-Zeiger nicht NULL ist.|  
|[scheduler_ptr:: Operator-&gt;](#operator_ptr)|Verhält sich wie ein Zeiger.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** pplinterface.h  
  
 **Namespace:** Parallelität  
  
##  <a name="get"></a>scheduler_ptr::Get-Methode  
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
Scheduler_interface * Operator -> (const);
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
explizite Scheduler_ptr (Std:: shared_ptr < Scheduler_interface > Zeitplanungsmodul);

explizite Scheduler_ptr (_In_opt_ Scheduler_interface * pScheduler);
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)
