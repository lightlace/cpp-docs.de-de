---
title: "Verwenden eines Abk&#252;rzungstasten-Steuerelements"
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
  - "CHotKeyCtrl-Klasse, Verwenden"
  - "Abkürzungstasten-Steuerelemente"
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden eines Abk&#252;rzungstasten-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typische Verwendung eines Abkürzungstasten\-Steuerelements entspricht dem Muster unten:  
  
-   Das Steuerelement wird erstellt.  Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, ist Erstellung automatisch, wenn das Dialogfeld erstellt wird. \(Sie sollten [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) einen Member in der Dialogfeldklasse haben, die zum Abkürzungstasten\-Steuerelement entspricht.\) Alternativ können Sie die Memberfunktion [Erstellen](../Topic/CHotKeyCtrl::Create.md) verwenden, um das Steuerelement als untergeordnetes Fenster eines jeden Fensters zu erstellen.  
  
-   Wenn Sie einen Standardwert für das Steuerelement festlegen möchten, rufen Sie die [SetHotKey](../Topic/CHotKeyCtrl::SetHotKey.md)\-Memberfunktion auf.  Wenn Sie bestimmte Schichtzustände verhindern möchten, rufen Sie [SetRules](../Topic/CHotKeyCtrl::SetRules.md) auf.  Für Steuerelemente in einem Dialogfeld, ist ein guter Zeitpunkt, dazu in der [OnInitDialog](../Topic/CDialog::OnInitDialog.md)\-Funktion des Dialogfelds.  
  
-   Der Benutzer interagiert mit dem Steuerelement ein, indem eine Abkürzungstastenkombination drückt, während das Abkürzungstasten\-Steuerelement den Fokus besitzt.  Der Benutzer gibt, dass alle diese Aufgabe abgeschlossen ist, möglicherweise an, indem er auf eine Schaltfläche im Dialogfeld klickt.  
  
-   Wenn das Programm benachrichtigt wird, dass der Benutzer eine Zugriffstaste ausgewählt hat, sollte er die Memberfunktion [GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md) verwenden, um die virtuellen Schlüssel\- und Schichtzustandswerte vom Abkürzungstasten\-Steuerelement abzurufen.  
  
-   Wenn Sie wissen, welcher Schlüssel der Benutzer, der ausgewählt ist, die Zugriffstaste mit einer der Methoden festlegen kann, die in [Festlegen einer Zugriffstaste](../mfc/setting-a-hot-key.md) beschrieben werden.  
  
-   Wenn das Abkürzungstasten\-Steuerelement in einem Dialogfeld ist, werden diese und das `CHotKeyCtrl`\-Objekt automatisch zerstört.  Falls nicht, müssen Sie sicherstellen, dass das Steuerelement und das `CHotKeyCtrl`\-Objekt ordnungsgemäß gelöscht werden.  
  
## Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)