---
title: "Formatieren von Zeichen in RichEdit-Steuerelementen"
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
  - "CRichEditCtrl-Klasse, Zeichenformatierung in"
  - "Formatierung [C++], Zeichen"
  - "Rich-Edit-Steuerelemente, Zeichenformatierung in"
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Formatieren von Zeichen in RichEdit-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Memberfunktionen des Rich\-Edit\-Steuerelements \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) den Formatierungsinformationen Formatzeichen verwenden und abrufen.  Für Zeichen können Sie Schriftart, Größe, Farbe und Effekten wie Fett, kursiv formatierten Text festlegen und geschützte sich.  
  
 Sie können Zeichenformatierung anwenden, indem Sie die [SetSelectionCharFormat](../Topic/CRichEditCtrl::SetSelectionCharFormat.md) und [SetWordCharFormat](../Topic/CRichEditCtrl::SetWordCharFormat.md) verwenden Memberfunktionen.  Um die aktuelle Zeichenformatierung für den markierten Text zu bestimmen, verwenden Sie die [GetSelectionCharFormat](../Topic/CRichEditCtrl::GetSelectionCharFormat.md)\-Memberfunktion.  Die [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881)\-Struktur wird mit dieser Memberfunktionen verwendet, um anzugeben Zeichenattributen.  Einer der wichtigen Member von **CHARFORMAT** ist **dwMask**.  In `SetSelectionCharFormat` und `SetWordCharFormat` gibt **dwMask** an, die Zeichenattribute von diesem Funktionsaufruf eingerichtet werden.  `GetSelectionCharFormat` meldet die Attribute des ersten Zeichens in der Auswahl; **dwMask** gibt den Attributen an, die während der Auswahl konsistent sind.  
  
 Sie können die "Standardzeichenformatierung auch abrufen und festlegen" auszusondern, die die Formatierung, die in allen eingefügten Zeichen anschließend angewendet wird.  Wenn eine Anwendung die Standardzeichenformatierung auf Fett festlegt und der Benutzer anschließend ein Zeichen eingibt, lautet dieses Zeichen fett.  Um Standardzeichenformatierung abzurufen und festzulegen, verwenden Sie die [GetDefaultCharFormat](../Topic/CRichEditCtrl::GetDefaultCharFormat.md) und [SetDefaultCharFormat](../Topic/CRichEditCtrl::SetDefaultCharFormat.md)\-Memberfunktionen.  
  
 Das "Zeichenattribut geschützte" ändert nicht die Darstellung des Texts.  Wenn der Benutzer versucht, geschützten Text zu ändern, wird ein Rich\-Edit\-Steuerelement sein übergeordnetes Fenster **EN\_PROTECTED** eine Benachrichtigung und ermöglicht dem übergeordneten Fenster, um die Änderung zu ermöglichen oder zu verbieten.  Um diese Benachrichtigung zu erhalten, müssen Sie sie aktivieren indem Sie die Memberfunktion [SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md) verwenden.  Weitere Informationen über die Ereignismaske, finden Sie unter [Benachrichtigungen von einem Rich\-Edit\-Steuerelement](../mfc/notifications-from-a-rich-edit-control.md), weiter unten in diesem Thema.  
  
 Vordergrundfarbe ist ein Zeichenattribut, aber Hintergrundfarbe ist eine Eigenschaft des Rich\-Edit\-Steuerelements.  Wenn Sie die Hintergrundfarbe festlegen, verwenden Sie die [SetBackgroundColor](../Topic/CRichEditCtrl::SetBackgroundColor.md)\-Memberfunktion.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)