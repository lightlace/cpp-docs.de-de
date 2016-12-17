---
title: "Die aktuelle Auswahl in einem RichEdit-Steuerelement"
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
  - "CRichEditCtrl-Klasse, Aktuelle Auswahl in"
  - "Aktuelle Auswahl in CRichEditCtrls"
  - "Rich-Edit-Steuerelemente, Aktuelle Auswahl in"
  - "Auswahl, Aktuell in CRichEditCtrl"
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Die aktuelle Auswahl in einem RichEdit-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Benutzer kann Text in einem Rich\-Edit\-Steuerelement \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) mithilfe der Maus oder Tastatur auswählen verwendet.  Die aktuelle Auswahl ist der Bereich der ausgewählten Zeichen oder die Position der Einfügemarke, wenn keine Zeichen ausgewählt werden.  Eine Anwendung kann Informationen zur aktuellen Auswahl abzurufen, legen Sie die aktuelle Auswahl, bestimmen, wann die aktuelle Auswahl ändert, und die die Auswahlhervorhebung oder ausblenden.  
  
 Um die aktuelle Auswahl in einem Rich\-Edit\-Steuerelement zu bestimmen, verwenden Sie die [GetSel](../Topic/CRichEditCtrl::GetSel.md)\-Memberfunktion.  Um die aktuelle Auswahl festzulegen, verwenden Sie die [SetSel](../Topic/CRichEditCtrl::SetSel.md)\-Memberfunktion.  Die [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885)\-Struktur wird mit diesen Funktionen verwendet, um einen Bereich von Zeichen an.  Um Informationen über den Inhalt der aktuellen Auswahl abzurufen, können Sie die Memberfunktion [GetSelectionType](../Topic/CRichEditCtrl::GetSelectionType.md) verwenden.  
  
 Standardmäßig zeigt ein Rich\-Edit\-Steuerelement an und blendet die Auswahlhervorhebung aus, wenn es den Fokus erhält bzw. verliert.  Sie können die Auswahlhervorhebung jederzeit ein\- oder ausblenden, indem Sie die Memberfunktion [HideSelection](../Topic/CRichEditCtrl::HideSelection.md) verwenden.  Beispielsweise kann eine Anwendung ein Dialogfeld "Suche" zur Verfügung, um Text in einem Rich\-Edit\-Steuerelement zu suchen.  Die Anwendung vielleicht entsprechenden Text, ohne das Dialogfeld zu schließen, in diesem Fall die `HideSelection` verwenden muss, um die Auswahl zu markieren.  
  
 Um den markierten Text in einem Rich\-Edit\-Steuerelement abzurufen, verwenden Sie die [GetSelText](../Topic/CRichEditCtrl::GetSelText.md)\-Memberfunktion.  Der Text wird im angegebenen Zeichenarray kopiert.  Sie müssen sicherstellen, dass das Array ausreicht, um den ausgewählten Text sowie einem NULL enthält.  
  
 Sie können eine Zeichenfolge in einem Rich\-Edit\-Steuerelement suchen, indem Sie die Memberfunktion [FindText](../Topic/CRichEditCtrl::FindText.md) verwenden, die die [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909)\-Struktur, die dieser Funktion verwendet wird, den Textbereich, um zu suchen und der angibt Zeichenfolge zu suchen.  Sie können diesen Optionen wie auch angeben, ob die Suche die Groß\-\/Kleinschreibung beachtet wird.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)