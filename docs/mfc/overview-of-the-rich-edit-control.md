---
title: "&#220;bersicht &#252;ber das RichEdit-Steuerelement | Microsoft Docs"
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
  - "Rich-Edit-Steuerelemente"
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# &#220;bersicht &#252;ber das RichEdit-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Wenn Sie ein Rich\-Edit\-Steuerelement in einem Dialogfeld verwenden \(unabhängig davon, ob Ihre SDI\-Anwendung, MDI oder dialogfeldbasiertes ist\), müssen Sie [AfxInitRichEdit](../Topic/AfxInitRichEdit.md) aufrufen, bevor das Dialogfeld angezeigt wird.  Ein typischer Position, an dieser Funktion wird in `InitInstance`\-Memberfunktion des Programms.  Sie müssen nicht, um ihn für jedes Mal, wenn Sie das Dialogfeld anzeigen, nur das erste Mal aufrufen.  Sie müssen `AfxInitRichEdit` nicht aufrufen, wenn mit `CRichEditView` arbeiten.  
  
 Verwendet \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) stellen eine Programmierschnittstelle zum Formatieren von Text bereit.  Es muss eine Anwendung alle Benutzeroberflächenkomponenten implementieren, die erforderlich sind, Formatierungsvorgänge für den Benutzer verfügbar zu machen.  Das heißt, unterstützt das Rich\-Edit\-Steuerelement Ändern des Zeichens oder der Absatzstile von markiertem Text.  Einige Beispiele von Zeichenattributen sind fett, kursiv, Schriftfamilie und Schriftgröße.  Beispiele Absatzformatvorlagen enthalten Ausrichtung, Ränder und Tabstopps.  Allerdings liegt es immer zu Ihnen, um die Benutzeroberfläche bereitzustellen, ob das Symbolleistenschaltflächen, Menüelemente oder ein Formatzeichendialogfeld ist.  Es sind außerdem Funktionen, um den Rich\-Edit\-Steuerelements für die Attribute der aktuellen Auswahl abzufragen.  Verwenden Sie diese Funktionen, um die aktuellen Einstellungen für die Attribute beispielsweise anzuzeigen ein Häkchen auf der Befehlsbenutzeroberfläche festlegen, ob die Markierung das Fett Zeichenformatierungsattribut hat.  
  
 Weitere Informationen über Zeichen und Absatzformatierung, finden Sie unter [Zeichenformatierung](../mfc/character-formatting-in-rich-edit-controls.md) und [Für Absatzformatierung](../mfc/paragraph-formatting-in-rich-edit-controls.md) weiter unten in diesem Thema.  
  
 Verwendet unterstützen fast alle Vorgänge und Benachrichtigungsmeldungen, die mit mehrzeiligem Bearbeitungssteuerelementen verwendet werden.  Folglich können Anwendungen, die bereits von Bearbeitungssteuerelementen verwenden, problemlos geändert werden, die derzeit verwendet.  Zusätzliche Meldungen und Benachrichtigungen können Anwendungen, die auf Funktionen zugreifen, die den Rich\-Edit\-Steuerelementen eindeutig ist.  Informationen zu allen Bearbeitungssteuerelementen, finden Sie unter [CEdit](../mfc/reference/cedit-class.md).  
  
 Weitere Informationen über Benachrichtigungen, finden Sie unter [Benachrichtigungen von einem Rich\-Edit\-Steuerelement](../mfc/notifications-from-a-rich-edit-control.md) weiter unten in diesem Thema.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)