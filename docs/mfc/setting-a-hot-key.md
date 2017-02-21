---
title: "Festlegen einer Abk&#252;rzungstaste | Microsoft Docs"
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
  - "CHotKeyCtrl-Klasse, Festlegen einer Abkürzungstaste"
  - "Tastenkombinationen [C++], Abkürzungstasten"
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Festlegen einer Abk&#252;rzungstaste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Anwendung kann die Informationen verwenden, die von einem bereitgestellten Steuerelement der Zugriffstaste \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) in zwei Arten:  
  
-   Installieren Sie eine globale Zugriffstaste zum Aktivieren eines nonchild Fensters, indem Sie eine [WM\_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284)\-Funktion zu aktivierenden senden, Fenster.  
  
-   Installieren Sie eine Threadbesondereabkürzungstaste, indem Sie die Windows\-Funktion [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) aufrufen.  
  
## Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)