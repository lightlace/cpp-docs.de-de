---
title: Agent-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 1e6e23e742137bffd9035ecf69ecc32d199ca0c5
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="agent-class"></a>agent-Klasse
Diese Klasse ist als Basisklasse für alle unabhängigen Agents vorgesehen. Sie wird verwendet, um den Zustand von anderen Agents auszublenden und mithilfe von Meldungsübergabe zu interagieren.  
  
## <a name="syntax"></a>Syntax  
  
```
class agent;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Agent](#ctor)|Überladen. Erstellt einen Agent.|  
|[~ Agent-Destruktor](#dtor)|Zerstört den Agent.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Abbrechen](#cancel)|Versetzt einen Agent aus der `agent_created` oder `agent_runnable` Status der `agent_canceled` Zustand.|  
|[start](#start)|Versetzt einen Agent aus der `agent_created` Zustand der `agent_runnable` Status, und plant die Ausführung.|  
|[status](#status)|Eine synchrone Quelle der Statusinformationen vom Agent.|  
|[status_port](#status_port)|Eine asynchrone Quelle der Statusinformationen vom Agent.|  
|[Warte](#wait)|Wartet, bis ein Agent seine Aufgabe abgeschlossen.|  
|[wait_for_all](#wait_for_all)|Wartet, bis alle angegebenen Agents, ihre Aufgaben auszuführen.|  
|[wait_for_one](#wait_for_one)|Wartet auf eine der angegebenen Agents seine Aufgabe abgeschlossen.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Fertig](#done)|Versetzt einen Agent in der `agent_done` Zustand, der angibt, dass der Agent abgeschlossen wurde.|  
|[run](#run)|Stellt die Hauptaufgabe eines Agents dar. `run`in einer abgeleiteten Klasse überschrieben werden soll, und gibt an, was der Agent machen soll, nachdem es gestartet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Agents](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `agent`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>Agent 

 Erstellt einen Agent.  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `_PScheduler`  
 Die `Scheduler` in der Ausführung des Agents geplanten-Objekt.  
  
 `_PGroup`  
 Die `ScheduleGroup` in der Ausführung des Agents geplanten-Objekt. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
### <a name="remarks"></a>Hinweise  
 Die Laufzeit verwendet den Standardplaner, wenn Sie keinen angeben der `_PScheduler` oder `_PGroup` Parameter.  
  
##  <a name="dtor"></a>~ Agent 

 Zerstört den Agent.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist ein Fehler, einen Agent zu zerstören, die nicht in einem Endzustand ist (entweder `agent_done` oder `agent_canceled`). Dies kann vermieden werden, warten Sie, bis des Agents einen Endzustand im Destruktor einer Klasse erreicht, die von erbt die `agent` Klasse.  
  
##  <a name="cancel"></a>Abbrechen 

 Versetzt einen Agent aus der `agent_created` oder `agent_runnable` Status der `agent_canceled` Zustand.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Agent abgebrochen wurde, `false` andernfalls. Ein Agent kann nicht abgebrochen werden, wenn er bereits gestartet oder abgeschlossen wurde.  
  
##  <a name="done"></a>Fertig 

 Versetzt einen Agent in der `agent_done` Zustand, der angibt, dass der Agent abgeschlossen wurde.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Agent auf den `agent_done` Zustand `false` andernfalls. Ein Agent, der abgebrochen wurde nicht verschoben werden, um die `agent_done` Zustand.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte aufgerufen werden, am Ende der `run` Methode, wenn Sie wissen, dass die Ausführung des Agents abgeschlossen wurde.  
  
##  <a name="run"></a>Ausführen 

 Stellt die Hauptaufgabe eines Agents dar. `run`in einer abgeleiteten Klasse überschrieben werden soll, und gibt an, was der Agent machen soll, nachdem es gestartet wurde.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Agent-Status wird geändert, um `agent_started` unmittelbar bevor diese Methode aufgerufen wird. Aufrufen der Methode sollte `done` für den Agent mit einem entsprechenden Status vor dem zurückgeben, und kann keine Ausnahmen auslösen.  
  
##  <a name="start"></a>Starten 

 Versetzt einen Agent aus der `agent_created` Zustand der `agent_runnable` Status, und plant die Ausführung.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Agent ordnungsgemäß gestartet `false` andernfalls. Ein Agent, der abgebrochen wurde, kann nicht gestartet werden.  
  
##  <a name="status"></a>Status 

 Eine synchrone Quelle der Statusinformationen vom Agent.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Zustand des Agents zurück. Beachten Sie, dass dieser zurückgegebene Zustand sofort nach zurückgegeben werden konnte.  
  
##  <a name="status_port"></a>status_port 

 Eine asynchrone Quelle der Statusinformationen vom Agent.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Nachrichtenquelle, die Nachrichten über den aktuellen Zustand des Agents senden kann.  
  
##  <a name="wait"></a>Warte 

 Wartet, bis ein Agent seine Aufgabe abgeschlossen.  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `_PAgent`  
 Ein Zeiger auf den Agent zu warten.  
  
 `_Timeout`  
 Die maximale Zeit für die Wartezeit in Millisekunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `agent_status` des Agents des Wartevorgangs. Dies kann entweder `agent_canceled` oder `agent_done`.  
  
### <a name="remarks"></a>Hinweise  
 Eine Agent-Aufgabe ist abgeschlossen, wenn der Agent die `agent_canceled` oder `agent_done` Zustände.  
  
 Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, der die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor der Agent seine Aufgabe abgeschlossen hat.  
  
##  <a name="wait_for_all"></a>wait_for_all 

 Wartet, bis alle angegebenen Agents, ihre Aufgaben auszuführen.  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `count`  
 Die Anzahl der Agentzeiger im Array `_PAgents`.  
  
 `_PAgents`  
 Ein Array von Zeigern auf die Agents warten.  
  
 `_PStatus`  
 Ein Zeiger auf ein Array von Agent-Status. Jeder Statuswert wird beim Beenden die Methode den Status des zugehörigen Agents darstellen.  
  
 `_Timeout`  
 Die maximale Zeit für die Wartezeit in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Eine Agent-Aufgabe ist abgeschlossen, wenn der Agent die `agent_canceled` oder `agent_done` Zustände.  
  
 Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, der die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor der Agent seine Aufgabe abgeschlossen hat.  
  
##  <a name="wait_for_one"></a>wait_for_one 

 Wartet auf eine der angegebenen Agents seine Aufgabe abgeschlossen.  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `count`  
 Die Anzahl der Agentzeiger im Array `_PAgents`.  
  
 `_PAgents`  
 Ein Array von Zeigern auf die Agents warten.  
  
 `_Status`  
 Ein Verweis auf eine Variable, in dem der Status des Agents platziert werden.  
  
 `_Index`  
 Ein Verweis auf eine Variable, in dem der Agent-Index gespeichert wird.  
  
 `_Timeout`  
 Die maximale Zeit für die Wartezeit in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Eine Agent-Aufgabe ist abgeschlossen, wenn der Agent die `agent_canceled` oder `agent_done` Zustände.  
  
 Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, der die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor der Agent seine Aufgabe abgeschlossen hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

