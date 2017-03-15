---
title: "Asynchrone Agents | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Agents [Concurrency Runtime]"
  - "Asynchrone Agents"
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Asynchrone Agents
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein *asynchroner Agent* \(oder einfach *Agent*\) ist eine Anwendungskomponente, die asynchron mit anderen Agents arbeitet, um größere Rechenaufgaben zu lösen.  Sie können sich einen Agent als eine Aufgabe mit einem festgelegten Lebenszyklus vorstellen.  So kann beispielsweise ein Agent Daten von einem Ein\-\/Ausgabegerät \(wie etwa von der Tastatur, aus einer Datei auf einem Datenträger oder über eine Netzwerkverbindung\) lesen, während ein anderer Agent für diese Daten eine Aktion ausführt, sobald diese Daten verfügbar werden.  Der erste Agent informiert den zweiten Agent mithilfe der Nachrichtenübergabe darüber, dass weitere Daten verfügbar sind.  Der Concurrency Runtime\-Taskplaner stellt einen effizienten Mechanismus bereit, mit dem Agents gemeinsam blockieren und erzeugen können, ohne dass eine weniger effiziente vorzeitige Entfernung erforderlich ist.  
  
 Die Agents Library definiert die [concurrency::agent](../../parallel/concrt/reference/agent-class.md)\-Klasse, um einen asynchronen Agents.  `agent` ist eine abstrakte Klasse, die die virtuelle Methode [concurrency::agent::run](../Topic/agent::run%20Method.md) deklariert.  Die `run`\-Methode führt die Aufgabe aus, die vom Agent durchgeführt wird.  Da `run` abstrakt ist, müssen Sie diese Methode in jeder Klasse implementieren, die von `agent` abgeleitet wird.  
  
## Lebenszyklus von Agents  
 Agents haben einen festgelegten Lebenszyklus.  Die [concurrency::agent\_status](../Topic/agent_status%20Enumeration.md)\-Enumeration definiert die verschiedenen Zustände eines Agents.  Die folgende Abbildung ist ein Zustandsdiagramm, das zeigt, wie Agents von einem Zustand in einen anderen übergehen.  In dieser Abbildung stellen durchgezogene Linien Methoden dar, die Sie in der Anwendung aufrufen, während gepunktete Linien Methoden darstellen, die von der Runtime aufgerufen werden.  
  
 ![Agent&#45;Zustandsdiagramm](../../parallel/concrt/media/agentstate.png "AgentState")  
  
 In der folgenden Tabelle werden die einzelnen Zustände der `agent_status`\-Enumeration beschrieben.  
  
|Agent\-Zustand|**Beschreibung**|  
|--------------------|----------------------|  
|`agent_created`|Der Agent wurde nicht für die Ausführung geplant.|  
|`agent_runnable`|Die Runtime plant den Agent für die Ausführung.|  
|`agent_started`|Der Agent wurde gestartet und wird ausgeführt.|  
|`agent_done`|Der Agent wurde beendet.|  
|`agent_canceled`|Der Agent wurde abgebrochen, bevor er in den `started`\-Zustand übergegangen ist.|  
  
 `agent_created` ist der Anfangszustand eines Agents, `agent_runnable` und `agent_started` sind die aktiven Zustände und `agent_done` und `agent_canceled` sind die Endzustände.  
  
 Verwenden Sie die Methode [concurrency::agent::status](../Topic/agent::status%20Method.md), um den aktuellen Zustand eines `agent`\-Objekts abzurufen.  Obwohl die `status`\-Methode parallelitätssicher ist, kann sich der Zustand des Agents bis zu dem Zeitpunkt ändern, zu dem die `status`\-Methode zurückkehrt.  Ein Agent kann sich beispielsweise im `agent_started`\-Zustand befinden, wenn Sie die `status`\-Methode aufrufen, aber kurz nachdem die `status`\-Methode zurückkehrt, in den `agent_done`\-Zustand übergehen.  
  
## Methoden und Funktionen  
 In der folgenden Tabelle sind einige der wichtigen Methoden aufgeführt, die zur `agent`\-Klasse gehören.  Weitere Informationen zu allen `agent`\-Klassenmethoden finden Sie unter [agent\-Klasse](../../parallel/concrt/reference/agent-class.md).  
  
|Methode|**Beschreibung**|  
|-------------|----------------------|  
|[start](../Topic/agent::start%20Method.md)|Plant das `agent`\-Objekt für die Ausführung und legt für das Objekt den `agent_runnable`\-Zustand fest.|  
|[run](../Topic/agent::run%20Method.md)|Führt die Aufgabe aus, die vom `agent`\-Objekt ausgeführt werden soll.|  
|[dein](../Topic/agent::done%20Method.md)|Versetzt einen Agent in den `agent_done`\-Zustand.|  
|[cancel](../Topic/agent::cancel%20Method.md)|Wenn der Agent nicht gestartet wurde, bricht diese Methode die Ausführung des Agents ab und legt für den Agent den `agent_canceled`\-Zustand fest.|  
|[status](../Topic/agent::status%20Method.md)|Ruft den aktuellen Zustand des `agent`\-Objekts ab.|  
|[wait](../Topic/agent::wait%20Method.md)|Wartet, bis das `agent`\-Objekt in den `agent_done`\-Zustand oder in den `agent_canceled`\-Zustand übergegangen ist.|  
|[wait\_for\_all](../Topic/agent::wait_for_all%20Method.md)|Wartet, bis alle bereitgestellten `agent`\-Objekte in den `agent_done`\-Zustand oder in den `agent_canceled`\-Zustand übergegangen sind.|  
|[wait\_for\_one](../Topic/agent::wait_for_one%20Method.md)|Wartet, bis mindestens eines der bereitgestellten `agent`\-Objekte in den `agent_done`\-Zustand oder in den `agent_canceled`\-Zustand übergegangen ist.|  
  
 Nachdem Sie ein agent\-Objekt erstellt haben, rufen Sie die [concurrency::agent::start](../Topic/agent::start%20Method.md)\-Methode auf, um sie für die Ausführung zu planen.  Die Runtime ruft die `run`\-Methode nach der Planung des Agents auf und legt für die Methode den `agent_runnable`\-Zustand fest.  
  
 Die Runtime verwaltet keine Ausnahmen, die von asynchronen Agents ausgelöst werden.  Weitere Informationen zur Behandlung von Ausnahmen und Agents finden Sie unter [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## Beispiel  
 Ein Beispiel für die Erstellung einer einfachen agentbasierten Anwendung finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer agentbasierten Anwendung](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md).  
  
## Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)