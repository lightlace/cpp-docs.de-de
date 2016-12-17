---
title: "Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert."
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "shoag"
manager: "wpickett"
---
# Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.
Es wurde versucht, einen Eintrag in ein Ereignisprotokoll schreiben, bei dem die angegebene Quelle für ein anderes Ereignisprotokoll registriert ist.  
  
 Sie müssen die <xref:System.Diagnostics.EventLog.Source*>\-Eigenschaft Ihrer <xref:System.Diagnostics.EventLog>\-Komponenteninstanz festlegen, bevor die Komponente einen Eintrag in ein Protokoll schreibt. In diesem Fall überprüft das System, ob die angegebene Quelle mit dem Ereignisprotokoll registriert ist, in das die Komponente schreibt. Bei Bedarf wird dann <xref:System.Diagnostics.EventLog.CreateEventSource*> aufgerufen.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die Zuordnung der Quelle zum ersten Protokoll mithilfe der <xref:System.Diagnostics.EventLog.DeleteEventSource*>\- oder <xref:System.Diagnostics.EventLog.DeleteEventSource*>\-Methode.  
  
2.  Registrieren Sie die Quelle für das neue Protokoll.  
  
## Siehe auch  
 [My.Application.Log\-Objekt](../Topic/My.Application.Log%20Object.md)   
 [How to: Remove an Event Source](assetId:///bc66c900-4b8a-426a-b8e2-17031a20167e)   
 [How to: Add Your Application as a Source of Event Log Entries](assetId:///948ff920-a739-4e66-a191-ee951512d42c)