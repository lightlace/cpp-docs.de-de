---
title: "CommandHandler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CommandHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CommandHandler function"
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CommandHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CommandHandler` ist die Funktion, die durch den dritten Parameter des `COMMAND_HANDLER`\-Makros in der Meldungszuordnung identifiziert wird.  
  
## Syntax  
  
```  
  
      LRESULT   
      CommandHandler  
      (  
   WORD wNotifyCode,  
   WORD wID,  
   HWND hWndCtl,  
   BOOL& bHandled   
);  
```  
  
#### Parameter  
 `wNotifyCode`  
 Der Benachrichtigungscode.  
  
 *wID*  
 Der Bezeichner des Menüelements, des Steuerelements oder der Zugriffstaste.  
  
 *hWndCtl*  
 Ein Handle zu einem Window\-Steuerelement.  
  
 `bHandled`  
 Die Meldungszuordnungssätze `bHandled` zu **TRUE** vor `CommandHandler` wird aufgerufen.  Wenn `CommandHandler` nicht vollständig die Meldung verarbeitet, sollte sie `bHandled` zu **FALSE** festlegen, um die weiter Verarbeitungsaufwand Meldungsanforderungen anzugeben.  
  
## Rückgabewert  
 Das Ergebnis des Meldungsverarbeitens.  0 Wenn erfolgreich.  
  
## Hinweise  
 Ein Beispiel für die Verwendung dieses Meldungshandlers in einer Meldungszuordnung, finden Sie unter [COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md).  
  
## Siehe auch  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)