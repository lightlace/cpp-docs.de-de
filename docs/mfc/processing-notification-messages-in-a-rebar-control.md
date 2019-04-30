---
title: Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 8ac225802bd1d0a0a4b0f30e017fa677f1072fd3
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339627"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement

Erstellen Sie in der übergeordneten Klasse des Infoleisten-Steuerelements, einer `OnChildNotify` Handlerfunktion mit einer Switch-Anweisung für ein beliebiges Grundleisten-Steuerelement (`CReBarCtrl`) benachrichtigungsmeldungen, die Sie behandeln möchten. Benachrichtigungen werden an das übergeordnete Fenster gesendet, wenn der Benutzer Objekte über das Grundleistensteuerelement, Änderungen das Layout der rebarbereichen löscht bands zieht-Infoleisten-Steuerelements, und so weiter.

Die folgenden benachrichtigungsmeldungen können vom Objekt Infoleisten-Steuerelement gesendet werden:

- RBN_AUTOSIZE gesendet von einem Infoleisten-Steuerelement (erstellt mit dem Stil RBS_AUTOSIZE) Wenn die Infoleiste automatisch seine Größe selbst ändert.

- RBN_BEGINDRAG gesendet von einem Infoleisten-Steuerelement, wenn der Benutzer beginnt, ziehen ein Band.

- RBN_CHILDSIZE gesendet von einem Infoleisten-Steuerelement beim Ändern der Größe eines untergeordneten Fensters des Bands.

- RBN_DELETEDBAND wird gesendet, von einem Infoleisten-Steuerelement, nachdem ein Band gelöscht wurde.

- RBN_DELETINGBAND wird gesendet, von einem Infoleisten-Steuerelement, wenn ein Band gelöscht werden soll.

- RBN_ENDDRAG gesendet von einem Infoleisten-Steuerelement, wenn der Benutzer den Ziehvorgang für ein Band.

- RBN_GETOBJECT wird gesendet, von einem Infoleisten-Steuerelement (erstellt mit dem Stil RBS_REGISTERDROP) Wenn ein Objekt über ein Band in das Steuerelement gezogen wird.

- RBN_HEIGHTCHANGE wird gesendet, von einem Grundleisten-Steuerelement, wenn seine Höhe geändert wurde.

- RBN_LAYOUTCHANGED wird gesendet, von einem Grundleisten-Steuerelement, wenn der Benutzer das Layout der Bänder des Steuerelements ändert.

Weitere Informationen zu dieser Benachrichtigungen, finden Sie unter [Grundleisten-Steuerelementverweis](/windows/desktop/controls/rebar-control-reference) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
