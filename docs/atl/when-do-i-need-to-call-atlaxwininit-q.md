---
title: "When Do I Need to Call AtlAxWinInit?"
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
  - "AtlAxWinInit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinInit method"
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinInit?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinInit](../Topic/AtlAxWinInit.md) registriert die **"AtlAxWin80"** Fensterklasse \(plus ein paar benutzerdefinierte Fenstermeldungen\), daher muss diese Funktion aufgerufen werden, bevor Sie versuchen, ein Hostfenster zu erstellen.  Sie müssen jedoch nicht immer, um diese Funktion explizit aufzurufen, da die APIs \(und die Klassen, die sie verwenden\), häufig diese Funktion für Sie aufrufen.  Es gibt keinen Schaden, falls diese Funktion mehrmals aufruft.  Weitere Informationen finden Sie unter [Was ist das ATL\-Steuerelement\-Hosting API?](../atl/what-is-the-atl-control-hosting-api-q.md).  
  
## Siehe auch  
 [When Do I Need to Call AtlAxWinTerm?](../atl/when-do-i-need-to-call-atlaxwinterm-q.md)   
 [Fragen und Antworten zur Steuerelementkapselung](../atl/atl-control-containment-faq.md)