---
title: "CommandHandler"
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
  - "CommandHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CommandHandler function"
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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