---
title: IUMSCompletionList-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 65655e4e03a7b187e0bbadbd576bc088bb57f7c8
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList-Struktur
Stellt eine UMS-Vervollständigungsliste dar. Wenn ein UMS-Thread blockiert wird, wird der festgelegte Planungskontext des Planers weitergeleitet, um zu entscheiden, was für den Stamm des zugrunde liegenden virtuellen Prozessors geplant werden soll, während der ursprüngliche Thread blockiert ist. Wenn die Blockierung des ursprünglichen Threads aufgehoben wird, stellt das Betriebssystem ihn in die Warteschlange für die Vervollständigungsliste, auf die über diese Schnittstelle zugegriffen werden kann. Der Planer kann die Vervollständigungsliste für den festgelegten Planungskontext oder eine beliebige andere Stelle abfragen, in der er nach Arbeit sucht.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IUMSCompletionList:: GetUnblockNotifications](#getunblocknotifications)|Ruft eine Kette von `IUMSUnblockNotification` Schnittstellen, deren zugeordnete Threadproxys seit dem letzten Aufruf dieser Methode aufgerufen wurde, Ausführungskontexte darstellen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Planer muss besonders vorsichtig, welche Aktionen durchgeführt werden, nachdem diese Schnittstelle zum Entfernen von Elementen aus der Vervollständigungsliste sein. Die Elemente sollten auf der Liste ausführbarer Kontexte des Planers platziert werden und so bald wie möglich im Allgemeinen zugegriffen werden. Es ist durchaus möglich, dass eines der Elemente aus der Warteschlange entfernt den Besitz einer beliebigen Sperre zugewiesen wurde. Der Planer kann keine beliebigen Funktionsaufrufe ausführen, die eine Blockierung kann zwischen dem Aufruf von Elementen aus der Warteschlange entfernt und die Platzierung dieser Elemente in einer Liste, die im Allgemeinen von innerhalb des Planers zugegriffen werden kann.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getunblocknotifications"></a>IUMSCompletionList:: GetUnblockNotifications-Methode  
 Ruft eine Kette von `IUMSUnblockNotification` Schnittstellen, deren zugeordnete Threadproxys seit dem letzten Aufruf dieser Methode aufgerufen wurde, Ausführungskontexte darstellen.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kette von `IUMSUnblockNotification` Schnittstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebenen Benachrichtigungen sind ungültig, sobald die Ausführungskontexte neu geplant werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IUMSScheduler-Struktur](iumsscheduler-structure.md)   
 [IUMSUnblockNotification-Struktur](iumsunblocknotification-structure.md)

