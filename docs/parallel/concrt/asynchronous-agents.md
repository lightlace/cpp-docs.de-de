---
title: Asynchrone Agents | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c4ce3240041987a79657c7e8bf296f9e89acb7a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asynchronous-agents"></a>Asynchrone Agents
Ein *asynchronen Agents* (oder einfach *Agent*) ist eine Anwendungskomponente, die asynchron mit anderen Agents, um größere Rechenaufgaben zu lösen. Denken Sie als eine Aufgabe, die einen festgelegten Lebenszyklus eines Agents. Ein Agent kann beispielsweise lesen, Daten aus einer Eingabe-/Ausgabegerät (z. B. der Tastatur, eine Datei auf dem Datenträger oder eine Netzwerkverbindung) und einen weiteren Agent Aktion für diese Daten ausführen können, sobald sie verfügbar sind. Der erste Agent verwendet Meldungsübergabe, um dem zweiten Agent zu informieren, dass mehr Daten verfügbar ist. Taskplaners der Concurrency Runtime stellt einen effizienten Mechanismus zum Aktivieren des Agents blockieren und Zurückhalten kooperativ ohne Unterbrechung weniger effizient.  
  

 Die Agents Library definiert die [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) -Klasse zur Darstellung eines asynchronen Agents. `agent`ist eine abstrakte Klasse, die die virtuelle Methode deklariert [Concurrency::agent::run](reference/agent-class.md#run). Die `run` -Methode führt die Aufgabe, die vom Agent ausgeführt wird. Da `run` ist abstrakt ist, müssen Sie diese Methode in jeder Klasse, die Sie ableiten implementieren `agent`.  
  
## <a name="agent-life-cycle"></a>Lebenszyklus von Agents  
 Agents haben einen festgelegten Lebenszyklus. Die [concurrency::agent_status](reference/concurrency-namespace-enums.md#agent_status) Enumeration definiert die verschiedenen Zustände eines Agents. Die folgende Abbildung ist ein Zustandsdiagramm, das zeigt, wie Agents von einem Zustand in einen anderen Status. In dieser Abbildung darstellen durchgezogene Linien Methoden, die von Ihrer Anwendung aufgerufen werden; gepunktete Linien stellen die Methoden, die von der Laufzeit aufgerufen werden.  
  
 ![Agent-Zustandsdiagramm] (../../parallel/concrt/media/agentstate.png " /var /")  
  
 Die folgende Tabelle beschreibt die einzelnen Status in der `agent_status` Enumeration.  
  
|Agent-Status|Beschreibung|  
|-----------------|-----------------|  
|`agent_created`|Der Agent wurde nicht für die Ausführung geplant.|  
|`agent_runnable`|Die Common Language Runtime ist die Planung des Agents für die Ausführung.|  
|`agent_started`|Der Agent wurde gestartet und ausgeführt wird.|  
|`agent_done`|Der Agent wurde abgeschlossen.|  
|`agent_canceled`|Der Agent wurde abgebrochen, bevor er eingegeben der `started` Zustand.|  
  
 `agent_created`ist der Anfangszustand eines Agents `agent_runnable` und `agent_started` sind die aktiven Zustände und `agent_done` und `agent_canceled` werden die Terminaldienste-Status.  
  
 Verwenden der [Concurrency::agent::status](reference/agent-class.md#status) Methode zum Abrufen des aktuellen Status einer `agent` Objekt. Obwohl die `status` Methode ist nebenläufigkeitssicher, der Status des Agents kann ändern, indem Sie die Zeit der `status` -Methode zurückkehrt. Ein Agent kann beispielsweise der `agent_started` Zustand beim Aufrufen der `status` -Methode, jedoch verschoben, um die `agent_done` direkt nach Status der `status` -Methode zurückkehrt.  

  
## <a name="methods-and-features"></a>Methoden und Funktionen  
 Die folgende Tabelle zeigt einige der wichtigen Methoden, die zu gehören die `agent` Klasse. Weitere Informationen zu allen dem `agent` -Klassenmethoden, finden Sie unter [Agent-Klasse](../../parallel/concrt/reference/agent-class.md).  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[start](reference/agent-class.md#start)|Zeitpläne der `agent` Objekt für die Ausführung und legt es auf die `agent_runnable` Zustand.|  
|[run](reference/agent-class.md#run)|Führt die Aufgabe, die von ausgeführt werden soll aus der `agent` Objekt.|  
|[Fertig](reference/agent-class.md#done)|Verschiebt einen Agent für die die `agent_done` Zustand.|  
|[Abbrechen](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|Wenn der Agent nicht gestartet wurde, wird diese Methode bricht die Ausführung des Agents ab und legt es auf die `agent_canceled` Zustand.|  
|[status](reference/agent-class.md#status)|Ruft den aktuellen Zustand der `agent` Objekt.|  
|[Warte](reference/agent-class.md#wait)|Wartet, bis die `agent` -Objekt, geben die `agent_done` oder `agent_canceled` Zustand.|  
|[wait_for_all](reference/agent-class.md#wait_for_all)|Wartet, bis alle bereitgestellten `agent` Objekte zur Eingabe der `agent_done` oder `agent_canceled` Zustand.|  
|[wait_for_one](reference/agent-class.md#wait_for_one)|Wartet, bis mindestens eines der bereitgestellten `agent` Objekte zur Eingabe der `agent_done` oder `agent_canceled` Zustand.|  
  
 Nachdem Sie ein Agent-Objekt erstellt haben, rufen Sie die [Verwaltungsroutinen](reference/agent-class.md#start) Methode, um ihn für die Ausführung planen. Ruft die Laufzeit die `run` -Methode auf, nachdem er die Agents plant und legt es auf die `agent_runnable` Zustand.  
  
 Die Common Language Runtime verwaltet keine Ausnahmen, die von asynchronen Agents ausgelöst werden. Weitere Informationen zur Behandlung von Ausnahmen und Agents finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel, das zum Erstellen einer einfachen agentbasierten Anwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)

