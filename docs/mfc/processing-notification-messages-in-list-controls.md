---
title: Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af648a0bf4ae78c5c5e8bcceeac12c5dbc87307a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="processing-notification-messages-in-list-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen
Wie Benutzer auf Spaltenüberschriften klicken, ziehen Sie die Symbole, Bearbeiten von Bezeichnungen und So weiter, das Strukturelement-Steuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) sendet benachrichtigungsmeldungen an das übergeordnete Fenster. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Klickt der Benutzer auf eine Spaltenüberschrift, sollten Sie z. B. Sortieren der Elemente basierend auf dem Inhalt dieser Spalte, wie in Microsoft Outlook.  
  
 Prozess **WM_NOTIFY** Nachrichten das Strukturelement-Steuerelement in der Ansichts- oder Dialogfeldobjekt-Klasse. Verwenden des Eigenschaftenfensters zum Erstellen einer [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) Handlerfunktion mit einer Switch-Anweisung basierend auf der benachrichtigungsmeldung behandelt wird.  
  
 Eine Liste der Benachrichtigungen ein Listenfeld-Steuerelement an das übergeordnete Fenster senden kann, finden Sie unter [Liste Ansicht Kontrollverweis](http://msdn.microsoft.com/library/windows/desktop/bb774737) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

