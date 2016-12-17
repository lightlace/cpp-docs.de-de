---
title: "NotifyHandler"
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
  - "NotifyHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NotifyHandler function"
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# NotifyHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Name der Funktion identifiziert durch den dritten Parameter des `NOTIFY_HANDLER`\-Makros in der Meldungszuordnung.  
  
## Syntax  
  
```  
  
      LRESULT   
      NotifyHandler  
      (  
   int idCtrl,  
   LPNMHDR pnmh,  
   BOOL& bHandled   
);  
```  
  
#### Parameter  
 `idCtrl`  
 Der Bezeichner des Steuerelements, das die Meldung sendet.  
  
 *pnmh*  
 Adresse einer [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514)\-Struktur, die den Benachrichtigungscode und die zusätzliche Informationen enthält.  Für einige Benachrichtigungsmeldungen zeigt dieser Parameter auf einer größeren Struktur, die die **NMHDR**\-Struktur als erster Member verfügt.  
  
 `bHandled`  
 Die Meldungszuordnung legt `bHandled` zu **TRUE** fest, bevor *NotifyHandler* aufgerufen wird.  Wenn *NotifyHandler* nicht vollständig die Meldung verarbeitet, sollte es `bHandled` zu **FALSE** festlegen, um die weiter Verarbeitungsaufwand Meldungsanforderungen anzugeben.  
  
## Rückgabewert  
 Das Ergebnis des Meldungsverarbeitens.  0 Wenn erfolgreich.  
  
## Hinweise  
 Ein Beispiel für die Verwendung dieses Meldungshandlers in einer Meldungszuordnung, finden Sie unter [NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md).  
  
## Siehe auch  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)