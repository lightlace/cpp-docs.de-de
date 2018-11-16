---
title: Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 4c35a1efb1c93aecf17e8f57b9e96c033aa4334a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693183"
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

