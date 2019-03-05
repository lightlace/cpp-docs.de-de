---
title: Wann müssen Updatehandler aufgerufen werden?
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
ms.openlocfilehash: 4a52c147d1abf02b7c5e89abf868f87a07ab32cc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277585"
---
# <a name="when-update-handlers-are-called"></a>Wann müssen Updatehandler aufgerufen werden?

Nehmen wir an, dass der Benutzer den Mauszeiger über das Menü "Datei" klickt, die eine Nachricht WM_INITMENUPOPUP generiert. Die Framework Update-Mechanismus aktualisiert alle Elemente im Menü Datei zusammen, bevor im Menü wird angezeigt, damit der Benutzer ihn sehen kann.

Aktualisieren Sie zu diesem Zweck die Framework-Routen-Befehle für alle Menüelemente im Popupmenü entlang des standardbefehlsroutings. Befehlsziele für das routing haben die Möglichkeit, alle Menüelemente zu aktualisieren, indem Sie den Updatebefehl mit einer entsprechenden Meldungszuordnungseintrags übereinstimmende (des Formulars `ON_UPDATE_COMMAND_UI`) und eine "Update"-Funktion aufrufen. Daher werden für ein Menü mit sechs Menüelementen sechs Update-Befehle gesendet. Wenn ein Aktualisierungshandler für die Befehls-ID des Menüelements vorhanden ist, spricht man, um die Aktualisierung durchzuführen. Wenn dies nicht der Fall, das Framework überprüft das Vorhandensein eines Handlers für dieses Befehls-ID und aktiviert oder deaktiviert das Menüelement nach Bedarf.

Wenn das Framework nicht gefunden wird ein `ON_UPDATE_COMMAND_UI` Eintrag während Befehlsrouting es automatisch aktiviert das Benutzeroberflächen-Objekt liegt eine `ON_COMMAND` Eintrag an einer beliebigen Stelle mit derselben Befehls-ID. Andernfalls wird der Benutzeroberflächen-Objekt deaktiviert. Aus diesem Grund um sicherzustellen, dass ein Benutzeroberflächen-Objekt aktiviert ist, geben Sie einen Handler für den Befehl aus, den das Objekt generiert, oder geben Sie einen updatehandler für sie. Siehe die Abbildung im Thema [Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md).

Es ist möglich, deaktivieren Sie die Standard-Deaktivierung von Benutzeroberflächen-Objekten. Weitere Informationen finden Sie unter den [M_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) Member der Klasse `CFrameWnd` in die *MFC-Referenz*.

Menü-Initialisierung erfolgt automatisch im Framework auftritt, wenn die Anwendung eine WM_INITMENUPOPUP-Nachricht empfängt. Während Leerlaufschleife sucht das Framework an, das Befehlsrouting für Update-Handler der Schaltflächen auf dieselbe Weise wie für Menüs.

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)
