---
title: "CAtlServiceModuleT::Handler Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule::Handler"
  - "CServiceModule.Handler"
  - "Handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Handler method"
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CAtlServiceModuleT::Handler Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CAtlServiceModuleT::Handler` ist die Routine, die der Dienststeuerungs\-Manager \(SCM\) aufgerufen wird, um den Status des Diensts abzurufen und zu geben ihm verschiedenen Anweisungen \(wie Beenden oder Anhalten\).  Das SCM führt einen Operationscode zu `Handler`, um festzulegen, wie der Dienst reagieren soll.  Ein Standard ATL\-generierter Dienst behandelt nur die Stopp\-Anweisung.  Wenn das SCM die Stopp\-Anweisung übergibt, wird der Dienst dem SCM mit, dass das Programm im Begriff ist beenden.  Der Dienst `PostThreadMessage` ruft dann auf, um eine fehlgeschlagene Meldung mit sich selbst zu senden.  Dies beendet die Meldungsschleife und der Dienst wird letztlich.  
  
 Um mehr Anweisungen zu behandeln, müssen Sie den `m_status` Datenmember ändern, der im `CAtlServiceModuleT`\-Konstruktor initialisiert wird.  Dieser Datenmember teilt dem SCM mit, welche Schaltflächen, zu aktivieren, wenn der Dienst in der Dienste\-Systemsteuerungs\-Anwendung ausgewählt ist.  
  
## Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../Topic/CAtlServiceModuleT::Handler.md)