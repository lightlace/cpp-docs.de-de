---
title: "Adding Commands to a Menu"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.menu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "menu items, adding to menus"
  - "menus, adding items"
  - "commands, adding to menus"
  - "commands"
  - "menu items"
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Commands to a Menu
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So fügen Sie Befehle zu einem Menü hinzu  
  
1.  [Erstellen Sie ein Menü](../windows/creating-a-menu.md).  
  
2.  Klicken Sie auf einen Menünamen, beispielsweise „Datei“.  
  
     Jedes Menü wird erweitert, und es wird ein neues Elementfeld für Befehle zur Verfügung gestellt.  Beispielsweise können Sie die Befehle „New“, „Open“ und „Close“ zu einem Dateimenü hinzufügen.  
  
3.  Geben Sie im neuen Elementfeld einen Namen für den neuen Menübefehl ein.  
  
    > [!NOTE]
    >  Der eingegebene Text wird sowohl im Menü\-Editor als auch im Feld **Beschriftung** im [Eigenschaftenfenster](../Topic/Properties%20Window.md) angezeigt.  Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.  
  
    > [!TIP]
    >  Sie können eine mnemonische Taste \(Zugriffstaste\) definieren, die dem Benutzer ermöglicht, den Menübefehl auszuwählen.  Geben Sie ein kaufmännisches Und\-Zeichen \(&\) vor einen Buchstaben ein, um ihn als mnemonisch anzugeben.  Der Benutzer kann den Menübefehl auswählen, indem er diesen Buchstaben eingibt.  
  
4.  Wählen Sie im Fenster „Eigenschaften“ die geltenden Menübefehlseigenschaften aus.  Weitere Informationen finden Sie unter [Menübefehlseigenschaften](../windows/menu-command-properties.md).  
  
5.  Geben Sie im Feld **Eingabeaufforderung** im Fenster „Eigenschaften“ die Eingabeaufforderungs\-Zeichenfolge ein, die auf der Statusleiste Ihrer Anwendung angezeigt werden soll.  
  
     Dadurch wird ein Eintrag mit einem Ressourcenbezeichner in der Zeichenfolgentabelle erstellt, der dem von Ihnen erstellten Menübefehl entspricht.  
  
    > [!NOTE]
    >  Eingabeaufforderungen können nur auf Menüelemente mit einer **Popup**\-Eigenschaft von **True** angewendet werden.  Beispielsweise können Menüelemente auf oberster Ebene über Eingabeaufforderungen verfügen, wenn sie über Untermenüelemente verfügen.  Der Zweck einer Eingabeaufforderung besteht darin, das anzuzeigen, was passiert, wenn ein Benutzer auf das Menüelement klickt.  
  
6.  Drücken Sie die EINGABETASTE, um den Menübefehl abzuschließen.  
  
     Das neue Elementfeld wird ausgewählt, sodass Sie zusätzliche Menübefehle erstellen können.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Menu Editor](../mfc/menu-editor.md)   
 [Menüs](_win32_Menus)