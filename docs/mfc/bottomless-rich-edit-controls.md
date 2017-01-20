---
title: "Unbeschr&#228;nkte Rich-Edit-Steuerelemente"
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
  - "unbeschränkte Rich-Bearbeitungssteuerelemente"
  - "CRichEditCtrl-Klasse, unbeschränkt"
  - "Rich-Edit-Steuerelemente, unbeschränkt"
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Unbeschr&#228;nkte Rich-Edit-Steuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Anwendung kann ein Rich\-Edit\-Steuerelement \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) nach Bedarf angepasst werden, sodass er immer die gleiche Größe als sein Inhalt ist.  Ein Rich\-Edit\-Steuerelement unterstützt diese so genannte "bodenlose" Funktionen, indem sein übergeordnetes Fenster [EN\_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) eine Benachrichtigung gesendet, wenn die Größe des Inhalts ändert.  
  
 Wenn sie die **EN\_REQUESTRESIZE** Benachrichtigung verarbeitet, Eine Anwendung sollte das Steuerelement in den Dimensionen in der angegebenen [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950)\-Struktur Größe ändern.  Eine Anwendung verschieben kann möglicherweise auch alle Informationen neben dem Steuerelement, um die Änderung des Steuerelements in der Höhe anzupassen.  Um die Größe des Steuerelements zu ändern, können Sie die `CWnd`[SetWindowPos](../Topic/CWnd::SetWindowPos.md)\- Funktion verwenden.  
  
 Sie können ein bodenloses Rich\-Edit\-Steuerelement zwingen, eine **EN\_REQUESTRESIZE** Benachrichtigung senden, indem Sie die Memberfunktion [RequestResize](../Topic/CRichEditCtrl::RequestResize.md) verwenden.  Diese Meldung kann im [OnSize](../Topic/CWnd::OnSize.md)\-Handler hilfreich sein.  
  
 Damit **EN\_REQUESTRESIZE** Benachrichtigungen empfangen, müssen Sie die Benachrichtigungs\-URL aktivieren indem Sie die Memberfunktion `SetEventMask` verwenden.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)