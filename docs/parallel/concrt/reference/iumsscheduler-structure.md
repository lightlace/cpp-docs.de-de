---
title: IUMSScheduler-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
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
ms.openlocfilehash: 58ca59224b5d9cdeb282562349642736a1b22c74
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="iumsscheduler-structure"></a>IUMSScheduler-Struktur
Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners, der planbare Threads vom Ressourcen-Manager der Concurrency Runtime im Benutzermodus erwartet. Der Ressourcen-Manager verwendet diese Schnittstelle für die Kommunikation mit UMS-Threadplanern. Die `IUMSScheduler`-Schnittstelle erbt von der `IScheduler`-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IUMSScheduler:: SetCompletionList](#setcompletionlist)|Weist eine `IUMSCompletionList` Schnittstelle, um ein UMS-Thread-Scheduler.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten Planer, der mit dem Ressourcen-Manager kommuniziert implementieren und UMS-Threads an Ihren Planer anstelle gewöhnlicher Win32-Threads übergeben werden sollen, sollten Sie eine Implementierung bereitstellen der `IUMSScheduler` Schnittstelle. Darüber hinaus sollten Sie festlegen, den Richtlinienwert für den Planerrichtlinienschlüssel `SchedulerKind` werden `UmsThreadDefault`. Wenn die Richtlinie UMS-Thread, gibt die `IScheduler` -Schnittstelle, die als Parameter übergeben wird die [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) Methode muss ein `IUMSScheduler` Schnittstelle.  
  
 Der Ressourcen-Manager kann Sie nur auf Betriebssystemen UMS-Threads übergeben, die über die UMS-Funktion verfügen. 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützen UMS-Threads. Wenn Sie eine Planerrichtlinie mit Erstellen der `SchedulerKind` Schlüssel auf den Wert festgelegt `UmsThreadDefault` und die zugrunde liegende Plattform UMS, den Wert von nicht unterstützt die `SchedulerKind` -Taste auf die Richtlinie wird auf den Wert geändert werden `ThreadScheduler`. Sie sollten immer wieder Richtlinienwert lesen, bevor erwarten UMS-Threads.  
  
 Die `IUMSScheduler` -Schnittstelle ist ein Ende eine bidirektionale Kommunikation zwischen einem Planer und dem Ressourcen-Manager. Das andere Ende wird dargestellt, durch die `IResourceManager` und `ISchedulerProxy` Schnittstellen, die vom Ressourcen-Manager implementiert werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="setcompletionlist"></a>IUMSScheduler:: SetCompletionList-Methode  
 Weist eine `IUMSCompletionList` Schnittstelle, um ein UMS-Thread-Scheduler.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pCompletionList`  
 Die Fertigstellung Liste-Schnittstelle für den Planer. Es gibt eine einzelne Liste pro Planer.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager wird diese Methode für einen Planer aufgerufen, der angibt, dass er UMS-Threads benötigt, nachdem der Planer eine ursprüngliche Zuordnung von Ressourcen angefordert hat. Der Planer können die `IUMSCompletionList` Schnittstelle, um zu bestimmen, wann die Blockierung von UMS-Threadproxys aufgehoben wurde. Es ist nur gültig auf dieser Schnittstelle aus dem ein Threadproxy ausgeführt, die auf einem virtuellen Prozessorstamm UMS-Scheduler zugewiesen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IUMSCompletionList-Struktur](iumscompletionlist-structure.md)   
 [IResourceManager-Struktur](iresourcemanager-structure.md)

