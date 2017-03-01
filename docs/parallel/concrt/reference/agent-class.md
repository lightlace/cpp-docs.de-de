---
title: Agent-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::agent
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 640e1d66a879e8eb73428b50339d6a325cfd7cb2
ms.lasthandoff: 02/24/2017

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
|[Agent-Konstruktor](#ctor)|Überladen. Erstellt einen Agent.|  
|[~ Agent-Destruktor](#dtor)|Zerstört den Agent.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cancel-Methode](#cancel)|Versetzt einen Agent aus der `agent_created` oder `agent_runnable` Status der `agent_canceled` Zustand.|  
|[Start-Methode](#start)|Versetzt einen Agent aus der `agent_created` Zustand der `agent_runnable` Status, und plant die Ausführung.|  
|[Status-Methode](#status)|Eine synchrone Quelle der Statusinformationen vom Agent.|  
|[Status_port-Methode](#status_port)|Eine asynchrone Quelle der Statusinformationen vom Agent.|  
|[Wait-Methode](#wait)|Wartet, bis ein Agent seine Aufgabe abgeschlossen.|  
|[Wait_for_all-Methode](#wait_for_all)|Wartet, bis alle angegebenen Agents, ihre Aufgaben auszuführen.|  
|[Wait_for_one-Methode](#wait_for_one)|Wartet auf eine der angegebenen Agents seine Aufgabe abgeschlossen.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Done-Methode](#done)|Versetzt einen Agent in der `agent_done` Zustand, der angibt, dass der Agent abgeschlossen wurde.|  
|[Run-Methode](#run)|Stellt die Hauptaufgabe eines Agents dar. `run`in einer abgeleiteten Klasse überschrieben werden soll, und gibt an, was der Agent machen soll, nachdem es gestartet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Agents](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `agent`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-agent"></a><a name="ctor"></a>Agent 

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
  
##  <a name="a-namedtora-agent"></a><a name="dtor"></a>~ Agent 

 Zerstört den Agent.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist ein Fehler, einen Agent zu zerstören, die nicht in einem Endzustand ist (entweder `agent_done` oder `agent_canceled`). Dies kann vermieden werden, warten Sie, bis des Agents einen Endzustand im Destruktor einer Klasse erreicht, die von erbt die `agent` Klasse.  
  
##  <a name="a-namecancela-cancel"></a><a name="cancel"></a>Abbrechen 

 Versetzt einen Agent aus der `agent_created` oder `agent_runnable` Status der `agent_canceled` Zustand.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Agent abgebrochen wurde, `false` andernfalls. Ein Agent kann nicht abgebrochen werden, wenn er bereits gestartet oder abgeschlossen wurde.  
  
##  <a name="a-namedonea-done"></a><a name="done"></a>Fertig 

 Versetzt einen Agent in der `agent_done` Zustand, der angibt, dass der Agent abgeschlossen wurde.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Agent auf den `agent_done` Zustand `false` andernfalls. Ein Agent, der abgebrochen wurde nicht verschoben werden, um die `agent_done` Zustand.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte aufgerufen werden, am Ende der `run` Methode, wenn Sie wissen, dass die Ausführung des Agents abgeschlossen wurde.  
  
##  <a name="a-nameruna-run"></a><a name="run"></a>Ausführen 

 Stellt die Hauptaufgabe eines Agents dar. `run`in einer abgeleiteten Klasse überschrieben werden soll, und gibt an, was der Agent machen soll, nachdem es gestartet wurde.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Agent-Status wird geändert, um `agent_started` unmittelbar bevor diese Methode aufgerufen wird. Aufrufen der Methode sollte `done` für den Agent mit einem entsprechenden Status vor dem zurückgeben, und kann keine Ausnahmen auslösen.  
  
##  <a name="a-namestarta-start"></a><a name="start"></a>Starten 

 Versetzt einen Agent aus der `agent_created` Zustand der `agent_runnable` Status, und plant die Ausführung.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Agent ordnungsgemäß gestartet `false` andernfalls. Ein Agent, der abgebrochen wurde, kann nicht gestartet werden.  
  
##  <a name="a-namestatusa-status"></a><a name="status"></a>Status 

 Eine synchrone Quelle der Statusinformationen vom Agent.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Zustand des Agents zurück. Beachten Sie, dass dieser zurückgegebene Zustand sofort nach zurückgegeben werden konnte.  
  
##  <a name="a-namestatusporta-statusport"></a><a name="status_port"></a>status_port 

 Eine asynchrone Quelle der Statusinformationen vom Agent.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Nachrichtenquelle, die Nachrichten über den aktuellen Zustand des Agents senden kann.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Warte 

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
  
##  <a name="a-namewaitforalla-waitforall"></a><a name="wait_for_all"></a>wait_for_all 

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
  
##  <a name="a-namewaitforonea-waitforone"></a><a name="wait_for_one"></a>wait_for_one 

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

