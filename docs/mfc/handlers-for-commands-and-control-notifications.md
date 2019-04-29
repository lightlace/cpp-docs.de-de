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
ms.openlocfilehash: 6c92660c67fa91c27bb094111cebfef57904cdc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358993"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Handler für Befehle und Steuerelementbenachrichtigungen

Es gibt keine Standardhandler für Befehle oder Steuerelemente-benachrichtigungsmeldungen aus. Aus diesem Grund sind Sie nur gemäß der Konvention, bei der Benennung Ihrer Handler für diese Kategorien von Nachrichten gebunden. Wenn Sie die Benachrichtigung Befehl oder das Steuerelement einen Handler zuordnen, schlägt im Eigenschaftenfenster einen Namen basierend auf den Befehlscode-ID oder Steuerelement-Benachrichtigung. Sie können akzeptieren den vorgeschlagenen Namen, ändern oder Ersetzen Sie ihn.

Konvention legt nahe, dass Sie Handler in beiden Kategorien für das Objekt für die Benutzeroberflächen-Namen, die sie darstellen. Daher könnte ein Handler für den Befehl "Ausschneiden", auf das Menü "Bearbeiten" genannt werden

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Da der Befehl "Ausschneiden" so häufig in Anwendungen implementiert wird, wird das Framework verfügt über vordefinierte die Befehls-ID für den Befehl "Ausschneiden" als **ID_EDIT_CUT**. Eine Liste mit allen vordefinierten Befehls-IDs finden Sie in der Datei AFXRES. H. Weitere Informationen finden Sie unter [Standardbefehle](../mfc/standard-commands.md).

Darüber hinaus empfiehlt Konvention einen Handler für die **BN_CLICKED** Benachrichtigung von der Schaltfläche "Meine Schaltfläche" den Namen

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Sie können mit diesem Befehl ID zuweisen **IDC_MY_BUTTON** , da es eine anwendungsspezifische Benutzeroberflächen-Objekt entspricht.

Beide Kategorien von Nachrichten akzeptieren keine Argumente und gibt keinen Wert zurück.

## <a name="see-also"></a>Siehe auch

[Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
