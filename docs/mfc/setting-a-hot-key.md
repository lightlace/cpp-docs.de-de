---
title: "Festlegen einer Abk&#252;rzungstaste"
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
  - "CHotKeyCtrl-Klasse, Festlegen einer Abkürzungstaste"
  - "Tastenkombinationen [C++], Abkürzungstasten"
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Festlegen einer Abk&#252;rzungstaste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Anwendung kann die Informationen verwenden, die von einem bereitgestellten Steuerelement der Zugriffstaste \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) in zwei Arten:  
  
-   Installieren Sie eine globale Zugriffstaste zum Aktivieren eines nonchild Fensters, indem Sie eine [WM\_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284)\-Funktion zu aktivierenden senden, Fenster.  
  
-   Installieren Sie eine Threadbesondereabkürzungstaste, indem Sie die Windows\-Funktion [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) aufrufen.  
  
## Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)