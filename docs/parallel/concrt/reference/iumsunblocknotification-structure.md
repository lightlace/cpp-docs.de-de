---
title: IUMSUnblockNotification-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs: C++
helpviewer_keywords: IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2767ae80c2b967bfbe78f35431949b472ff550f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[IUMSUnblockNotification:: GetContext](#getcontext)|Gibt die `IExecutionContext` Schnittstelle für den der Threadproxy, der "Blockierung aufgehoben" verfügt über zugeordnete Ausführungskontext. Sobald diese Methode zurückkehrt und der zugrunde liegenden Ausführungskontext neu geplant wurde, über einen Aufruf an die `IThreadProxy::SwitchTo` -Methode, die diese Schnittstelle ist nicht mehr gültig.|  
|[IUMSUnblockNotification:: GetNextUnblockNotification](#getnextunblocknotification)|Gibt die nächste `IUMSUnblockNotification` Schnittstelle in der Kette, die von der Methode zurückgegebenen `IUMSCompletionList::GetUnblockNotifications`.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getcontext"></a>IUMSUnblockNotification:: GetContext-Methode  
 Gibt die `IExecutionContext` Schnittstelle für den der Threadproxy, der "Blockierung aufgehoben" verfügt über zugeordnete Ausführungskontext. Sobald diese Methode zurückkehrt und der zugrunde liegenden Ausführungskontext neu geplant wurde, über einen Aufruf an die `IThreadProxy::SwitchTo` -Methode, die diese Schnittstelle ist nicht mehr gültig.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `IExecutionContext` Schnittstelle für den Ausführungskontext für eine Threadproxy, der Blockierung aufgehoben hat.  
  
##  <a name="getnextunblocknotification"></a>IUMSUnblockNotification:: GetNextUnblockNotification-Methode  
 Gibt die nächste `IUMSUnblockNotification` Schnittstelle in der Kette, die von der Methode zurückgegebenen `IUMSCompletionList::GetUnblockNotifications`.  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das nächste `IUMSUnblockNotification` Schnittstelle in der Kette, die von der Methode zurückgegebenen `IUMSCompletionList::GetUnblockNotifications`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IUMSScheduler-Struktur](iumsscheduler-structure.md)   
 [IUMSCompletionList-Struktur](iumscompletionlist-structure.md)
