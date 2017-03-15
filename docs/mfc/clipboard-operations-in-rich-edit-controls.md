---
title: "Zwischenablageoperationen in RichEdit-Steuerelementen | Microsoft Docs"
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
  - "Zwischenablage, Vorgänge in CRichEditCtrl"
  - "Kopiervorgänge in rich-Bearbeitungssteuerelementen"
  - "CRichEditCtrl-Klasse, Zwischenablagevorgänge"
  - "CRichEditCtrl-Klasse, Einfügevorgänge"
  - "Ausschneidenvorgänge in der CRichEditCtrl-Klasse"
  - "Einfügen von Zwischenablagedaten"
  - "Rich-Edit-Steuerelemente, Zwischenablagevorgänge"
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Zwischenablageoperationen in RichEdit-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Anwendung kann den Inhalt der Zwischenablage in ein Rich\-Edit\-Steuerelement \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) entweder mit optimalen verfügbaren Zwischenablageformats oder eines bestimmten Zwischenablageformats einfügen.  Außerdem können Sie bestimmen, ob ein Rich\-Edit\-Steuerelement zum Einfügen eines Zwischenablageformats kann.  
  
 Sie können den Inhalt der aktuellen Auswahl kopieren oder ausschneiden, indem Sie die Memberfunktion [Kopieren](../Topic/CRichEditCtrl::Copy.md) oder [Ausschneiden](../Topic/CRichEditCtrl::Cut.md) verwenden.  Ebenso können Sie den Inhalt der Zwischenablage in ein Rich\-Edit\-Steuerelement einfügen, indem Sie die Memberfunktion [Einfügen](../Topic/CRichEditCtrl::Paste.md) verwenden.  Das Steuerelement fügt die erste verfügbare Format ein, das ihn erkennt, das sich wahrscheinlich das beschreibendste Formats.  
  
 Um ein bestimmtes Zwischenablageformat einzufügen, können Sie die Memberfunktion [PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md) verwenden.  Diese Funktion ist für Anwendungen mit einem Inhalte Einfügen nützlich, der den Benutzer aktiviert, um das Zwischenablageformat auszuwählen.  Sie können die [CanPaste](../Topic/CRichEditCtrl::CanPaste.md)\-Memberfunktion verwenden, um zu bestimmen, ob ein bestimmtes Format vom Steuerelement erkannt wird.  
  
 Sie können `CanPaste` auch verwenden, um zu bestimmen, ob ein verfügbares Zwischenablageformat durch ein Rich\-Edit\-Steuerelement erkannt wird.  Diese Funktion ist nützlich Handler im `OnInitMenuPopup`.  Eine Anwendung den Befehl Einfügen abhängig davon aktivieren oder abblendete möglicherweise, ob das Steuerelement ein Format verfügbar einfügen kann.  
  
 Rich\-Edit\-Steuerelement\-Register zwei Zwischenablageformate: haben und ein Format namens Text und Objekte RichEdit auf.  Eine Anwendung kann diese Stile registrieren, indem sie die [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049)\-Funktion verwendet und den **CF\_RTF** und **CF\_RETEXTOBJ**\-Werte festgelegt werden.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)