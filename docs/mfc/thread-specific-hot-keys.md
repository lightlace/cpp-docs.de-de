---
title: "Threadspezifische Abk&#252;rzungstasten"
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
  - "Zugriffstasten [C++], Abkürzungstasten"
  - "CHotKeyCtrl-Klasse, Threadspezifische Abkürzungstasten"
  - "Tastenkombinationen [C++], Abkürzungstasten"
  - "Threading [C++], Abkürzungstasten in CHotKeyCtrl"
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Threadspezifische Abk&#252;rzungstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Anwendung festgelegt wird eine Threadbesondereabkürzungstaste \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) durch die Windows\-Funktion **RegisterHotKey** verwendet.  Wenn der Benutzer eine Threadbesondereabkürzungstaste drückt, sendet Windows [WM\_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) eine Meldung am Anfang der bestimmten Meldungswarteschlange eines Threads.  Die **WM\_HOTKEY** Meldung enthält den virtueller Tastencode, den Schichtzustand und die benutzerdefinierte ID der bestimmten Abkürzungstaste\-Steuerelement, die gedrückt wurde.  Eine Liste von Standardvirtuellen, finden Sie tastencodes Winuser.h.  Weitere Informationen über diese Methode, finden Sie unter [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Beachten Sie, dass die Schichtzustandsflags, die im Aufruf von **RegisterHotKey** verwendet werden, die nicht identisch sind, die durch die [GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md)\-Memberfunktion zurückgegeben werden; Sie müssen diese Flags übersetzen, bevor Sie **RegisterHotKey** aufrufen.  
  
## Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)