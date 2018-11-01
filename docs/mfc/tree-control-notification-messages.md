---
title: Benachrichtigungsmeldungen von Struktursteuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: e187e08f894eeac37c8ad27aea45a1c8568c8a9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508175"
---
# <a name="tree-control-notification-messages"></a>Benachrichtigungsmeldungen von Struktursteuerelementen

Ein Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet die folgenden benachrichtigungsmeldungen als WM_NOTIFY-Meldungen:

|Benachrichtigungsmeldung|Beschreibung|
|--------------------------|-----------------|
|TVN_BEGINDRAG|Signalisiert den Start eines Drag & Drop-Vorgangs|
|TVN_BEGINLABELEDIT|Signalisiert den Start des direktes Bezeichnung bearbeiten|
|TVN_BEGINRDRAG|Signalisiert den Start eines Drag & Drop-Vorgangs, mit der rechten Maustaste|
|TVN_DELETEITEM|Signalisiert das Löschen eines bestimmten Elements|
|TVN_ENDLABELEDIT|Signalisiert das Ende der Bezeichnung bearbeiten|
|TVN_GETDISPINFO|Fordert Informationen, dass das Strukturansicht-Steuerelement erforderlich, zum Anzeigen eines Elements ist|
|TVN_ITEMEXPANDED|Signalisiert, dass ein übergeordnetes Element der Liste der untergeordneten Elemente erweitert oder reduziert wurde.|
|TVN_ITEMEXPANDING|Signalisiert, die dass ein übergeordnetes Element der Liste der untergeordneten Elemente ist dabei, erweitert oder reduziert werden|
|TVN_KEYDOWN|Signalisiert ein Tastaturereignis|
|EINE TVN_SELCHANGED|Signale, die die Auswahl von einem Element zum anderen geändert hat|
|TVN_SELCHANGING|Signalisiert, die dass die Auswahl ist von einem Element in eine andere geändert wird|
|TVN_SETDISPINFO|Benachrichtigung zum Aktualisieren der Informationen für ein Element verwaltet|

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

