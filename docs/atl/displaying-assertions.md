---
title: "Displaying Assertions"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Displaying Assertions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn der Client, der an den Dienst verbunden ist, wird nicht mehr reagiert, der Dienst ein Meldungsfeld bedacht haben und möglicherweise angezeigt, dass Sie nicht in der Lage sind anzuzeigen.  Sie können dies überprüfen, indem Sie Visual C\+\+ Debugger verwenden, um den Code zu debuggen \(siehe [Verwenden des Task\-Managers](../atl/using-task-manager.md) weiter oben in diesem Abschnitt\).  
  
 Wenn Sie feststellen, ob der Dienst ein Meldungsfeld anzeigt, das Sie nicht sehen können, sollten Sie die Option festlegen, **Datenaustausch zwischen Dienst und Desktop zulassen** vor den Dienst erneut verwenden.  Diese Option ist ein Startparameter, der alle Meldungsfelder ermöglicht, die vom Dienst angezeigt werden, um auf dem Desktop zu werden.  Um diese Option festzulegen, öffnen Sie die Dienste\-Systemsteuerungs\-Anwendung, wählen Sie den Dienst aus, klicken Sie auf **Start** und wählen Sie dann die Option aus. **Datenaustausch zwischen Dienst und Desktop zulassen**  
  
## Siehe auch  
 [Debugging Tips](../atl/debugging-tips.md)