---
title: "Benachrichtigungen von einem RichEdit-Steuerelement | Microsoft Docs"
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
  - "CRichEditCtrl-Klasse, Benachrichtigungen"
  - "Meldungen, Benachrichtigung"
  - "Benachrichtigungen, von CRichEditCtrl"
  - "Rich-Edit-Steuerelemente, Benachrichtigungen"
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Benachrichtigungen von einem RichEdit-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Benachrichtigungsmeldungsberichtsereignisse, die ein Rich\-Edit\-Steuerelement \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) beeinflussen.  Sie können vom übergeordneten Fenster oder, mithilfe der Meldungsreflektion verarbeitet werden, durch das Rich\-Edit\-Steuerelement selbst.  Verwendet unterstützen alle Benachrichtigungsmeldungen, die in Bearbeitungssteuerelementen sowie einige zusätzliche verwendet werden.  Sie können bestimmen, Benachrichtigungsmeldungen dem ein Rich\-Edit\-Steuerelement das übergeordnete Fenster gesendet werden, indem sie die Ereignismaske festlegen "."  
  
 Um die Ereignismaske für ein Rich\-Edit\-Steuerelement festzulegen, verwenden Sie die [SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md)\-Memberfunktion.  Sie können die Tagesereignissemaske für ein Rich\-Edit\-Steuerelement abrufen, indem Sie die Memberfunktion [GetEventMask](../Topic/CRichEditCtrl::GetEventMask.md) verwenden.  
  
 In den folgenden Absätzen führen bestimmte Benachrichtigungen und deren Verwendungszweck aufgeführt:  
  
-   Eine **EN\_MSGFILTER**, die die **EN\_MSGFILTER** Benachrichtigung behandelt, können entweder eine Klasse, das Rich\-Edit\-Steuerelement, oder das übergeordnete Fenster, filtern alle Tastatur\- und Mauseingabe für das Steuerelement.  Der Handler kann die Tastatur\- oder Mausmeldung an verarbeitet werden oder verhindern kann die Nachricht geändert, indem die angegebene [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936)\-Struktur ändern.  
  
-   **EN\_PROTECTED EN\_PROTECTED** Handle die Benachrichtigung, zu erkennen, wenn der Benutzer versucht, geschützten Text zu ändern.  Um einen Textbereich zu markieren wie geschützt, können Sie den geschützten Zeicheneffekt festlegen.  Weitere Informationen finden Sie unter [Zeichenformatierung in den Rich\-Edit\-Steuerelementen](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   **EN\_DROPFILES** Sie können den Benutzern ermöglichen, Dateien in einem Rich\-Edit\-Steuerelement abzulegen, indem Sie die **EN\_DROPFILES** Benachrichtigung verarbeiten.  Die angegebene Struktur [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) enthält Informationen über die Dateien, die behoben werden.  
  
-   **EN\_SELCHANGE** Eine Anwendung kann erkennen, wenn die aktuelle Auswahl ändert, indem sie die **EN\_SELCHANGE** Benachrichtigung verarbeitet.  Die Benachrichtigung gibt [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) eine Struktur, die Informationen über die neue Auswahl enthält.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)