---
title: Handler für Befehle und Steuerelementbenachrichtigungen
ms.date: 11/04/2016
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
ms.openlocfilehash: 43b6a517b680a5f6ff092337fbf3d90dd0115dd7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907970"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Handler für Befehle und Steuerelementbenachrichtigungen

Es sind keine Standard Handler für Befehle oder Steuerelement Benachrichtigungs Meldungen vorhanden. Daher sind Sie nur nach Konvention gebunden, wenn Sie Ihre Handler für diese Nachrichten Kategorien benennen. Wenn Sie den Befehl oder die Steuerelement Benachrichtigung einem Handler zuordnen, schlägt der [Klassen-Assistent](reference/mfc-class-wizard.md) auf der Grundlage der Befehls-ID oder des Steuerelement Benachrichtigungs Codes einen Namen vor. Sie können den vorgeschlagenen Namen akzeptieren, ändern oder ersetzen.

Die Konvention schlägt vor, dass Sie Handler in beiden Kategorien für das Benutzeroberflächen Objekt benennen, das Sie darstellen. Daher kann ein Handler für den Befehl "Ausschneiden" im Menü "Bearbeiten" benannt werden.

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Da der Befehl "Ausschneiden" in Anwendungen so häufig implementiert ist, definiert das Framework die Befehls-ID für den Befehl "Ausschneiden" als " **ID_EDIT_CUT**". Eine Liste aller vordefinierten Befehls-IDs finden Sie in der Datei "AFXRES". Micha. Weitere Informationen finden Sie unter [Standard Befehle](../mfc/standard-commands.md).

Außerdem schlägt die Konvention vor, dass ein Handler für die **BN_CLICKED** -Benachrichtigungs Meldung von einer Schaltfläche mit der Bezeichnung "Meine Schaltfläche" den Namen hat.

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Sie können diesen Befehl der ID **IDC_MY_BUTTON** zuweisen, da er einem anwendungsspezifischen Benutzerschnittstellen Objekt entspricht.

Beide Nachrichten Kategorien akzeptieren keine Argumente und geben keinen Wert zurück.

## <a name="see-also"></a>Siehe auch

[Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
