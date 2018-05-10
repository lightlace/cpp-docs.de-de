---
title: IThreadProxy-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
dev_langs:
- C++
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbf59302a73374f08f1c226c1e7e56202654dcfb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="ithreadproxy-structure"></a>IThreadProxy-Struktur
Eine Abstraktion für einen Thread der Ausführung. Abhängig von dem von Ihnen erstellten `SchedulerType`-Richtlinienschlüssel des Planers, gewährt der Ressourcen-Manager eine Threadproxy, der entweder von einem regulären Win32-Thread oder einem im Benutzermodus planbaren (UMS) Thread unterstützt wird. UMS-Threads werden auf 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IThreadProxy;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IThreadProxy::GetId](#getid)|Gibt einen eindeutigen Bezeichner für den Threadproxy zurück.|  
|[IThreadProxy::SwitchOut](#switchout)|Hebt die Zuordnung des Kontexts vom zugrunde liegenden virtuellen Prozessorstamm auf.|  
|[IThreadProxy::SwitchTo](#switchto)|Führt einen kooperativen Kontextwechsel aus dem Kontext des derzeit ausgeführten an eine andere Definition aus.|  
|[IThreadProxy::YieldToSystem](#yieldtosystem)|Bewirkt, dass der aufrufende Thread die Ausführung an einen anderen Thread übergibt, der auf dem aktuellen Prozessor ausgeführt werden kann. Das Betriebssystem wählt den nächsten Thread ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Threadproxys werden mit Ausführungskontexten verbunden, dargestellt durch die Schnittstelle `IExecutionContext` als Mittel zum Weiterleiten von Arbeit.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IThreadProxy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getid"></a>  IThreadProxy:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den Threadproxy zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine eindeutige ganzzahlige Bezeichner.  
  
##  <a name="switchout"></a>  IThreadProxy:: SwitchOut-Methode  
 Hebt die Zuordnung des Kontexts vom zugrunde liegenden virtuellen Prozessorstamm auf.  
  
```
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `switchState`  
 Gibt den Zustand des Threadproxys an, der den Wechsel ausführt. Der Parameter ist vom Typ `SwitchingProxyState`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie `SwitchOut`, wenn Sie aus irgendeinem Grund die Zuordnung eines Kontexts zu einem virtuellen Prozessorstamm aufheben müssen, in dem dieser ausgeführt wird. Je nachdem, welchen Wert Sie an den `switchState`-Parameter übergeben, und abhängig von dessen Ausführung auf einem virtuellen Prozessorstamm, wird der Aufruf entweder sofort zurückgegeben oder der dem Kontext zugeordnete Threadproxy wird blockiert. Es ist nicht zulässig, `SwitchOut` aufzurufen, wenn der Parameter auf `Idle` festgelegt ist. Auf diese Weise führt zu einer [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme.  
  
 `SwitchOut` ist nützlich, wenn Sie die Anzahl der Stämme virtueller Prozessoren für den Planer verringern möchten, da der Ressourcen-Manager Sie angewiesen hat, dies zu tun oder Sie den Stamm eines überzeichneten temporären virtuellen Prozessors angefordert haben und diesen nicht mehr benötigen. In diesem Fall sollten Sie die Methode aufrufen [IVirtualProcessorRoot::Remove](http://msdn.microsoft.com/en-us/ad699b4a-1972-4390-97ee-9c083ba7d9e4) auf der virtuellen Prozessorstamm, vor einem Aufruf an `SwitchOut` mit dem Parameter `switchState` festgelegt `Blocking`. Auf diese Weise wird der Threadproxy blockiert. Die Ausführung wird fortgesetzt, wenn im Planer ein anderer virtueller Prozessorstamm für die Ausführung verfügbar ist. Die Ausführung des blockierten Threadproxys kann fortgesetzt werden, indem die `SwitchTo`-Funktion aufgerufen wird, um zum Ausführungskontext dieses Threadproxys zu wechseln. Sie können den Threadproxy auch fortsetzen, indem Sie dessen zugeordneten Kontext verwenden, um den Stamm eines virtuellen Prozessors zu aktivieren. Weitere Informationen hierzu finden Sie unter [IVirtualProcessorRoot](ivirtualprocessorroot-structure.md#activate).  
  
 Sie können `SwitchOut` zudem verwenden, um den virtuellen Prozessor erneut zu initialisieren, damit dieser zukünftig aktiviert werden kann, wenn Sie den Threadproxy blockieren oder vorübergehend vom Stamm des virtuellen Prozessors, für den dieser ausgeführt wird, und vom Planer, für den er Arbeit verteilt, trennen möchten. Verwenden Sie `SwitchOut` mit dem auf `switchState` festgelegten `Blocking`-Parameter, wenn Sie den Threadproxy blockieren möchten. Wie oben beschrieben, kann er zu einem späteren Zeitpunkt mithilfe von `SwitchTo` oder `IVirtualProcessorRoot::Activate` fortgesetzt werden. Verwenden Sie `SwitchOut` mit dem auf `Nesting` festgelegten Parameter, wenn Sie diesen Threadproxy vorübergehend vom Stamm des virtuellen Prozessors, auf dem er ausgeführt wird, und vom Planer, dem der virtuelle Prozessor zugeordnet ist, trennen möchten. Das Aufrufen von `SwitchOut` mit dem auf `switchState` festgelegten `Nesting`-Parameter führt während dessen Ausführung auf einem virtuellen Prozessorstamm zu einer erneuten Initialisierung des Stamms und zur Fortsetzung des aktuellen Threadproxys, obwohl dieser nicht erforderlich ist. Der Threadproxy den Planer verlassen hat, bis sie ruft die [IThreadProxy:: SwitchOut](#switchout) Methode mit `Blocking` zu einem späteren Zeitpunkt. Der zweite Aufruf von `SwitchOut` mit dem auf `Blocking` festgelegten Parameter soll den Kontext in einen blockierten Zustand zurückversetzen, damit er im Planer, von dem er getrennt ist, mit `SwitchTo` oder `IVirtualProcessorRoot::Activate` fortgesetzt werden kann. Da die Ausführung nicht auf einem virtuellen Prozessorstamm erfolgt, findet keine erneute Initialisierung statt.  
  
 Ein erneut initialisierter virtueller Prozessorstamm unterscheidet sich nicht von einem neuen virtuellen Prozessorstamm, der dem Planer vom Ressourcen-Manager gewährt wurde. Sie können ihn für die Ausführung verwenden, indem Sie ihn mit `IVirtualProcessorRoot::Activate` in einem Ausführungskontext aktivieren.  
  
 `SwitchOut` muss für die `IThreadProxy`-Schnittstelle aufgerufen werden, die den gerade ausgeführten Thread darstellt, oder die Ergebnisse sind nicht definiert.  
  
 In den Bibliotheken und Headern, die mit Visual Studio 2010 geliefert wurden, weist diese Methode keinen Parameter auf, und der virtuelle Prozessorstamm wurde nicht initialisiert. Um altes Verhalten beizubehalten, wird der Standardparameterwert von `Blocking` angegeben.  
  
##  <a name="switchto"></a>  IThreadProxy:: SwitchTo-Methode  
 Führt einen kooperativen Kontextwechsel aus dem Kontext des derzeit ausgeführten an eine andere Definition aus.  
  
```
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Ausführungskontext kooperativ zu wechseln.  
  
 `switchState`  
 Gibt den Zustand des Threadproxys an, der den Wechsel ausführt. Der Parameter ist vom Typ `SwitchingProxyState`.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können aus einem Ausführungskontext zu einem anderen, wechseln Sie aus der [IExecutionContext:: Dispatch](iexecutioncontext-structure.md#dispatch) Methode des ersten Ausführungskontexts. Die Methode ordnet den Ausführungskontext `pContext` mit dem ein Threadproxy, wenn es nicht bereits einem zugeordnet ist. Der Besitz des aktuellen Threadproxys richtet sich nach den Wert aus, Sie für geben, die `switchState` Argument.  
  
 Verwenden Sie den Wert `Idle` bei den derzeit ausgeführten Threadproxy zum Ressourcen-Manager zurückgegeben werden soll. Aufrufen von `SwitchTo` mit dem Parameter `switchState` festgelegt `Idle` führt dazu, dass den Ausführungskontext `pContext` Ausführung in der zugrunde liegenden Ausführungsressource. Besitz an diesen Threadproxy zum Ressourcen-Manager übergeben, und es wird erwartet, aus des Ausführungskontexts zurückgeben `Dispatch` Methode kurz nach `SwitchTo` zurückgegeben wird, um die Übertragung abzuschließen. Der Ausführungskontext, den den Threadproxy weitergeleitet wurde der Threadproxy aufgehoben wird, und der Planer kann seine wiederzuverwenden oder Belieben zu zerstören.  
  
 Verwenden Sie den Wert `Blocking` Wenn Sie diesen Threadproxy einen blockierten Zustand eingeben möchten. Aufrufen von `SwitchTo` mit dem Parameter `switchState` festgelegt `Blocking` führt dazu, dass den Ausführungskontext `pContext` die Ausführung gestartet, und der aktuellen Threadproxy blockiert, bis er fortgesetzt wird. Der Planer behält den Besitz des Threadproxys an, wenn der Threadproxy befindet der `Blocking` Zustand. Die Ausführung des blockierten Threadproxys kann fortgesetzt werden, indem die `SwitchTo`-Funktion aufgerufen wird, um zum Ausführungskontext dieses Threadproxys zu wechseln. Sie können den Threadproxy auch fortsetzen, indem Sie dessen zugeordneten Kontext verwenden, um den Stamm eines virtuellen Prozessors zu aktivieren. Weitere Informationen hierzu finden Sie unter [IVirtualProcessorRoot](ivirtualprocessorroot-structure.md#activate).  
  
 Verwenden Sie den Wert `Nesting` Wenn Sie vorübergehend vom Stamm virtuellen Prozessors diesen Threadproxy Trennen dieser ausgeführt wird, und der Planer er Arbeit verteilt. Aufrufen von `SwitchTo` mit dem Parameter `switchState` festgelegt `Nesting` führt dazu, dass den Ausführungskontext `pContext` starten ausführen und die aktuelle Threadproxy auch weiterhin ohne die Notwendigkeit von einem virtuellen Prozessorstamm ausgeführt. Der Threadproxy den Planer verlassen hat, bis sie ruft die [IThreadProxy:: SwitchOut](#switchout) Methode zu einem späteren Zeitpunkt. Die `IThreadProxy::SwitchOut` Methode konnte der Threadproxy blockiert, bis ein virtueller Prozessorstamm für planen verfügbar ist.  
  
 `SwitchTo` muss für die `IThreadProxy`-Schnittstelle aufgerufen werden, die den gerade ausgeführten Thread darstellt, oder die Ergebnisse sind nicht definiert. Löst die Funktion `invalid_argument` Wenn der Parameter `pContext` festgelegt ist, um `NULL`.  
  
##  <a name="yieldtosystem"></a>  IThreadProxy:: YieldToSystem-Methode  
 Bewirkt, dass der aufrufende Thread die Ausführung an einen anderen Thread übergibt, der auf dem aktuellen Prozessor ausgeführt werden kann. Das Betriebssystem wählt den nächsten Thread ausgeführt werden.  
  
```
virtual void YieldToSystem() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufruf durch ein Threadproxy, der von einem regulären Windows-Thread unterstützt `YieldToSystem` verhält sich genau wie die Windows-Funktion `SwitchToThread`. Jedoch im Falle eines Aufrufs von im Benutzermodus planbare (UMS) Threads, die `SwitchToThread` Funktion delegiert die Aufgabe des nächsten Threads, auf den Benutzer Modus Planer nicht vom Betriebssystem ausgeführt. Um den gewünschten Effekt der Wechsel zu einem anderen bereiten Thread im System zu erzielen, verwenden `YieldToSystem`.  
  
 `YieldToSystem` muss für die `IThreadProxy`-Schnittstelle aufgerufen werden, die den gerade ausgeführten Thread darstellt, oder die Ergebnisse sind nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IExecutionContext-Struktur](iexecutioncontext-structure.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)
