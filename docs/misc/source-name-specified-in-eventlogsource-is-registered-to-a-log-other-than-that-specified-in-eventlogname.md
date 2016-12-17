---
title: "Der in &quot;EventLogSource&quot; angegebene Quellenname ist f&#252;r ein anderes als in &quot;EventLogName&quot; angegebenes Protokoll registriert"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Der in &quot;EventLogSource&quot; angegebene Quellenname ist f&#252;r ein anderes als in &quot;EventLogName&quot; angegebenes Protokoll registriert
`EventLog` versucht, auf eine Quelle zu verweisen, die für ein anderes Protokoll registriert ist. Wenn Sie Einträge in ein Ereignisprotokoll schreiben, müssen Sie die <xref:System.Diagnostics.EventLog.Source*>\-Eigenschaft angeben. Die <xref:System.Diagnostics.EventLog.Source*>\-Eigenschaft registriert die Komponente beim Ereignisprotokoll als gültige Quelle für Einträge. Eine einzelne Quelle kann nur jeweils einem Ereignisprotokoll zugeordnet werden \(und somit Einträge jeweils in nur ein Ereignisprotokoll schreiben\).  
  
 Wenn Sie den Versuch unternehmen, einen Eintrag zu schreiben, ohne zuerst die Komponente als gültige Quelle zu registrieren, registriert das System standardmäßig die Quelle automatisch beim Ereignisprotokoll. Dazu wird der Wert der <xref:System.Diagnostics.EventLog.Source*>\-Eigenschaft als Quellzeichenfolge verwendet.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Quelle beim richtigen Protokoll registriert ist. Verwenden Sie dazu die <xref:System.Diagnostics.EventLog.CreateEventSource*>\-Methode oder eine ihrer Überladungen, um eine Zeichenfolge anzugeben, die die Komponente beim Ereignisprotokoll eindeutig identifiziert.  
  
## Siehe auch  
 [Administering Event Logs](assetId:///35f53238-bdd2-417b-acd8-2fd9f7397f18)   
 [Event Log References](assetId:///4af0661c-6c96-49f4-961d-b26ed9bc3e87)   
 [How to: Add Your Application as a Source of Event Log Entries](assetId:///948ff920-a739-4e66-a191-ee951512d42c)   
 [How to: Remove an Event Source](assetId:///bc66c900-4b8a-426a-b8e2-17031a20167e)