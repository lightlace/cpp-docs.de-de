---
title: Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 044cef644f746f7cb70944805882bd8e2f2806b4
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908107"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen

Wenn Benutzer mit dem erweiterten Kombinationsfeld interagieren, sendet das Steuerelement (`CComboBoxEx`) Benachrichtigungen an sein übergeordnetes Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer z. b. die Dropdown Liste aktiviert oder in das Bearbeitungsfeld des Steuer Elements klickt, wird die CBEN_BEGINEDIT-Benachrichtigung gesendet.

Verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um der übergeordneten Klasse Benachrichtigungs Handler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.

In der folgenden Liste sind die verschiedenen Benachrichtigungen beschrieben, die vom erweiterten Kombinationsfeld-Steuerelement gesendet werden.

- CBEN_BEGINEDIT wird gesendet, wenn der Benutzer die Dropdown Liste aktiviert oder in das Bearbeitungsfeld des Steuer Elements klickt.

- CBEN_DELETEITEM gesendet, wenn ein Element gelöscht wurde.

- CBEN_DRAGBEGIN wird gesendet, wenn der Benutzer mit dem Ziehen des Bilds des Elements beginnt, das im Bearbeitungsbereich des Steuer Elements angezeigt wird.

- CBEN_ENDEDIT wird gesendet, wenn der Benutzer einen Vorgang innerhalb des Bearbeitungs Felds abgeschlossen hat oder ein Element aus der Dropdown Liste des Steuer Elements ausgewählt hat.

- CBEN_GETDISPINFO gesendet, um Anzeigeinformationen zu einem Rückruf Element abzurufen.

- CBEN_INSERTITEM wird gesendet, wenn ein neues Element in das Steuerelement eingefügt wurde.

## <a name="see-also"></a>Siehe auch

[Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
