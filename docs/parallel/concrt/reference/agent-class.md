---
title: "agent-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::agent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "agent-Klasse"
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# agent-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist als Basisklasse für alle unabhängigen Agents vorgesehen.  Sie wird verwendet, um den Zustand von anderen Agents auszublenden und mithilfe von Meldungsübergabe zu interagieren.  
  
## Syntax  
  
```  
class agent;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[agent::agent\-Konstruktor](../Topic/agent::agent%20Constructor.md)|Überladen.  Erstellt einen Agent.|  
|[agent::~agent\-Destruktor](../Topic/agent::~agent%20Destructor.md)|Zerstört den Agent.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[agent::cancel\-Methode](../Topic/agent::cancel%20Method.md)|Versetzt einen Agent aus dem Zustand `agent_created` oder `agent_runnable` in den Zustand `agent_canceled`.|  
|[agent::start\-Methode](../Topic/agent::start%20Method.md)|Versetzt einen Agent aus dem Zustand `agent_created` in den Zustand `agent_runnable` und plant die Ausführung des Agents.|  
|[agent::status\-Methode](../Topic/agent::status%20Method.md)|Eine synchrone Quelle der Statusinformationen vom Agent.|  
|[agent::status\_port\-Methode](../Topic/agent::status_port%20Method.md)|Eine asynchrone Quelle der Statusinformationen vom Agent.|  
|[agent::wait\-Methode](../Topic/agent::wait%20Method.md)|Wartet, bis ein Agent seine Aufgabe abgeschlossen hat.|  
|[agent::wait\_for\_all\-Methode](../Topic/agent::wait_for_all%20Method.md)|Wartet, bis alle angegebenen Agents die Ausführung ihrer Aufgaben abschließen.|  
|[agent::wait\_for\_one\-Methode](../Topic/agent::wait_for_one%20Method.md)|Wartet, bis einer der angegebenen Agents die Ausführung seiner Aufgabe abschließt.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[agent::done\-Methode](../Topic/agent::done%20Method.md)|Versetzt einen Agent in den `agent_done`\-Zustand und zeigt damit den Abschluss des Agents an.|  
|[agent::run\-Methode](../Topic/agent::run%20Method.md)|Stellt die Hauptaufgabe eines Agents dar.  `run` sollte in einer abgeleiteten Klasse überschrieben werden und gibt an, was der Agent machen soll, nachdem er gestartet wurde.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Agents](../../../parallel/concrt/asynchronous-agents.md).  
  
## Vererbungshierarchie  
 `agent`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)