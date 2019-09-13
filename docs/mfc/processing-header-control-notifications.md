---
title: Verarbeiten von Benachrichtigungen des Headersteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: bc811763fe3f4717b8baaeb4a23df1ae59bb1979
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908136"
---
# <a name="processing-header-control-notifications"></a>Verarbeiten von Benachrichtigungen des Headersteuerelements

Verwenden Sie in der Ansicht oder Dialogfeld Klasse den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um eine [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) -Handlerfunktion mit einer Switch-Anweisung für alle Header Steuerelemente ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) zu erstellen, die Sie behandeln möchten (siehe [Mapping von Nachrichten zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)). Benachrichtigungen werden an das übergeordnete Fenster gesendet, wenn der Benutzer auf ein Header Element klickt oder doppelklickt, einen unter Teiler zwischen Elementen zieht usw.

Die einem Header Steuerelement zugeordneten Benachrichtigungs Meldungen werden in der Windows SDK des [Header Steuer](/windows/win32/controls/header-control-reference) Elements aufgeführt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
