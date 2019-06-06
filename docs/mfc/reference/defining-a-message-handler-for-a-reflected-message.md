---
title: Definieren eines Meldungshandlers für eine reflektierte Meldung
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.defining.msg.msghandler
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
ms.openlocfilehash: 970dd7072cb8391d76d39536e442d5aab8e0f61d
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741602"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Definieren eines Meldungshandlers für eine reflektierte Meldung

Nachdem Sie eine neue Klasse von MFC-Steuerelements erstellt haben, können Sie Meldungshandler dafür definieren. Reflektierte Meldung-Handler können eine Klasse, eine eigene Nachrichten zu verarbeiten, bevor die Nachricht vom übergeordneten Element empfangen wird. Sie können die MFC-Bibliothek verwenden [Funktion CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) Funktion zum Senden von Nachrichten über das Steuerelement für ein übergeordnetes Fenster.

Erstellen Sie mit dieser Funktionalität, Sie z. B. könnten, ein Listenfeld, die gezeichnet wird, statt Sie zu der das übergeordnete Fenster, ist dies der Fall ist (Ownerdrawn). Weitere Informationen zu reflektierter Meldungen, finden Sie unter [wiedergegeben Nachrichten behandeln](../../mfc/handling-reflected-messages.md).

Zum Erstellen einer [ActiveX-Steuerelement](../../mfc/activex-controls-on-the-internet.md) mit derselben Funktionalität, müssen Sie ein Projekt für das ActiveX-Steuerelement erstellen.

> [!NOTE]
>  Sie können keine reflektierte Meldung hinzufügen (OCM*Nachricht*) mithilfe des Eigenschaftenfensters für ein ActiveX-steuern, wie unten beschrieben. Sie müssen diese Nachrichten manuell hinzufügen.

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>Zum Definieren eines meldungshandlers für eine reflektierte Meldung aus dem Fenster "Eigenschaften"

1. Fügen Sie ein Steuerelement, z. B. eine Liste, einem Grundleisten-Steuerelement, einer Symbolleiste oder ein Strukturansicht-Steuerelement zu einem MFC-Projekt hinzu.

1. Klicken Sie in der Klassenansicht auf den Namen der Steuerelementklasse.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), Klassennamen des Steuerelements angezeigt wird, der **Klassenname** Liste.

1. Klicken Sie auf die **Nachrichten** Schaltfläche zur Anzeige der Windows-Meldungen, die auf dem Steuerelement hinzugefügt.

1. Bildlauf nach unten in der Liste der Nachrichten im Fenster Eigenschaften, bis Sie sehen, dass die Überschrift **reflektiert**. Klicken Sie alternativ auf die **Kategorien** Schaltfläche, und reduzieren Sie die Ansicht finden Sie unter den **reflektiert** Überschrift.

1. Wählen Sie die reflektierte Meldung, die für die Sie einen Ereignishandler definieren möchten. Reflektierte Meldungen werden mit einem Gleichheitszeichen (=) markiert.

1. Klicken Sie auf die Zelle in der rechten Spalte im Fenster Eigenschaften den vorgeschlagenen Namen des Handlers als anzuzeigende \<hinzufügen >*HandlerName*. (Z. B. die **= WM_CTLCOLOR** Meldungshandler schlägt \<hinzufügen >**CtlColor vor**).

1. Klicken Sie auf den vorgeschlagenen Namen zu akzeptieren. Der Handler wird dem Projekt hinzugefügt.

   Handler für Namen, die Sie hinzugefügt haben, werden in der rechten Spalte des Fensters reflektierter Meldungen angezeigt.

9. Zum Bearbeiten oder Löschen eines meldungshandlers, wiederholen Sie die Schritte 4 bis 7. Klicken Sie auf die Zelle mit dem Namen des Handlers bearbeiten oder löschen, und klicken Sie auf die entsprechende Aufgabe.

## <a name="see-also"></a>Siehe auch

[Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigate-code-cpp.md)
