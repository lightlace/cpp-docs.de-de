---
title: "MessageHandler"
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
  - "MessageHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MessageHandler function"
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MessageHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**MessageHandler** ist der Name der Funktion, die durch den zweiten Parameter des `MESSAGE_HANDLER`\-Makros in der Meldungszuordnung identifiziert wird.  
  
## Syntax  
  
```  
  
      LRESULT   
      MessageHandler  
      (  
   UINT uMsg,  
   WPARAM wParam,  
   LPARAM lParam,  
   BOOL& bHandled  
);  
```  
  
#### Parameter  
 `uMsg`  
 Gibt die Meldung an.  
  
 `wParam`  
 Zusätzliche meldungsspezifische Informationen.  
  
 `lParam`  
 Zusätzliche meldungsspezifische Informationen.  
  
 `bHandled`  
 Die Meldungszuordnungssätze `bHandled` zu **TRUE** vor `MessageHandler` wird aufgerufen.  Wenn `MessageHandler` nicht vollständig die Meldung verarbeitet, sollte sie `bHandled` zu **FALSE** festlegen, um die weiter Verarbeitungsaufwand Meldungsanforderungen anzugeben.  
  
## Rückgabewert  
 Das Ergebnis des Meldungsverarbeitens.  0 Wenn erfolgreich.  
  
## Hinweise  
 Ein Beispiel für die Verwendung dieses Meldungshandlers in einer Meldungszuordnung, finden Sie unter [MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md).  
  
## Siehe auch  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)