---
title: "Threadspezifische Abk&#252;rzungstasten | Microsoft Docs"
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
  - "Zugriffstasten [C++], Abkürzungstasten"
  - "CHotKeyCtrl-Klasse, Threadspezifische Abkürzungstasten"
  - "Tastenkombinationen [C++], Abkürzungstasten"
  - "Threading [C++], Abkürzungstasten in CHotKeyCtrl"
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Threadspezifische Abk&#252;rzungstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Anwendung festgelegt wird eine Threadbesondereabkürzungstaste \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) durch die Windows\-Funktion **RegisterHotKey** verwendet.  Wenn der Benutzer eine Threadbesondereabkürzungstaste drückt, sendet Windows [WM\_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) eine Meldung am Anfang der bestimmten Meldungswarteschlange eines Threads.  Die **WM\_HOTKEY** Meldung enthält den virtueller Tastencode, den Schichtzustand und die benutzerdefinierte ID der bestimmten Abkürzungstaste\-Steuerelement, die gedrückt wurde.  Eine Liste von Standardvirtuellen, finden Sie tastencodes Winuser.h.  Weitere Informationen über diese Methode, finden Sie unter [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Beachten Sie, dass die Schichtzustandsflags, die im Aufruf von **RegisterHotKey** verwendet werden, die nicht identisch sind, die durch die [GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md)\-Memberfunktion zurückgegeben werden; Sie müssen diese Flags übersetzen, bevor Sie **RegisterHotKey** aufrufen.  
  
## Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)