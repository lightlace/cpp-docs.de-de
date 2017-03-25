---
title: IUMSUnblockNotification-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: ee9c1ada7718b948e5a038852bfa5514127324b1
ms.lasthandoff: 03/17/2017

---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification-Struktur
Stellt eine Benachrichtigung vom Ressourcen-Manager darüber dar, dass ein Threadproxy, der blockiert und eine Rückkehr zum festgelegten Planungskontext des Planers ausgelöst hatte, die Blockierung aufgehoben hat und zum Planen bereit ist. Diese Schnittstelle ist ungültig, sobald der zugeordnete Ausführungskontext des Threadproxys, der von der `GetContext`-Methode zurückgegeben wurde, neu geplant wird.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IUMSUnblockNotification;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IUMSUnblockNotification:: GetContext](#getcontext)|Gibt die `IExecutionContext` -Schnittstelle für den Ausführungskontext zugeordnete der Threadproxy, der Blockierung aufgehoben hat. Sobald diese Methode zurückkehrt und der zugrunde liegende Ausführungskontext neu geplant wurde, über einen Aufruf an die `IThreadProxy::SwitchTo` -Methode, die diese Schnittstelle ist nicht mehr gültig.|  
|[IUMSUnblockNotification:: GetNextUnblockNotification](#getnextunblocknotification)|Gibt die nächste `IUMSUnblockNotification` -Schnittstelle in der Kette von der Methode zurückgegebene `IUMSCompletionList::GetUnblockNotifications`.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getcontext"></a>IUMSUnblockNotification:: GetContext-Methode  
 Gibt die `IExecutionContext` -Schnittstelle für den Ausführungskontext zugeordnete der Threadproxy, der Blockierung aufgehoben hat. Sobald diese Methode zurückkehrt und der zugrunde liegende Ausführungskontext neu geplant wurde, über einen Aufruf an die `IThreadProxy::SwitchTo` -Methode, die diese Schnittstelle ist nicht mehr gültig.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `IExecutionContext` -Schnittstelle für den Ausführungskontext zu einem Threadproxy, der Blockierung aufgehoben hat.  
  
##  <a name="getnextunblocknotification"></a>IUMSUnblockNotification:: GetNextUnblockNotification-Methode  
 Gibt die nächste `IUMSUnblockNotification` -Schnittstelle in der Kette von der Methode zurückgegebene `IUMSCompletionList::GetUnblockNotifications`.  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nächste `IUMSUnblockNotification` -Schnittstelle in der Kette von der Methode zurückgegebene `IUMSCompletionList::GetUnblockNotifications`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IUMSScheduler-Struktur](iumsscheduler-structure.md)   
 [IUMSCompletionList-Struktur](iumscompletionlist-structure.md)

