---
title: Benachrichtigungen von einem Rich-Edit-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928728093ff6e2150578c4ba48f2d8081620a48d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931143"
---
# <a name="notifications-from-a-rich-edit-control"></a>Benachrichtigungen von einem RichEdit-Steuerelement
Benachrichtigung Nachrichten Bericht Ereignisse, die Auswirkungen auf ein Rich-edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Sie können durch das übergeordnete Fenster verarbeitet werden oder mithilfe von Reflektion Nachricht vom Rich edit-Steuerelement selbst. Rich-Edit-Steuerelemente unterstützen alle die benachrichtigungsmeldungen mit Bearbeitungssteuerelementen sowie mehrere zusätzliche diejenigen verwendet. Sie können bestimmen, welche benachrichtigungsmeldungen ein rich-Edit-Steuerelement das übergeordnete Fenster sendet durch Festlegen seiner "" Ereignismaske.  
  
 Verwenden Sie zum Festlegen der Ereignismaske für ein Rich--Steuerelement Edit die [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) Memberfunktion. Sie können die aktuelle Ereignismaske abrufen, für ein Rich-Steuerelement mithilfe Edit der [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) Memberfunktion.  
  
 In den folgenden Absätzen Liste mehrere bestimmte Benachrichtigungen und deren Verwendung:  
  
-   EN_MSGFILTER durch Verarbeiten der EN_MSGFILTER-Benachrichtigung können einer Klasse entweder das rich-Edit-Steuerelement oder das übergeordnete Fenster, alle Tastatur- und Mauseingaben an das Steuerelement zu filtern. Der Handler kann verhindern, dass die Tastatur- oder Maustastenzustand Nachricht verarbeitet wird, oder ändern Sie die Nachricht kann durch Ändern der angegebenen [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) Struktur.  
  
-   EN_PROTECTED durch Behandeln der EN_PROTECTED-Benachrichtigung erkennen, wenn der Benutzer versucht, geschützten Text zu ändern. Um einen Textbereich als geschützt zu kennzeichnen, können Sie die geschützten Zeichen Auswirkungen festlegen. Weitere Informationen finden Sie unter [Formatieren von Zeichen im Rich-Edit-Steuerelemente](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   EN_DROPFILES Sie können den Benutzer, die Dateien in einem rich-Edit-Steuerelement zu löschen, indem Sie die Verarbeitung der benachrichtigungsmeldung EN_DROPFILES aktivieren. Das angegebene [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) Struktur enthält Informationen zu den Dateien, die gelöscht wird.  
  
-   EN_SELCHANGE eine Anwendung kann erkennen, wenn die aktuelle Auswahl ändert, durch die Verarbeitung der benachrichtigungsmeldung EN_SELCHANGE. Gibt an, die Nachricht eine [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) Struktur, die Informationen über die neue Auswahl enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

