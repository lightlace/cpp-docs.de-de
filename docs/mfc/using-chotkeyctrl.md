---
title: "Verwenden von CHotKeyCtrl"
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
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl-Klasse, Verwenden"
  - "Abkürzungstasten-Steuerelemente"
  - "Schlüssel, hot und CHotKeyCtrl"
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von CHotKeyCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Abkürzungstasten\-Steuerelement, dargestellt durch Klasse [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), ist ein Fenster, das eine Textdarstellung der Tastenkombination die Eingabe in sie anzeigt, z STRG\+UMSCHALT\+Q.  Es wird auch eine interne Darstellung dieser Schlüssel in Form eines virtuellen Tastencodes und einen Satz von Flags bei, die den Schichtzustand darstellen.  Das Abkürzungstasten\-Steuerelement nicht tatsächlich wird die Zugriffstaste fest \- das zu tun ist bis dem Programm. \(Eine Liste von Standardvirtuellen, finden Sie tastencodes Winuser.h.\)  
  
 Verwenden Sie ein Abkürzungstasten\-Steuerelement, um eine Benutzereingabe abzurufen, für die die Zugriffstaste, die in einem Fenster oder Thread zugeordnet.  Abkürzungstasten\-Steuerelemente werden häufig in den Dialogfeldern, wie Sie sich wird möglicherweise angezeigt, wenn sie den Benutzer bitten, eine Zugriffstaste zuzuweisen.  Es liegt in der Verantwortung des Programms, die Werte abzurufen, welche die Zugriffstaste vom Abkürzungstasten\-Steuerelement und die entsprechenden Funktionen aufgerufen, um die Zugriffstaste mit einem Fenster oder einem Thread zu beschreiben.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden eines Abkürzungstasten\-Steuerelements](../mfc/using-a-hot-key-control.md)  
  
-   [Festlegen einer Zugriffstaste](../mfc/setting-a-hot-key.md)  
  
-   [Globale Abkürzungstasten](../mfc/global-hot-keys.md)  
  
-   [Thread\-Besondere\-Abkürzungstasten](../mfc/thread-specific-hot-keys.md)  
  
## Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)