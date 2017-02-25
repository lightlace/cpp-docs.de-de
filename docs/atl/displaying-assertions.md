---
title: "Displaying Assertions | Microsoft Docs"
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
  - "Assertionen, Debuggen"
  - "Assertionen, Anzeigen"
  - "Debuggen [ATL], displaying assertions"
  - "Debuggen von Assertionen"
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Displaying Assertions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn der Client, der an den Dienst verbunden ist, wird nicht mehr reagiert, der Dienst ein Meldungsfeld bedacht haben und möglicherweise angezeigt, dass Sie nicht in der Lage sind anzuzeigen.  Sie können dies überprüfen, indem Sie Visual C\+\+ Debugger verwenden, um den Code zu debuggen \(siehe [Verwenden des Task\-Managers](../atl/using-task-manager.md) weiter oben in diesem Abschnitt\).  
  
 Wenn Sie feststellen, ob der Dienst ein Meldungsfeld anzeigt, das Sie nicht sehen können, sollten Sie die Option festlegen, **Datenaustausch zwischen Dienst und Desktop zulassen** vor den Dienst erneut verwenden.  Diese Option ist ein Startparameter, der alle Meldungsfelder ermöglicht, die vom Dienst angezeigt werden, um auf dem Desktop zu werden.  Um diese Option festzulegen, öffnen Sie die Dienste\-Systemsteuerungs\-Anwendung, wählen Sie den Dienst aus, klicken Sie auf **Start** und wählen Sie dann die Option aus. **Datenaustausch zwischen Dienst und Desktop zulassen**  
  
## Siehe auch  
 [Debugging Tips](../atl/debugging-tips.md)