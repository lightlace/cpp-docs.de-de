---
title: Benachrichtigungen von einem Rich-Edit-Steuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcfcb2e4fe333db1ed629489b405255d4ab050b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-from-a-rich-edit-control"></a>Benachrichtigungen von einem RichEdit-Steuerelement
Benachrichtigung Nachrichten Bericht Ereignisse, die Auswirkungen auf ein Rich-edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Sie können durch das übergeordnete Fenster verarbeitet werden oder mithilfe von Reflektion Nachricht vom Rich edit-Steuerelement selbst. Rich-Edit-Steuerelemente unterstützen alle die benachrichtigungsmeldungen mit Bearbeitungssteuerelementen sowie mehrere zusätzliche diejenigen verwendet. Sie können bestimmen, welche benachrichtigungsmeldungen ein rich-Edit-Steuerelement das übergeordnete Fenster sendet durch Festlegen seiner "" Ereignismaske.  
  
 Verwenden Sie zum Festlegen der Ereignismaske für ein Rich--Steuerelement Edit die [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) Memberfunktion. Sie können die aktuelle Ereignismaske abrufen, für ein Rich-Steuerelement mithilfe Edit der [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) Memberfunktion.  
  
 In den folgenden Absätzen Liste mehrere bestimmte Benachrichtigungen und deren Verwendung:  
  
-   **EN_MSGFILTER** Behandlung der **EN_MSGFILTER** Benachrichtigung können Sie eine Klasse, die entweder die Rich-Text-Steuerelement oder das übergeordnete Fenster bearbeiten, filtern alle Tastatur und eine Maus Eingabe für das Steuerelement. Der Handler kann verhindern, dass die Tastatur- oder Maustastenzustand Nachricht verarbeitet wird, oder ändern Sie die Nachricht kann durch Ändern der angegebenen [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) Struktur.  
  
-   **EN_PROTECTED durch** behandeln die **EN_PROTECTED durch** benachrichtigungsmeldung erkennen, wenn der Benutzer versucht, geschützten Text zu ändern. Um einen Textbereich als geschützt zu kennzeichnen, können Sie die geschützten Zeichen Auswirkungen festlegen. Weitere Informationen finden Sie unter [Formatieren von Zeichen im Rich-Edit-Steuerelemente](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   **EN_DROPFILES** können Sie ermöglichen es dem Benutzer zum Löschen von Dateien in einem rich-Edit-Steuerelement durch die Verarbeitung der **EN_DROPFILES** Benachrichtigung. Das angegebene [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) Struktur enthält Informationen zu den Dateien, die gelöscht wird.  
  
-   **EN_SELCHANGE** eine Anwendung kann erkennen, wenn die aktuelle Auswahl, durch die Verarbeitung ändert der **EN_SELCHANGE** Benachrichtigung. Gibt an, die Nachricht eine [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) Struktur, die Informationen über die neue Auswahl enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

