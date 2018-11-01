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
ms.openlocfilehash: 0c6691f37a1b0754835aba5c09d251c4986c4fb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592538"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Aktualisieren des Textes in der Statusleiste

In diesem Artikel wird erläutert, wie zum Ändern des Texts, die in einer MFC-Statusleistenbereich angezeigt wird. Eine Statusleiste, ein Window-Objekt der Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md) – enthält verschiedene "Bereiche". Jeder Bereich ist ein rechteckiger Bereich der Statusleiste für die Sie verwenden können, um Informationen anzuzeigen. Viele Anwendungen werden z. B. den Status der FESTSTELLTASTE, NUM- und andere Schlüssel in den Bereichen ganz rechts angezeigt. Anwendungen auch häufig informative Text in der ganz linke Bereich (Bereich 0) bezeichnet die "Bereich"Meldung "." angezeigt. Beispielsweise verwendet die standardmäßigen MFC-Statusleiste den Bereich "Meldung", um eine Zeichenfolge, die erläutert, der aktuell ausgewähltes oder eine Symbolleisten-Schaltfläche anzuzeigen. In der Abbildung in [Statusleisten](../mfc/status-bar-implementation-in-mfc.md) zeigt eine Statusleiste, die von einer Anwendungs-Assistenten erstellten MFC-Anwendung.

MFC wird standardmäßig nicht aktiviert eine `CStatusBar` Bereich, wenn es sich um den Bereich erstellt. Um einen Bereich zu aktivieren, müssen Sie verwenden die ON_UPDATE_COMMAND_UI-Makro für jeden Bereich auf der Statusleiste und aktualisieren die Bereiche. Da Bereiche nicht WM_COMMAND-Meldungen senden (was nicht wie Schaltflächen der Symbolleiste), müssen Sie den Code manuell eingeben.

Nehmen wir beispielsweise an, die einen Bereich hat `ID_INDICATOR_PAGE` als die Befehls-ID, und dass sie die aktuelle Seitenzahl in einem Dokument enthält. Das folgende Verfahren beschreibt, wie erstellen Sie einen neuen Bereich in der Statusleiste angezeigt wird.

### <a name="to-make-a-new-pane"></a>Um einen neuen Bereich zu machen.

1. Definieren Sie im Bereich der Befehls-ID.

   Auf der **Ansicht** Menü klicken Sie auf **Ressourcenansicht**. Mit der rechten Maustaste der Projektressource ein, und klicken Sie auf **Ressourcensymbole**. Klicken Sie in das Dialogfeld "Ressourcensymbole" `New`. Geben Sie einen Namen der Befehls-ID: z.B. `ID_INDICATOR_PAGE`. Geben Sie einen Wert für die ID, oder übernehmen Sie den Wert, der im Dialogfeld "Ressourcensymbole" empfohlen. Beispielsweise `ID_INDICATOR_PAGE`, übernehmen Sie den Standardwert. Schließen Sie das Dialogfeld "Ressourcensymbole".

1. Definieren Sie eine Standardzeichenfolge, die im Bereich angezeigt.

   Ressourcenansicht öffnen, und doppelklicken Sie auf **Zeichenfolgentabelle** im Fenster, in der Ressourcentypen, die für Ihre Anwendung aufgeführt. Mit der **Zeichenfolgentabelle** Editor geöffnet ist, wählen Sie **neue Zeichenfolge** aus der **einfügen** Menü. Wählen Sie im Fenster Eigenschaften die Befehls-ID des Bereichs (z. B. `ID_INDICATOR_PAGE`), und geben Sie einen Standardwert, wie z. B. "Page". Die Zeichenfolgen-Editor zu schließen. (Sie benötigen eine Standardzeichenfolge aus, um einen Compilerfehler zu vermeiden.)

1. Fügen Sie den Bereich, um die *Indikatoren* Array.

   In der Datei MAINFRM. CPP, suchen Sie die *Indikatoren* Array. Dieses Array enthält Befehls-IDs für alle Indikatoren für die Statusleiste, in der Reihenfolge von links nach rechts. Geben Sie an der entsprechenden Stelle im Array, Befehls-ID des Bereichs, wie hier gezeigt für `ID_INDICATOR_PAGE`:

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

Die empfohlene Methode zum Anzeigen von Text in einem Bereich wird zum Aufrufen der `SetText` Memberfunktion der Klasse `CCmdUI` in einer Update-Handler-Funktion für den Bereich. Angenommen, Sie möchten eine ganzzahlige Variable einrichten *M_nPage* , enthält die aktuelle Seitenzahl und die Verwendung `SetText` auf eine Zeichenfolgenversion der diese Zahl im Bereich des Texts fest.

> [!NOTE]
>  Die `SetText` Ansatz wird empfohlen. Es ist möglich, führen Sie hierzu eine etwas niedrigere Ebene durch Aufrufen der `CStatusBar` Memberfunktion `SetPaneText`. Trotzdem benötigen Sie weiterhin einen updatehandler. Ohne einen solchen Handler für den Bereich deaktiviert MFC automatisch im Bereich sein Inhalt gelöscht.

Das folgende Verfahren zeigt, wie eine Update-Handler-Funktion, die zum Anzeigen von Text in einem Bereich verwendet wird.

#### <a name="to-make-a-pane-display-text"></a>Um einen Bereich, Anzeigen von Text zu machen.

1. Fügen Sie ein Update-Befehlshandler für den Befehl hinzu.

   Fügen Sie einen Prototyp für den Handler, manuell hinzu, wie hier gezeigt für `ID_INDICATOR_PAGE` (in MAINFRM. H):

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. In den entsprechenden. CPP hinzufügen. der Handler die Definition wie folgt für `ID_INDICATOR_PAGE` (in MAINFRM. CPP):

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   Die letzten drei Zeilen von diesem Handler werden der Code, der den Text wird angezeigt.

1. Fügen Sie in der entsprechenden meldungszuordnung, die ON_UPDATE_COMMAND_UI-Makro wie folgt für `ID_INDICATOR_PAGE` (in MAINFRM. CPP):

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

Nachdem Sie den Wert des definiert die *M_nPage* Membervariable (Klasse `CMainFrame`), dieses Verfahren führt dazu, dass die Nummer der Seite im Bereich während der Verarbeitung von im Leerlauf auf die gleiche Weise angezeigt werden, dass die Anwendung andere Indikatoren aktualisiert. Wenn *M_nPage* Änderungen, die anzeigeänderungen, während der nächsten Leerlaufschleife.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Aktualisieren von Benutzeroberflächenobjekten (Gewusst wie: Aktualisieren von Symbolleisten-Schaltflächen und Menüelemente als Programm Bedingungen sich ändern)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>Siehe auch

[Implementieren der Statusleiste mit MFC](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar-Klasse](../mfc/reference/cstatusbar-class.md)
