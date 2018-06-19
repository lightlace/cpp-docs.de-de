---
title: IUMSScheduler-Struktur | Microsoft Docs
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
ms.openlocfilehash: 489978a97d42439e5560a75e429c38be10c18c29
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688530"
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
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|Weist ein `IUMSCompletionList` Schnittstelle, um ein UMS-Zeitplanungsmodul Thread.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten Planer, der mit dem Ressourcen-Manager kommuniziert implementieren und UMS-Threads, die an dem Planer anstelle von gewöhnlichen Win32-Threads übergegeben werden sollen, sollten Sie eine Implementierung bereitstellen der `IUMSScheduler` Schnittstelle. Darüber hinaus sollten Sie festlegen, den Richtlinienwert für den Planerrichtlinienschlüssel `SchedulerKind` werden `UmsThreadDefault`. Wenn die Richtlinie gibt UMS-Threads an die `IScheduler` Schnittstelle, die als Parameter übergeben wird der [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) Methode muss ein `IUMSScheduler` Schnittstelle.  
  
 Der Ressourcen-Manager kann Sie UMS-Threads nur unter Betriebssystemen, die über die UMS-Funktion übergeben. 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützen UMS-Threads. Bei der Erstellung einer Planerrichtlinie mit der `SchedulerKind` Schlüssel festgelegt wird, auf den Wert `UmsThreadDefault` und die zugrunde liegende Plattform unterstützt keine UMS, den Wert des der `SchedulerKind` -Taste auf diese Richtlinie wird auf den Wert geändert werden `ThreadScheduler`. Sie sollten immer wieder der Richtlinienwert lesen, bevor erwartet, dass er UMS-Threads erhalten.  
  
 Die `IUMSScheduler` Schnittstelle ist ein Ende eines Kanals bidirektionale Kommunikation zwischen einem Planer und den Ressourcen-Manager. Das andere Ende wird dargestellt, indem die `IResourceManager` und `ISchedulerProxy` Schnittstellen, die vom Ressourcen-Manager implementiert werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="setcompletionlist"></a>  IUMSScheduler:: SetCompletionList-Methode  
 Weist ein `IUMSCompletionList` Schnittstelle, um ein UMS-Zeitplanungsmodul Thread.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pCompletionList`  
 Die Liste Schnittstelle für den rückrufabschluss für den Planer. Es gibt eine einzelne Liste pro Zeitplanungsmodul.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager wird diese Methode in einem Zeitplanungsmodul aufgerufen, der angibt, dass er UMS-Threads benötigt, nachdem der Planer eine anfängliche Zuordnung von Ressourcen angefordert hat. Der Planer können die `IUMSCompletionList` Schnittstelle, um zu bestimmen, wann UMS-Threadproxys "Blockierung aufgehoben" haben. Es ist nur zulässig, ein Threadproxy, der auf einem virtuellen Prozessorstamm zugewiesene UMS-Zeitplanungsmodul ausgeführt wird diese Schnittstelle zuzugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IUMSCompletionList-Struktur](iumscompletionlist-structure.md)   
 [IResourceManager-Struktur](iresourcemanager-structure.md)
