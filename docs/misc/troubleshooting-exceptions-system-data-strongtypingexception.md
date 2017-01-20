---
title: "Problembehandlung bei Ausnahmen: System.Data.StrongTypingException"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "StrongTypingException-Klasse"
ms.assetid: 90859ce2-3696-43cb-baf4-7daf98d8e2e1
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "douge"
---
# Problembehandlung bei Ausnahmen: System.Data.StrongTypingException
Eine <xref:System.Data.StrongTypingException> tritt auf, wenn der Benutzer auf einen <xref:System.DBNull>\-Wert in einem stark typisierten <xref:System.Data.DataTable.DataSet*> zugreift.  
  
## Tipps  
 **Fügen Sie eine Fehlerbehandlung für die StrongTypingException hinzu.**  
 Platzieren Sie den Code, der auf das <xref:System.Data.DataTable.DataSet*> zugreift, in einem `Try…Catch`\-Block, und fangen Sie die <xref:System.Data.StrongTypingException> ab.  
  
## Siehe auch  
 <xref:System.Data.DataTable.DataSet*>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [Arbeiten mit Datasets in Visual Studio](../Topic/Dataset%20tools%20in%20Visual%20Studio.md)