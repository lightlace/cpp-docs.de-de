---
title: "Problembehandlung bei Ausnahmen: System.Exception"
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
  - "System.Exception-Ausnahme"
  - "Basisklassen, Ausnahmen"
  - "Ausnahmen, Basisklasse"
ms.assetid: fc15931a-9323-47c6-a42f-55d0534b939a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# Problembehandlung bei Ausnahmen: System.Exception
Stellt Fehler dar, die beim Ausführen einer Anwendung auftreten. Dies ist die Basisklasse für alle Ausnahmen.  
  
## Tipps  
 **Weitere Informationen finden Sie in der InnerException\-Eigenschaft.**  
 Um den Fehler zu beheben, benötigen Sie möglicherweise Informationen über die interne \(oder vorangegangene\) Ausnahme, die zur aktuellen Ausnahme geführt hat. Die <xref:System.Exception.InnerException*>\-Eigenschaft der aktuellen Ausnahme enthält die interne Ausnahme. Sie können im Dialogfeld **Ausnahmen\-Assistent** über den Link **Details anzeigen** auf die <xref:System.Exception.InnerException*>\-Eigenschaft zugreifen.  
  
 **Vorübergehend Nur mein Code\-Debuggen deaktivieren.**  
 Die Ausnahme ist möglicherweise in Code aufgetreten, den Sie nicht geschrieben haben. Um diesen Code zu debuggen, müssen Sie möglicherweise Nur mein Code\-Debuggen deaktivieren. Weitere Informationen finden Sie unter [Allgemein, Debuggen, Dialogfeld "Optionen"](../Topic/General,%20Debugging,%20Options%20Dialog%20Box.md).  
  
## Siehe auch  
 <xref:System.Exception>   
 <xref:System.Exception.InnerException*>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Gewusst wie: Unterbrechen bei ausgelöster Ausnahme](../misc/how-to-break-when-an-exception-is-thrown.md)   
 [Allgemein, Debuggen, Dialogfeld "Optionen"](../Topic/General,%20Debugging,%20Options%20Dialog%20Box.md)