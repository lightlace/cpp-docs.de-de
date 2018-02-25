---
title: IUMSCompletionList-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 378eccbc0e29a9356ffd89699039b9877c76c751
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList-Struktur
Stellt eine UMS-Vervollständigungsliste dar. Wenn ein UMS-Thread blockiert wird, wird der festgelegte Planungskontext des Planers weitergeleitet, um zu entscheiden, was für den Stamm des zugrunde liegenden virtuellen Prozessors geplant werden soll, während der ursprüngliche Thread blockiert ist. Wenn die Blockierung des ursprünglichen Threads aufgehoben wird, stellt das Betriebssystem ihn in die Warteschlange für die Vervollständigungsliste, auf die über diese Schnittstelle zugegriffen werden kann. Der Planer kann die Vervollständigungsliste für den festgelegten Planungskontext oder eine beliebige andere Stelle abfragen, in der er nach Arbeit sucht.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|Ruft eine Kette von `IUMSUnblockNotification` Schnittstellen darstellt Ausführungskontexte, deren zugeordnete Threadproxys seit der letzten Ausführung dieser Methode wurde aufgerufen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Planer muss besonders vorsichtig, welche Aktionen durchgeführt werden, nachdem Sie diese Schnittstelle, um Elemente aus der Vervollständigungsliste dequeue nutzen. Die Elemente müssen auf den Planer Liste ausführbarer Kontexte platziert werden und so bald wie möglich in der Regel zugegriffen werden. Es ist möglich, dass eines der Elemente aus den Besitz einer beliebigen Sperre gewährt wurde. Der Planer kann keine beliebigen Funktionsaufrufe ausführen, die Blockierung verursachen können, zwischen dem Aufruf von Elementen aus der Warteschlange entfernen und die Platzierung der Elemente in einer Liste, die in der Regel innerhalb des Planers aus zugegriffen werden kann.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getunblocknotifications"></a>  IUMSCompletionList:: GetUnblockNotifications-Methode  
 Ruft eine Kette von `IUMSUnblockNotification` Schnittstellen darstellt Ausführungskontexte, deren zugeordnete Threadproxys seit der letzten Ausführung dieser Methode wurde aufgerufen.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kette von `IUMSUnblockNotification` Schnittstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Benachrichtigungen sind ungültig, sobald die Ausführungskontexte neu geplant werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IUMSScheduler-Struktur](iumsscheduler-structure.md)   
 [IUMSUnblockNotification-Struktur](iumsunblocknotification-structure.md)
