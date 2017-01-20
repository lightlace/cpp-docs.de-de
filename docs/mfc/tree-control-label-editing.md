---
title: "Bearbeiten der Struktursteuerelement-Bezeichnung"
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
  - "CTreeCtrl-Klasse, Bearbeiten von Bezeichnungen"
  - "Bearbeiten von Struktursteuerelement-Bezeichnungen"
  - "Bearbeiten von Bezeichnungen in der CTreeCtrl-Klasse"
  - "Struktursteuerelemente, Bearbeiten von Bezeichnungen"
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Bearbeiten der Struktursteuerelement-Bezeichnung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Benutzer kann die Bezeichnungen der Elemente in einem Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) direkt bearbeiten das das **TVS\_EDITLABELS** Format hat.  Der Benutzer beginnt Bearbeitung, indem er auf die Bezeichnung des Elements klicken, das den Fokus besitzt.  Eine Anwendung startet Bearbeitung, indem sie die [EditLabel](../Topic/CTreeCtrl::EditLabel.md)\-Memberfunktion verwendet.  Das Tree\-Steuerelement sendet die Benachrichtigung, wenn das Bearbeiten beginnt und wenn sie abgebrochen oder abgeschlossen wird.  Wenn die Bearbeitung abgeschlossen wird, können Sie zum Aktualisieren der Bezeichnung des Elements zuständig, wenn entsprechend.  
  
 Wenn Bezeichnungsbearbeitung beginnt, sendet eine Strukturansicht eine Benachrichtigung. [TVN\_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) Auf diese Benachrichtigung verarbeiten, können Sie mehrere Bezeichnungen und Bearbeitung ermöglichen das Bearbeiten andere verhindern.  Die Rückgabe 0 ermöglicht Bearbeiten und das Zurückgeben des Werts ungleich 0 \(null\) verhindert sie.  
  
 Wenn Bezeichnungsbearbeitung abgebrochen oder abgeschlossen ist, sendet eine Strukturansicht eine Benachrichtigung. [TVN\_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515) Der Parameter ist `lParam` die Adresse [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) eine Struktur.  Der **Element**\-Member [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) ist eine Struktur, die das Element identifiziert und den bearbeiteten Text enthält.  Sie sind zum Aktualisieren der Bezeichnung des Elements zuständig, wenn entsprechend, etwa, nachdem Sie die bearbeitete Zeichenfolge überprüft haben.  Der **pszText**\-Member von `TV_ITEM` ist 0, während der Bearbeitung abgebrochen wird.  
  
 Während der Bezeichnungsbearbeitung normalerweise als Reaktion auf die [TVN\_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) Benachrichtigung, können Sie einen Zeiger an das Bearbeitungssteuerelement finden, das für Bezeichnung bearbeiten verwendet wird, indem Sie die Memberfunktion [GetEditControl](../Topic/CTreeCtrl::GetEditControl.md) verwenden.  Sie können die [SetLimitText](../Topic/CEdit::SetLimitText.md)\-Memberfunktion des Bearbeitungssteuerelements aufrufen, um die Textmenge zu beschränken, den ein Benutzer dem Bearbeitungssteuerelement eingeben oder unterordnen kann, um ungültige Zeichen abzufangen und zu verwerfen.  Beachten Sie jedoch das Bearbeitungssteuerelement angezeigt wird, nachdem **TVN\_BEGINLABELEDIT** gesendet wird.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)