---
title: Definieren eines Meldungshandlers für eine reflektierte Meldung
ms.date: 09/07/2019
f1_keywords:
- vc.codewiz.defining.msg.msghandler
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
ms.openlocfilehash: 1e38c63464cacf445688a1d431a65af21eac86f4
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907932"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Definieren eines Meldungshandlers für eine reflektierte Meldung

Nachdem Sie eine neue MFC-Steuerelement Klasse erstellt haben, können Sie Meldungs Handler dafür definieren. Reflektierte Meldungs Handler ermöglichen es ihrer Steuerelement Klasse, ihre eigenen Nachrichten zu verarbeiten, bevor die Nachricht vom übergeordneten Element empfangen wird. Sie können die MFC [CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) -Funktion verwenden, um Nachrichten von Ihrem Steuerelement an ein übergeordnetes Fenster zu senden.

Mit dieser Funktion können Sie z. b. ein Listenfeld erstellen, das sich selbst neu zeichnet, anstatt sich auf das übergeordnete Fenster zu verlassen (der Besitzer wird gezeichnet). Weitere Informationen zu reflektierten Meldungen finden Sie unter [Behandeln reflektierter Nachrichten](../../mfc/handling-reflected-messages.md).

Zum Erstellen eines [ActiveX-Steuer](../../mfc/activex-controls-on-the-internet.md) Elements mit der gleichen Funktionalität müssen Sie ein Projekt für das ActiveX-Steuerelement erstellen.

> [!NOTE]
>  Mit dem Klassen-Assistenten können Sie keine reflektierte Nachricht (OCM_-*Meldung*) für ein ActiveX-Steuerelement hinzufügen, wie unten beschrieben. Sie müssen diese Nachrichten manuell hinzufügen.

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-class-wizard"></a>So definieren Sie einen Meldungs Handler für eine reflektierte Nachricht vom Klassen-Assistenten

1. Fügen Sie Ihrem MFC-Projekt ein Steuerelement hinzu, z. b. eine Liste, ein Grund leisten-Steuerelement, eine Symbolleiste oder ein Struktur Steuerelement.

1. Klicken Sie in Klassenansicht auf den Namen der Steuerelement Klasse.

1. Im [Klassen-Assistenten](mfc-class-wizard.md)wird der Name der Steuerelement Klasse in der Liste **Klassenname** angezeigt.

1. Klicken Sie auf die Registerkarte **Meldungen** , um die dem Steuerelement hinzu zufügenden Windows-Meldungen anzuzeigen.

1. Wählen Sie die reflektierte Meldung aus, für die Sie einen Handler definieren möchten. Reflektierte Nachrichten werden mit einem Gleichheitszeichen (=) markiert.

1. Klicken Sie in der rechten Spalte des Klassen-Assistenten auf die Zelle, um den vorgeschlagenen Namen des Handlers als \<Add >*HandlerName*anzuzeigen. (Beispielsweise schlägt \<der **= WM_CTLCOLOR** -Meldungs Handler Add >**CtlColor**) vor.

1. Klicken Sie auf den vorgeschlagenen Namen, um ihn zu akzeptieren. Der Handler wird dem Projekt hinzugefügt.

1. Wiederholen Sie die Schritte 4 bis 7, um einen Meldungs Handler zu bearbeiten oder zu löschen. Klicken Sie auf die Zelle mit dem Namen des Handlers, um Sie zu bearbeiten oder zu löschen.

## <a name="see-also"></a>Siehe auch

[Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigate-code-cpp.md)
