---
title: IThreadProxy-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IThreadProxy
dev_langs:
- C++
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: 21
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: baa3266d1068672df96595fa8b9bcc974d52e7fa
ms.lasthandoff: 02/24/2017

---
# <a name="ithreadproxy-structure"></a>IThreadProxy-Struktur
Eine Abstraktion für einen Thread der Ausführung. Abhängig von dem von Ihnen erstellten `SchedulerType`-Richtlinienschlüssel des Planers, gewährt der Ressourcen-Manager eine Threadproxy, der entweder von einem regulären Win32-Thread oder einem im Benutzermodus planbaren (UMS) Thread unterstützt wird. UMS-Threads werden auf 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IThreadProxy;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IThreadProxy:: GetID-Methode](#getid)|Gibt einen eindeutigen Bezeichner für den Threadproxy zurück.|  
|[IThreadProxy:: SwitchOut-Methode](#switchout)|Hebt die Zuordnung des Kontexts vom zugrunde liegenden virtuellen Prozessorstamm auf.|  
|[IThreadProxy:: SwitchTo-Methode](#switchto)|Führt einen kooperativen Kontextwechsel vom derzeit ausgeführten Kontext zu einer anderen.|  
|[IThreadProxy:: YieldToSystem-Methode](#yieldtosystem)|Bewirkt, dass der aufrufende Thread die Ausführung an einen anderen Thread übergibt, der auf dem aktuellen Prozessor ausgeführt werden kann. Das Betriebssystem wählt den nächsten Thread ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Threadproxys werden mit Ausführungskontexten verbunden, dargestellt durch die Schnittstelle `IExecutionContext` als Mittel zur Arbeit verteilt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IThreadProxy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namegetida--ithreadproxygetid-method"></a><a name="getid"></a>IThreadProxy:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den Threadproxy zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine eindeutige ganzzahlige Bezeichner.  
  
##  <a name="a-nameswitchouta--ithreadproxyswitchout-method"></a><a name="switchout"></a>IThreadProxy:: SwitchOut-Methode  
 Hebt die Zuordnung des Kontexts vom zugrunde liegenden virtuellen Prozessorstamm auf.  
  
```
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `switchState`  
 Gibt den Zustand des Threadproxys an, der den Wechsel ausführt. Der Parameter ist vom Typ `SwitchingProxyState`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie `SwitchOut`, wenn Sie aus irgendeinem Grund die Zuordnung eines Kontexts zu einem virtuellen Prozessorstamm aufheben müssen, in dem dieser ausgeführt wird. Je nachdem, welchen Wert Sie an den `switchState`-Parameter übergeben, und abhängig von dessen Ausführung auf einem virtuellen Prozessorstamm, wird der Aufruf entweder sofort zurückgegeben oder der dem Kontext zugeordnete Threadproxy wird blockiert. Es ist nicht zulässig, `SwitchOut` aufzurufen, wenn der Parameter auf `Idle` festgelegt ist. Dies führt zu einer [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme.  
  
 `SwitchOut` ist nützlich, wenn Sie die Anzahl der Stämme virtueller Prozessoren für den Planer verringern möchten, da der Ressourcen-Manager Sie angewiesen hat, dies zu tun oder Sie den Stamm eines überzeichneten temporären virtuellen Prozessors angefordert haben und diesen nicht mehr benötigen. In diesem Fall sollten Sie die Methode aufrufen [IVirtualProcessorRoot::Remove Methode](http://msdn.microsoft.com/en-us/ad699b4a-1972-4390-97ee-9c083ba7d9e4) auf dem virtuellen Prozessorstamm vor einem Aufruf von `SwitchOut` mit dem Parameter `switchState` festgelegt `Blocking`. Auf diese Weise wird der Threadproxy blockiert. Die Ausführung wird fortgesetzt, wenn im Planer ein anderer virtueller Prozessorstamm für die Ausführung verfügbar ist. Die Ausführung des blockierten Threadproxys kann fortgesetzt werden, indem die `SwitchTo`-Funktion aufgerufen wird, um zum Ausführungskontext dieses Threadproxys zu wechseln. Sie können den Threadproxy auch fortsetzen, indem Sie dessen zugeordneten Kontext verwenden, um den Stamm eines virtuellen Prozessors zu aktivieren. Weitere Informationen hierzu finden Sie unter [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate).  
  
 Sie können `SwitchOut` zudem verwenden, um den virtuellen Prozessor erneut zu initialisieren, damit dieser zukünftig aktiviert werden kann, wenn Sie den Threadproxy blockieren oder vorübergehend vom Stamm des virtuellen Prozessors, für den dieser ausgeführt wird, und vom Planer, für den er Arbeit verteilt, trennen möchten. Verwenden Sie `SwitchOut` mit dem auf `switchState` festgelegten `Blocking`-Parameter, wenn Sie den Threadproxy blockieren möchten. Wie oben beschrieben, kann er zu einem späteren Zeitpunkt mithilfe von `SwitchTo` oder `IVirtualProcessorRoot::Activate` fortgesetzt werden. Verwenden Sie `SwitchOut` mit dem auf `Nesting` festgelegten Parameter, wenn Sie diesen Threadproxy vorübergehend vom Stamm des virtuellen Prozessors, auf dem er ausgeführt wird, und vom Planer, dem der virtuelle Prozessor zugeordnet ist, trennen möchten. Das Aufrufen von `SwitchOut` mit dem auf `switchState` festgelegten `Nesting`-Parameter führt während dessen Ausführung auf einem virtuellen Prozessorstamm zu einer erneuten Initialisierung des Stamms und zur Fortsetzung des aktuellen Threadproxys, obwohl dieser nicht erforderlich ist. Der Threadproxy den Planer verlassen hat, bis er aufruft der [IThreadProxy:: SwitchOut](#switchout) -Methode mit `Blocking` zu einem späteren Zeitpunkt. Der zweite Aufruf von `SwitchOut` mit dem auf `Blocking` festgelegten Parameter soll den Kontext in einen blockierten Zustand zurückversetzen, damit er im Planer, von dem er getrennt ist, mit `SwitchTo` oder `IVirtualProcessorRoot::Activate` fortgesetzt werden kann. Da die Ausführung nicht auf einem virtuellen Prozessorstamm erfolgt, findet keine erneute Initialisierung statt.  
  
 Ein erneut initialisierter virtueller Prozessorstamm unterscheidet sich nicht von einem neuen virtuellen Prozessorstamm, der dem Planer vom Ressourcen-Manager gewährt wurde. Sie können ihn für die Ausführung verwenden, indem Sie ihn mit `IVirtualProcessorRoot::Activate` in einem Ausführungskontext aktivieren.  
  
 `SwitchOut` muss für die `IThreadProxy`-Schnittstelle aufgerufen werden, die den gerade ausgeführten Thread darstellt, oder die Ergebnisse sind nicht definiert.  
  
 In den Bibliotheken und Headern, die mit Visual Studio 2010 geliefert wurden, weist diese Methode keinen Parameter auf, und der virtuelle Prozessorstamm wurde nicht initialisiert. Um altes Verhalten beizubehalten, wird der Standardparameterwert von `Blocking` angegeben.  
  
##  <a name="a-nameswitchtoa--ithreadproxyswitchto-method"></a><a name="switchto"></a>IThreadProxy:: SwitchTo-Methode  
 Führt einen kooperativen Kontextwechsel vom derzeit ausgeführten Kontext zu einer anderen.  
  
```
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Ausführungskontext kooperativ gewechselt werden soll.  
  
 `switchState`  
 Gibt den Zustand des Threadproxys an, der den Wechsel ausführt. Der Parameter ist vom Typ `SwitchingProxyState`.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können aus einem Ausführungskontext zur anderen wechseln, aus der [IExecutionContext:: Dispatch](iexecutioncontext-structure.md#dispatch) -Methode des ersten Ausführungskontexts. Die Methode ordnet den Ausführungskontext `pContext` einem Threadproxy, wenn er nicht bereits zugeordnet ist. Der Besitz des aktuellen Threadproxys wird bestimmt durch den Wert aus, Sie für geben, die `switchState` Argument.  
  
 Verwenden Sie den Wert `Idle` bei den derzeit ausgeführte Threadproxy zum Ressourcen-Manager zurückgegeben werden soll. Aufrufen von `SwitchTo` mit dem Parameter `switchState` festgelegt `Idle` bewirkt, dass den Ausführungskontext `pContext` Ausführung in der zugrunde liegenden Ausführungsressource. Der Ressourcen-Manager wird der Besitz an diesem Threadproxy übergeben, und es wird erwartet, um des Ausführungskontexts zurückzugeben `Dispatch` Methode kurz nach `SwitchTo` zurückgegeben wird, um die Übertragung abzuschließen. Der Ausführungskontext, den den Threadproxy weitergeleitet hat wird der Threadproxy aufgehoben, und der Planer kann erneut verwendet oder zerstören Ermessen.  
  
 Verwenden Sie den Wert `Blocking` soll dieser Threadproxy in einen blockierten Zustand übergeht. Aufrufen von `SwitchTo` mit dem Parameter `switchState` festgelegt `Blocking` bewirkt, dass den Ausführungskontext `pContext` ausführen und den aktuellen Threadproxy blockiert, bis er fortgesetzt wird. Der Planer behält den Besitz des Threadproxys an, wenn der Threadproxy ist der `Blocking` Zustand. Die Ausführung des blockierten Threadproxys kann fortgesetzt werden, indem die `SwitchTo`-Funktion aufgerufen wird, um zum Ausführungskontext dieses Threadproxys zu wechseln. Sie können den Threadproxy auch fortsetzen, indem Sie dessen zugeordneten Kontext verwenden, um den Stamm eines virtuellen Prozessors zu aktivieren. Weitere Informationen hierzu finden Sie unter [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate).  
  
 Verwenden Sie den Wert `Nesting` Wenn Sie vorübergehend diesen Threadproxy vom Stamm virtuellen Prozessors Trennen dieser ausgeführt wird, und der Planer er Arbeit verteilt. Aufrufen von `SwitchTo` mit dem Parameter `switchState` festgelegt `Nesting` bewirkt, dass den Ausführungskontext `pContext` starten ausführen und die aktuelle Threadproxy ebenfalls weiter ausgeführt wird, ohne dass ein virtueller Prozessorstamm. Der Threadproxy den Planer verlassen hat, bis er aufruft der [IThreadProxy:: SwitchOut](#switchout) Methode zu einem späteren Zeitpunkt. Die `IThreadProxy::SwitchOut` Methode konnte der Threadproxy blockiert, bis ein virtueller Prozessorstamm ist, um neu zu planen.  
  
 `SwitchTo` muss für die `IThreadProxy`-Schnittstelle aufgerufen werden, die den gerade ausgeführten Thread darstellt, oder die Ergebnisse sind nicht definiert. Löst die Funktion `invalid_argument` Wenn der Parameter `pContext` Wert `NULL`.  
  
##  <a name="a-nameyieldtosystema--ithreadproxyyieldtosystem-method"></a><a name="yieldtosystem"></a>IThreadProxy:: YieldToSystem-Methode  
 Bewirkt, dass der aufrufende Thread die Ausführung an einen anderen Thread übergibt, der auf dem aktuellen Prozessor ausgeführt werden kann. Das Betriebssystem wählt den nächsten Thread ausgeführt werden.  
  
```
virtual void YieldToSystem() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufruf durch einen Threadproxy, der von einem regulären Windows-Thread `YieldToSystem` verhält sich genau wie die Windows-Funktion `SwitchToThread`. Jedoch, die beim Aufruf von im Benutzermodus planbare (UMS) Threads, die `SwitchToThread` Funktion delegiert die Aufgabe des nächsten Threads, auf den Benutzer-Modus-Planer, nicht vom Betriebssystem ausgeführt. Um den gewünschten Effekt der Wechsel zu einem anderen bereiten Thread im System zu erreichen, verwenden Sie `YieldToSystem`.  
  
 `YieldToSystem` muss für die `IThreadProxy`-Schnittstelle aufgerufen werden, die den gerade ausgeführten Thread darstellt, oder die Ergebnisse sind nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IExecutionContext-Struktur](iexecutioncontext-structure.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)

