---
title: Anpassen von Tastatur und Maus
ms.date: 11/19/2018
helpviewer_keywords:
- customizations [MFC], keyboard and mouse (MFC Extensions)
- keyboard and mouse customizations (MFC Extensions)
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
ms.openlocfilehash: 55eaac9d800730f3a01dcdb2eef943eb48d147b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311155"
---
# <a name="keyboard-and-mouse-customization"></a>Anpassen von Tastatur und Maus

MFC ermöglicht, dem Benutzer der Anwendung anpassen, wie es sich um Tastatur- und Mauseingaben behandelt wird. Der Benutzer kann Tastatureingaben anpassen, indem Sie Befehle Tastenkombinationen zuweisen zu können. Der Benutzer kann auch die Mauseingabe anpassen, indem wählen Sie den Befehl aus, der ausgeführt werden soll, wenn der Benutzer in bestimmten Fenster der Anwendung doppelklickt. In diesem Thema wird erläutert, wie Sie die Eingabe für Ihre Anwendung anpassen.

In der **Anpassung** im Dialogfeld der Benutzer kann die benutzerdefinierte Steuerelemente für die Maus und Tastatur ändern. Um das Dialogfeld anzuzeigen, zeigt der Benutzer auf **anpassen** auf die **Ansicht** Menü und klickt dann auf **Symbolleisten und Andocken**. Klicken Sie im Dialogfeld klickt der Benutzer entweder der **Tastatur** Registerkarte oder die **Maus** Registerkarte.

## <a name="keyboard-customization"></a>Anpassung der Tastatur

Die folgende Abbildung zeigt die **Tastatur** Registerkarte die **Anpassung** Dialogfeld.

![Registerkarte "Tastatur" im Dialogfeld "anpassen"](../mfc/media/mfcnextkeyboardtab.png "Registerkarte \"Tastatur\" im Dialogfeld \"anpassen\"") <br/>
Tastatur-Registerkarte "Anpassung"

Der Benutzer interagiert mit der Registerkarte "Tastatur" zu einem Befehl eine oder mehrere Tastenkombinationen zuweisen. Die verfügbaren Befehle finden Sie auf der linken Seite der Registerkarte. Der Benutzer kann einen der verfügbaren Befehle im Menü auswählen. Nur Befehle im Menü können eine Tastenkombination zugeordnet werden. Nachdem der Benutzer eine neue Verknüpfung, gibt die **weisen** Schaltfläche aktiviert wird. Wenn der Benutzer diese Schaltfläche klickt, ordnet die Anwendung den ausgewählten Befehl diese Tastenkombination auftaucht.

Alle der aktuell zugewiesenen Tastenkombinationen werden im Listenfeld in der rechten Spalte aufgeführt. Benutzer kann auch einzelne Verknüpfungen auswählen und entfernen oder Zurücksetzen alle Zuordnungen für die Anwendung.

Wenn Sie diese Anpassung in Ihrer Anwendung unterstützen möchten, müssen Sie erstellen eine [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md) Objekt. Zum Erstellen einer `CKeyboardManager` Objekt, rufen Sie die Funktion [CWinAppEx::InitKeyboardManager](../mfc/reference/cwinappex-class.md#initkeyboardmanager). Diese Methode erstellt und initialisiert einen Tastatur-Manager. Wenn Sie eine Tastatur Manager manuell erstellen, noch müssen Sie aufrufen `CWinAppEx::InitKeyboardManager` initialisieren.

Wenn Sie den Assistenten zum Erstellen Ihrer Anwendung verwenden, wird der Assistent den Tastatur-Manager initialisiert. Nachdem Ihre Anwendung den Tastatur-Manager initialisiert wird, fügt das Framework eine **Tastatur** TAB-Taste zu der **Anpassung** Dialogfeld.

## <a name="mouse-customization"></a>Maus-Anpassung

Die folgende Abbildung zeigt die **Maus** Registerkarte die **Anpassung** Dialogfeld.

![Registerkarte "Maus" im Dialogfeld "anpassen"](../mfc/media/mfcnextmousetab.png "Registerkarte \"Maus\" im Dialogfeld \"anpassen\"") <br/>
Registerkarte "Maus-Anpassung"

Der Benutzer interagiert mit dieser Registerkarte können Sie ein Menü zuweisen Befehl aus, um die Maus, doppelklicken Sie auf Aktion. Der Benutzer eine Ansicht aus der linken Seite des Fensters ausgewählt und verwendet dann die Steuerelemente auf der rechten Seite, die Doppelklickaktion aus einen Befehl zugeordnet werden soll. Nachdem der Benutzer klickt auf **schließen**, führt die Anwendung den zugeordneten Befehl aus, wenn der Benutzer eine beliebige Stelle in der Ansicht doppelklickt.

Standardmäßig ist die Anpassung der Maus bei der Erstellung einer Anwendungs mithilfe des Assistenten nicht aktiviert.

#### <a name="to-enable-mouse-customization"></a>Um eine Maus Anpassung aktivieren

1. Initialisiert eine [CMouseManager](../mfc/reference/cmousemanager-class.md) Objekt durch Aufrufen von [CWinAppEx::InitMouseManager](../mfc/reference/cwinappex-class.md#initmousemanager).

1. Erhalten Sie einen Zeiger auf die Maus-Manager mit [CWinAppEx::GetMouseManager](../mfc/reference/cwinappex-class.md#getmousemanager).

1. Hinzufügen von Ansichten mit der Maus-Manager mithilfe der [CMouseManager::AddView](../mfc/reference/cmousemanager-class.md#addview) Methode. Dies gilt für jede Ansicht, die Sie mit der Maus-Manager hinzufügen möchten.

Nachdem Ihre Anwendung den Maus-Manager initialisiert wird, fügt das Framework die **Maus** TAB-Taste zu der **anpassen** Dialogfeld. Wenn Sie keine Ansichten hinzufügen, bewirkt den Zugriff auf die Registerkarte, dass eine nicht behandelte Ausnahme. Nach der Erstellung einer Liste der Ansichten, die **Maus** Registerkarte für den Benutzer verfügbar ist.

Wenn Sie eine neue Ansicht mit der Maus-Manager hinzufügen, geben Sie ihm eine eindeutige ID. Wenn Sie die Maus-Anpassung für ein Fenster unterstützen möchten, müssen Sie Verarbeiten der WM_LBUTTONDBLCLICK-Nachricht und rufen die [CWinAppEx::OnViewDoubleClick](../mfc/reference/cwinappex-class.md#onviewdoubleclick) Funktion. Wenn Sie diese Funktion aufrufen, ist einer der Parameter die ID für das Fenster an. Es ist die Verantwortung des Programmierers zu verfolgen die ID-Nummern und die Objekte, die zugeordnet werden.

## <a name="security-concerns"></a>Sicherheitsaspekte

Siehe [benutzerdefinierte Tools](../mfc/user-defined-tools.md), die Benutzer kann eine benutzerdefiniertes Tool-ID das Doppelklickereignis zuordnen. Wenn der Benutzer eine Ansicht doppelklickt, sieht die Anwendung für ein Tool, das die zugeordneten-ID übereinstimmt. Wenn die Anwendung ein übereinstimmendes Tool gefunden wird, führt er das Tool an. Wenn die Anwendung ein entsprechendes Tool finden kann, sendet er eine WM_COMMAND-Meldung mit der ID an die Ansicht, die doppelgeklickt wurde.

Die angepassten Einstellungen werden in der Registrierung gespeichert. Durch Bearbeiten der Registrierung, kann ein Angreifer eine gültige Benutzer-ID-Tool durch einen beliebigen Befehl ersetzen. Wenn der Benutzer eine Ansicht doppelklickt, verarbeitet die Ansicht den Befehl, den die Angreifer platziert. Dies kann zu unerwarteten und möglicherweise gefährliches Verhalten führen.

Darüber hinaus kann diese Art von Angriff Benutzer Schnittstelle Schutzmaßnahmen umgangen werden. Nehmen wir beispielsweise an, dass eine Anwendung das Drucken ist deaktiviert hat. D. h. in der Benutzeroberfläche der **Drucken** Menüs und Schaltflächen sind nicht verfügbar. Normalerweise wird verhindert, dass dies die Anwendung nicht gedruckt. Wenn ein Angreifer die Registrierung bearbeitet haben, ein Benutzer konnte jetzt konnte sendet jedoch den Druckbefehl direkt durch Doppelklicken auf die Ansicht umgehen die Elemente der Benutzeroberfläche, die nicht verfügbar sind.

Fügen Sie Code zum Schutz gegen diese Art von Angriff auf Ihre Anwendung Befehlshandler, um sicherzustellen, dass ein Befehl gültig ist, bevor er ausgeführt wird. Hängen Sie nicht von der Benutzeroberfläche, um zu verhindern, dass einen Befehl an die Anwendung gesendet werden.

## <a name="see-also"></a>Siehe auch

[Anpassung für MFC](../mfc/customization-for-mfc.md)<br/>
[CKeyboardManager-Klasse](../mfc/reference/ckeyboardmanager-class.md)<br/>
[CMouseManager-Klasse](../mfc/reference/cmousemanager-class.md)<br/>
[Sicherheitsauswirkungen der Anpassung](../mfc/security-implications-of-customization.md)
