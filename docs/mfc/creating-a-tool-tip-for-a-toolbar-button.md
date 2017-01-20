---
title: "Creating a Tool Tip for a Toolbar Button"
ms.custom: na
ms.date: "12/15/2016"
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
  - "tool tips [C++], adding to toolbar buttons"
  - "\n in tool tip"
  - "toolbar buttons [C++], tool tips"
  - "buttons [C++], tool tips"
  - "Toolbar editor, creating tool tips"
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Tool Tip for a Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So erstellen Sie eine QuickInfo  
  
1.  Markieren Sie die Symbolleisten\-Schaltfläche.  
  
2.  Geben Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) im Eigenschaftenfeld **Eingabeaufforderung** eine Schaltflächenbeschreibung für die Statusleiste ein. Fügen Sie hinter der Meldung "\\n" sowie den Namen der QuickInfo ein.  
  
 Ein bekanntes Beispiel für eine QuickInfo ist die Schaltfläche **Drucken** in WordPad:  
  
 1.  Öffnen Sie WordPad.  
  
 2.  Zeigen Sie mit dem Mauszeiger auf die Symbolleisten\-Schaltfläche **Drucken**.  
  
 3.  Beachten Sie, dass nun der Begriff "Drucken" unterhalb des Mauszeigers angezeigt wird.  
  
 4.  Beachten Sie die Statusleiste \(ganz unten im WordPad\-Fenster\); dort wird jetzt der Text "Druckt das aktive Dokument" angezeigt.  
  
 Der Begriff "Drucken" in Schritt 3 entspricht dem Namen der QuickInfo, und "Druckt das aktuelle Dokument" unter Schritt 4 ist die Schaltflächenbeschreibung für die Statusleiste.  
  
 Sie erzielen diesen Effekt über den Symbolleisten\-Editor, indem Sie für die Eigenschaft **Eingabeaufforderung** die Zeichenfolge **Druckt das aktive Dokument\\nDrucken** angeben.  
  
> [!NOTE]
>  Aufforderungstext kann im [Eigenschaftenfenster](../Topic/Properties%20Window.md) bearbeitet werden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 MFC oder ATL  
  
## Siehe auch  
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)