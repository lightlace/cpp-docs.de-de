---
title: IUMSScheduler-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46ed7dac35dce4b5df51cd4c218a1a70a84d21df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079062"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler-Struktur
Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners, der planbare Threads vom Ressourcen-Manager der Concurrency Runtime im Benutzermodus erwartet. Der Ressourcen-Manager verwendet diese Schnittstelle für die Kommunikation mit UMS-Threadplanern. Die `IUMSScheduler`-Schnittstelle erbt von der `IScheduler`-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|Weist eine `IUMSCompletionList` Schnittstelle, um ein UMS-Thread-Planer.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten Planer, der mit dem Resource Manager kommuniziert implementieren und UMS-Threads, die an der Planer statt der gewöhnlichen Win32-Threads übergegeben werden sollen, sollten Sie eine Implementierung bereitstellen der `IUMSScheduler` Schnittstelle. Darüber hinaus sollten Sie festlegen, den Richtlinienwert für den Scheduler-Richtlinienschlüssel `SchedulerKind` sein `UmsThreadDefault`. Wenn die Richtlinie UMS-Thread, gibt die `IScheduler` -Schnittstelle, die als Parameter übergeben wird die [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) Methode muss eine `IUMSScheduler` Schnittstelle.  
  
 Der Ressourcen-Manager kann Sie nur auf Betriebssystemen UMS-Threads, die die UMS-Funktion übergeben. 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützen UMS-Threads. Bei der Erstellung einer Planerrichtlinie mit der `SchedulerKind` Schlüssel festgelegt wird, auf den Wert `UmsThreadDefault` und die zugrunde liegende Plattform unterstützt keine UMS, den Wert des der `SchedulerKind` -Taste auf die Richtlinie wird auf den Wert geändert `ThreadScheduler`. Sie sollten immer wieder der Richtlinienwert lesen, bevor UMS-Threads erhalten möchte.  
  
 Die `IUMSScheduler` Schnittstelle ist ein Ende der einen bidirektionalen Kanal für die Kommunikation zwischen einem Planer und der Ressourcen-Manager. Das andere Ende wird dargestellt, durch die `IResourceManager` und `ISchedulerProxy` Schnittstellen, die vom Ressourcen-Manager implementiert werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="setcompletionlist"></a>  IUMSScheduler:: SetCompletionList-Methode  
 Weist eine `IUMSCompletionList` Schnittstelle, um ein UMS-Thread-Planer.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>Parameter  
*pCompletionList*<br/>
Die Vervollständigung Liste-Schnittstelle für das Zeitplanungsmodul. Es gibt eine einzelne Liste pro Zeitplanungsmodul.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager wird diese Methode für einen Planer aufgerufen, der angibt, dass es UMS-Threads benötigt wird, nachdem der Scheduler eine anfängliche Zuordnung von Ressourcen angefordert hat. Der Planer können die `IUMSCompletionList` Schnittstelle, um zu bestimmen, wann UMS-Threadproxys Blockierung aufgehoben wurde. Es ist nur gültig, auf diese Schnittstelle über ein Threadproxy, der auf einem virtuellen Prozessorstamm zugewiesen, der UMS-Zeitplanungsmodul ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IUMSCompletionList-Struktur](iumscompletionlist-structure.md)   
 [IResourceManager-Struktur](iresourcemanager-structure.md)
