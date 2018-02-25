---
title: Agent-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4617007525fdd924dce7b09f1d351c7c18cc96
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="agent-class"></a>agent-Klasse
Diese Klasse ist als Basisklasse für alle unabhängigen Agents vorgesehen. Sie wird verwendet, um den Zustand von anderen Agents auszublenden und mithilfe von Meldungsübergabe zu interagieren.  
  
## <a name="syntax"></a>Syntax  
  
```
class agent;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[agent](#ctor)|Überladen. Erstellt einen Agent an.|  
|[~ Agent-Destruktor](#dtor)|Zerstört den Agent.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[cancel](#cancel)|Verschiebt einen Agent von entweder der `agent_created` oder `agent_runnable` Status der `agent_canceled` Zustand.|  
|[start](#start)|Verschiebt einen Agent von der `agent_created` Zustands, in der `agent_runnable` Zustand, und plant die Ausführung.|  
|[Status](#status)|Eine synchrone Informationsquelle Status des Agents.|  
|[status_port](#status_port)|Eine asynchrone Datenquelle Statusinformationen vom Agent.|  
|[wait](#wait)|Für einen Agent zum Abschließen des Tasks wartet.|  
|[wait_for_all](#wait_for_all)|Wartet, bis alle angegebenen Agents, um ihre Tasks auszuführen.|  
|[wait_for_one](#wait_for_one)|Wartet auf eine der angegebenen Agents Abschließen des Tasks.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[done](#done)|Verschiebt einen Agent in der `agent_done` Zustand, der angibt, dass der Agent abgeschlossen wurde.|  
|[run](#run)|Stellt die Hauptaufgabe eines Agents dar. `run` in einer abgeleiteten Klasse überschrieben werden soll, und gibt an, welche Aktion der Agent ausführen soll, nachdem es gestartet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Agents](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `agent`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> Agent 

 Erstellt einen Agent an.  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `_PScheduler`  
 Die `Scheduler` Objekt, in dem der ausführungstask des Agents geplant ist.  
  
 `_PGroup`  
 Die `ScheduleGroup` Objekt, in dem der ausführungstask des Agents geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
### <a name="remarks"></a>Hinweise  
 Die Laufzeit mithilfe des Standardplaners aus, wenn Sie keinen angeben der `_PScheduler` oder `_PGroup` Parameter.  
  
##  <a name="dtor"></a> ~ Agent 

 Zerstört den Agent.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist ein Fehler auf einen Agent zu zerstören, die nicht in ein Endzustand ist (entweder `agent_done` oder `agent_canceled`). Dies kann vermieden werden, warten Sie, bis des Agents einen Endzustand im Destruktor einer Klasse erreicht, die von erben die `agent` Klasse.  
  
##  <a name="cancel"></a> Abbrechen 

 Verschiebt einen Agent von entweder der `agent_created` oder `agent_runnable` Status der `agent_canceled` Zustand.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der Agent abgebrochen wurde, `false` andernfalls. Ein Agent kann nicht abgebrochen werden, wenn er bereits gestartet oder bereits abgeschlossen wurde.  
  
##  <a name="done"></a> Fertig 

 Verschiebt einen Agent in der `agent_done` Zustand, der angibt, dass der Agent abgeschlossen wurde.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der Agent, um verschoben wird die `agent_done` Zustand `false` andernfalls. Ein Agent, der abgebrochen wurde kann nicht verschoben werden, um die `agent_done` Zustand.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte aufgerufen werden, am Ende der `run` Methode, wenn Sie wissen, dass die Ausführung des Agents abgeschlossen wurde.  
  
##  <a name="run"></a> Führen Sie 

 Stellt die Hauptaufgabe eines Agents dar. `run` in einer abgeleiteten Klasse überschrieben werden soll, und gibt an, welche Aktion der Agent ausführen soll, nachdem es gestartet wurde.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Agent-Status wird geändert, um `agent_started` mit der rechten Maustaste, bevor diese Methode aufgerufen wird. Aufrufen der Methode sollte `done` für den Agent mit einem entsprechenden Status vor der Rückgabe, und kann keine Ausnahmen auslösen.  
  
##  <a name="start"></a> Starten 

 Verschiebt einen Agent von der `agent_created` Zustands, in der `agent_runnable` Zustand, und plant die Ausführung.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der Agent ordnungsgemäß gestartet `false` andernfalls. Ein Agent, der abgebrochen wurde, kann nicht gestartet werden.  
  
##  <a name="status"></a> status 

 Eine synchrone Informationsquelle Status des Agents.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Status des Agents zurück. Beachten Sie, dass dieser zurückgegebene Status ändern könnte, sofort nach dem zurückgegeben wird.  
  
##  <a name="status_port"></a> status_port 

 Eine asynchrone Datenquelle Statusinformationen vom Agent.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Nachrichtenquelle, die Nachrichten über den aktuellen Status des Agents senden kann.  
  
##  <a name="wait"></a> Warte 

 Für einen Agent zum Abschließen des Tasks wartet.  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `_PAgent`  
 Ein Zeiger auf den Agent gewartet werden soll.  
  
 `_Timeout`  
 Die maximale Zeit für die Wartezeit in Millisekunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `agent_status` des Agents des Wartevorgangs. Dies kann entweder `agent_canceled` oder `agent_done`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Agent-Task abgeschlossen ist, wenn der Agent die `agent_canceled` oder `agent_done` Status.  
  
 Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor der Agent seine Aufgabe abgeschlossen ist.  
  
##  <a name="wait_for_all"></a> wait_for_all 

 Wartet, bis alle angegebenen Agents, um ihre Tasks auszuführen.  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `count`  
 Die Anzahl von Agent-Zeigern, die im Array vorhanden `_PAgents`.  
  
 `_PAgents`  
 Ein Array von Zeigern auf die Agents gewartet werden soll.  
  
 `_PStatus`  
 Ein Zeiger auf ein Array von Agent-Status. Jeder Statuswert repräsentiert den Status des entsprechenden Agents beim Beenden der Methode.  
  
 `_Timeout`  
 Die maximale Zeit für die Wartezeit in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Ein Agent-Task abgeschlossen ist, wenn der Agent die `agent_canceled` oder `agent_done` Status.  
  
 Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor der Agent seine Aufgabe abgeschlossen ist.  
  
##  <a name="wait_for_one"></a> wait_for_one 

 Wartet auf eine der angegebenen Agents Abschließen des Tasks.  
  
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
 Die Anzahl von Agent-Zeigern, die im Array vorhanden `_PAgents`.  
  
 `_PAgents`  
 Ein Array von Zeigern auf die Agents gewartet werden soll.  
  
 `_Status`  
 Ein Verweis auf eine Variable, in dem der Agent-Status platziert werden.  
  
 `_Index`  
 Ein Verweis auf eine Variable, in dem der Agent-Index platziert werden.  
  
 `_Timeout`  
 Die maximale Zeit für die Wartezeit in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Ein Agent-Task abgeschlossen ist, wenn der Agent die `agent_canceled` oder `agent_done` Status.  
  
 Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor der Agent seine Aufgabe abgeschlossen ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
