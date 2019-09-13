---
title: Aktualisieren des Textes in der Statusleiste
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
ms.openlocfilehash: 20cd519f15fa9b218bca3dd1348659cfd0d5e473
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907640"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Aktualisieren des Textes in der Statusleiste

In diesem Artikel wird erläutert, wie Sie den Text ändern, der in einem MFC-Status Leistenbereich angezeigt wird. Eine Statusleiste – ein Fenster Objekt der Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md) – enthält mehrere Bereiche. Jeder Bereich ist ein rechteckiger Bereich der Statusleiste, der zum Anzeigen von Informationen verwendet werden kann. Viele Anwendungen zeigen z. b. den Status der FESTSTELL Sperre, der NUM-Sperre und anderer Schlüssel in den äußersten rechten Bereichen an. Anwendungen zeigen auch häufig informativen Text im linken Bereich an (Bereich 0), der manchmal auch als "Nachrichtenbereich" bezeichnet wird. Beispielsweise verwendet die Standard-MFC-Statusleiste den Bereich Meldung, um eine Zeichenfolge anzuzeigen, die das aktuell ausgewählte Menü Element oder die Symbolleisten Schaltfläche erläutert. Die Abbildung in [Status leisten](../mfc/status-bar-implementation-in-mfc.md) zeigt eine Status Leiste von einer vom Anwendungs-Assistenten erstellten MFC-Anwendung an.

Standardmäßig aktiviert MFC einen `CStatusBar` Bereich nicht, wenn er den Bereich erstellt. Um einen Bereich zu aktivieren, müssen Sie das ON_UPDATE_COMMAND_UI-Makro für jeden Bereich in der Statusleiste verwenden und die Bereiche aktualisieren. Da Bereiche keine WM_COMMAND-Nachrichten senden (Sie sind nicht wie Symbolleisten-Schaltflächen), müssen Sie den Code manuell eingeben.

Nehmen wir beispielsweise an, dass `ID_INDICATOR_PAGE` ein Bereich als Befehls Bezeichner und die aktuelle Seitenzahl in einem Dokument enthält. Im folgenden Verfahren wird beschrieben, wie ein neuer Bereich in der Statusleiste erstellt wird.

### <a name="to-make-a-new-pane"></a>So erstellen Sie einen neuen Bereich

1. Definieren Sie die Befehls-ID des Bereichs.

   Klicken Sie im Menü **Ansicht** auf **Ressourcenansicht**. Klicken Sie mit der rechten Maustaste auf die Projekt Ressource und dann auf **Ressourcen Symbole**. Klicken Sie im Dialogfeld Ressourcen Symbole auf `New`. Geben Sie einen Befehls-ID-Namen ein `ID_INDICATOR_PAGE`, z. b. Geben Sie einen Wert für die ID an, oder übernehmen Sie den Wert, der im Dialogfeld Ressourcen Symbole vorgeschlagen wird. Nehmen Sie z. `ID_INDICATOR_PAGE`b. für den Standardwert an. Schließen Sie das Dialogfeld Ressourcen Symbole.

1. Definieren Sie eine Standard Zeichenfolge, die im Bereich angezeigt werden soll.

   Wenn Ressourcenansicht geöffnet ist, doppelklicken Sie in dem Fenster, in dem die Ressourcentypen für die Anwendung aufgelistet werden, auf **Zeichen folgen Tabelle** . Wählen Sie im geöffneten Zeichen folgen- **Tabellen** -Editor im Menü **Einfügen** die Option **neue Zeichenfolge** aus. Wählen Sie die Befehls-ID Ihres Bereichs (z `ID_INDICATOR_PAGE`. b.) aus, und geben Sie einen Standard Zeichen folgen Wert ein, z.b. "page". Schließen Sie den Zeichen folgen-Editor. (Sie benötigen eine Standard Zeichenfolge, um einen Compilerfehler zu vermeiden.)

1. Fügen Sie dem *Indikator* Array den Bereich hinzu.

   In Datei-MainFrm. Cpp: Suchen Sie das Array " *Indikatoren* ". Dieses Array listet die Befehls-IDs für alle Indikatoren der Statusleiste in der Reihenfolge von links nach rechts auf. Geben Sie an der entsprechenden Stelle im Array die Befehls-ID Ihres Bereichs ein, wie hier `ID_INDICATOR_PAGE`gezeigt:

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

Die empfohlene Vorgehensweise zum Anzeigen von Text in einem Bereich besteht darin `SetText` , die Member- `CCmdUI` Funktion der-Klasse in einer Update Handler-Funktion für den Bereich aufzurufen. Beispielsweise können Sie eine ganzzahlige Variable *m_nPage* einrichten, die die aktuelle Seitenzahl enthält, und verwenden `SetText` , um den Text des Bereichs auf eine Zeichen folgen Version dieser Zahl festzulegen.

> [!NOTE]
>  Der `SetText` Ansatz wird empfohlen. Es ist möglich, diese Aufgabe auf etwas niedrigerer Ebene durch Aufrufen der `CStatusBar` Member-Funktion `SetPaneText`auszuführen. Trotzdem benötigen Sie trotzdem einen Update Handler. Ohne diesen Handler deaktiviert MFC automatisch den Bereich und löscht seinen Inhalt.

Im folgenden Verfahren wird gezeigt, wie Sie eine Update Handler-Funktion verwenden, um Text in einem Bereich anzuzeigen.

#### <a name="to-make-a-pane-display-text"></a>So machen Sie einen Fenster Anzeige Text

1. Fügen Sie einen Befehls Aktualisierungs Handler für den Befehl hinzu.

   Fügen Sie manuell einen Prototyp für den Handler hinzu, wie hier `ID_INDICATOR_PAGE` für (in mainfrm) gezeigt. H):

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. In der entsprechenden. Cpp-Datei, fügen Sie die Definition des Handlers hinzu, `ID_INDICATOR_PAGE` wie hier für (in mainfrm) gezeigt. Cpp):

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   Die letzten drei Zeilen dieses Handlers sind der Code, der Ihren Text anzeigt.

1. Fügen Sie in der entsprechenden Meldungs Zuordnung das ON_UPDATE_COMMAND_UI-Makro hinzu, wie `ID_INDICATOR_PAGE` hier für (in mainfrm) gezeigt. Cpp):

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

Wenn Sie den Wert der *m_nPage* -Element Variablen (der-Klasse `CMainFrame`) definieren, bewirkt dieses Verfahren, dass die Seitenzahl im Bereich während der Leerlauf Verarbeitung auf die gleiche Weise angezeigt wird, wie die Anwendung andere Indikatoren aktualisiert. Wenn *m_nPage* geändert wird, ändert sich die Anzeige während der nächsten Leerlauf Schleife.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Aktualisieren von Benutzeroberflächen Objekten (Aktualisieren von Symbolleisten-Schaltflächen und Menü Elementen als Programmbedingungen ändern)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>Siehe auch

[Implementieren der Statusleiste mit MFC](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar-Klasse](../mfc/reference/cstatusbar-class.md)
