---
title: QuickInfos für die Symbolleiste
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
ms.openlocfilehash: 4582b03844e1be3d4cf70bcc3fff1c3b66119ae3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351773"
---
# <a name="toolbar-tool-tips"></a>QuickInfos für die Symbolleiste

QuickInfos sind kleine Popupfenster, für die kurze Beschreibung des Zwecks für eine Symbolleisten-Schaltfläche werden angezeigt, wenn Sie die Maus über eine Schaltfläche für eine bestimmte Zeitspanne positionieren. Wenn Sie eine Anwendung mit der Anwendungs-Assistenten, die eine Symbolleiste hat erstellen, ist Tip-toolunterstützung für Sie bereitgestellt. Dieser Artikel beschreibt beide den Tipp toolunterstützung erstellt, indem der Anwendungs-Assistent und das Hinzufügen von Tip-toolunterstützung für Ihre Anwendung.

Dieser Artikel behandelt Folgendes:

- [Aktivieren von QuickInfos](#_core_activating_tool_tips)

- [Statusleistenupdates](#_core_fly_by_status_bar_updates)

##  <a name="_core_activating_tool_tips"></a> Aktivieren von QuickInfos

Um QuickInfos in Ihrer Anwendung zu aktivieren, müssen Sie zwei Dinge tun:

- Die anderen Formate den CBRS_TOOLTIPS-Stil hinzugefügt (z. B. WS_CHILD, WS_VISIBLE und andere **CBRS_** Stile) übergeben, als die *DwStyle* Parameter, um die [Symbolleistenformate](../mfc/reference/ctoolbar-class.md#create) Funktion oder im [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle).

- Wie im folgenden Verfahren beschrieben, fügen Sie die Symbolleiste QuickInfo-Text, getrennt durch ein Zeilenumbruchzeichen ('\n'), auf die Zeichenfolgenressource, die die Eingabeaufforderung für die Befehle der Hilfesymbolleiste enthält. Die Zeichenfolgenressource gibt die ID des der Symbolleisten-Schaltfläche.

#### <a name="to-add-the-tool-tip-text"></a>Um den QuickInfo-Text hinzuzufügen.

1. Öffnen Sie auf die Symbolleiste in der Symbolleisten-Editor bearbeiten werden, die **Eigenschaften von Symbolleisten-Schaltfläche** Fenster für eine bestimmte Schaltfläche.

1. In der **Eingabeaufforderung** geben den Text in der QuickInfo für die Schaltfläche angezeigt werden sollen.

> [!NOTE]
>  Festlegen des Texts, wie eine Eigenschaft für eine Symbolleisten-Editor die vorherige Prozedur ersetzt, in der Sie mussten zu öffnen Sie und bearbeiten Sie die Zeichenfolgenressource.

Verfügt eine Steuerleiste mit QuickInfos aktiviert untergeordnete Steuerelemente darauf platziert, wird die Steuerleiste eine QuickInfo für jedes untergeordnete Steuerelement auf der Steuerleiste angezeigt werden soll, solange sie die folgenden Kriterien erfüllt:

- Die ID des Steuerelements ist nicht - 1.

- Der Zeichenfolgentabelle Eintrag mit derselben ID wie das untergeordnete Steuerelement in der Ressourcendatei hat es sich um eine Zeichenfolge der Tool-Tipps.

##  <a name="_core_fly_by_status_bar_updates"></a> Statusleiste Flyby-Updates

Eine Funktion, die im Zusammenhang mit QuickInfos ist "Flyby" Statusleiste aktualisiert. Standardmäßig wird die Nachricht in der Statusleiste nur eine bestimmten Symbolleisten-Schaltfläche beschrieben, wenn die Schaltfläche aktiviert wird. Dazu CBRS_FLYBY in der Liste der Stile, die an `CToolBar::Create`, Sie haben diese aktualisiert, wenn der Mauszeiger über der Symbolleiste bewegt werden, ohne Aktivierung tatsächlich auf die Schaltfläche mit den Nachrichten.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Implementieren der MFC-Symbolleiste (Übersicht die Übersichtsinformationen auf der Symbolleiste)](../mfc/mfc-toolbar-implementation.md)

- [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)

- Die [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Klassen

- [Arbeiten mit dem Symbolleisten-Steuerelement](../mfc/working-with-the-toolbar-control.md)

- [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Siehe auch

[Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)
