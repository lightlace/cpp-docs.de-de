---
title: Implementieren der MFC-Symbolleiste
ms.date: 11/04/2016
helpviewer_keywords:
- toolbars [MFC], creating
- buttons [MFC], MFC toolbars
- toolbars [MFC], docking
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- floating toolbars [MFC]
- toolbars [MFC], floating
- docking toolbars [MFC]
- bitmaps [MFC], toolbar
- toolbar controls [MFC]
- CToolBarCtrl class [MFC], implementing toolbars
- tool tips [MFC], enabling
- toolbars [MFC]
- toolbars [MFC], implementing MFC toolbars
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
ms.openlocfilehash: 55c43c47b93cd21d86293706fc7c3eb5145c39fd
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773176"
---
# <a name="mfc-toolbar-implementation"></a>Implementieren der MFC-Symbolleiste

Eine Symbolleiste ist eine [Steuerleiste](../mfc/control-bars.md) , die die Bitmapbilder von Steuerelementen enthält. Diese Bilder können sich wie Druckknöpfe, Kontrollkästchen oder Optionsfelder verhalten. MFC stellt die Klasse [CToolbar](../mfc/reference/ctoolbar-class.md) Symbolleisten zu verwalten.

Wenn Sie sie aktivieren, können Benutzer von MFC-Symbolleisten diese an den Rand eines Fensters andocken, oder an einer beliebigen Stelle im Anwendungsfenster "abdocken". MFC unterstützt keine anpassbaren Symbolleisten wie in der Entwicklungsumgebung.

MFC unterstützt auch QuickInfos: kleine Popupfenster, in denen der Zweck einer Symbolleistenschaltfläche beschrieben wird, wenn Sie die Maus über die Schaltfläche positionieren. Wenn der Benutzer eine Symbolleisten-Schaltfläche drückt, wird standardmäßig eine Statuszeichenfolge in der Statusleiste (falls vorhanden) angezeigt. Sie können die Aktualisierung der "aufleuchtenden" Statusleiste aktivieren, damit die Statuszeichenfolge angezeigt wird, wenn die Maus über die Schaltfläche positioniert wird, ohne dass sie gedrückt wird.

> [!NOTE]
>  Ab MFC 4.0 werden Symbolleisten und QuickInfo mit der Funktionalität von Windows 95 und höher anstelle der vorherigen, MFC-spezifischen Implementierung implementiert.

Für die Abwärtskompatibilität behält MFC die ältere symbolleistenimplementierung in Klasse `COldToolBar`. Beschreiben Sie die Dokumentation für frühere Versionen von MFC `COldToolBar` unter `CToolBar`.

Erstellen Sie die erste Symbolleiste im Programm, indem Sie die Symbolleistenoption im Anwendungs-Assistenten auswählen. Sie können auch weitere Symbolleisten erstellen.

Die folgenden werden in diesem Artikel eingeführt:

- [Symbolleisten-Schaltflächen](#_core_toolbar_buttons)

- [Andockbare und unverankerte Symbolleisten](#_core_docking_and_floating_toolbars)

- [Symbolleisten und QuickInfo](#_core_toolbars_and_tool_tips)

- [Die Klassen CToolBar und CToolBarCtrl](#_core_the_ctoolbar_and_ctoolbarctrl_classes)

- [Die Symbolleistenbitmap](#_core_the_toolbar_bitmap)

##  <a name="_core_toolbar_buttons"></a> Symbolleisten-Schaltflächen

Die Schaltflächen in einer Symbolleiste sind den Elementen in einem Menü analog. Beide Arten von Benutzeroberflächen-Objekten generieren Befehle, die das Programm bearbeitet, indem es Handlerfunktionen bereitstellt. Häufig duplizieren Symbolleisten-Schaltflächen die Funktionalität von Menübefehlen und stellen eine alternative Benutzeroberfläche mit derselben Funktionalität bereit. Solche Duplizierung wird einfach angeordnet, indem die Schaltfläche und das Menüelement die gleiche ID erhalten.

Sie können die Schaltflächen in einer Symbolleiste so erstellen, dass sie als Druckknöpfe, Kontrollkästchen oder Optionsfelder angezeigt werden und sich entsprechend verhalten. Weitere Informationen finden Sie in der Klasse [CToolBar](../mfc/reference/ctoolbar-class.md).

##  <a name="_core_docking_and_floating_toolbars"></a> Andockbare und unverankerte Symbolleisten

Eine MFC-Symbolleiste kann:

- fest entlang der Seite des übergeordneten Fensters geöffnet stehen.

- vom Benutzer gezogen und an einer oder mehreren Seiten des von Ihnen angegebenen übergeordneten Fensters "angedockt" oder angefügt werden.

- vom Rahmenfenster "abgedockt" oder gelöst werden und im eigenen kleinen Rahmenfenster angezeigt werden, sodass der Benutzer es an eine beliebige Position verschieben kann.

- im unverankerten Modus in der Größe verändert werden.

Weitere Informationen finden Sie im Artikel [andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md).

##  <a name="_core_toolbars_and_tool_tips"></a> Symbolleisten und QuickInfo

MFC-Symbolleisten können als "QuickInfo" angezeigt werden. Hierbei handelt es sich um kleine Fenster, die eine Kurztextbeschreibung mit dem Zweck einer Symbolleisten-Schaltfläche enthalten. Wenn der Benutzer die Maus über eine Symbolleisten-Schaltfläche bewegt, bieten die Popupfenster mit den QuickInfos einen Hinweis an. Weitere Informationen finden Sie im Artikel [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md).

##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> Die Klassen CToolBar und CToolBarCtrl

Sie verwalten die Symbolleisten der Anwendung über die Klasse [CToolBar](../mfc/reference/ctoolbar-class.md). Ab MFC 4.0 ist `CToolBar` erneut implementiert, sodass das allgemeine Steuerelement für Symbolleisten verwendet werden kann, das unter Windows 95 oder höher und Windows NT 3.51 oder höher verfügbar ist.

Diese Neuimplementierung führt zu weniger MFC-Code in Symbolleisten, da MFC die Betriebssystemunterstützung ausnutzt. Das Neuimplementierung verbessert auch die Funktionalität. Sie können `CToolBar` Memberfunktionen zum Bearbeiten von Symbolleisten, oder Sie erhalten einen Verweis auf die zugrunde liegende [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt aus, und rufen Sie seine Memberfunktionen für symbolleistenanpassung sowie zusätzliche Funktionen.

> [!TIP]
>  Wenn Sie in die ältere MFC-Implementierung von `CToolBar` investiert haben, ist diese Unterstützung weiterhin verfügbar. Finden Sie im Artikel [verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md).

Außerdem finden Sie im allgemeinen MFC-Beispiel [DOCKTOOL](../overview/visual-cpp-samples.md).

##  <a name="_core_the_toolbar_bitmap"></a> Die Symbolleistenbitmap

Ein erstelltes `CToolBar`-Objekt erstellt das Symbolleistenbild, indem es eine einzelne Bitmap lädt, das ein Bild für jede Schaltfläche enthält. Die Anwendungs-Assistent erstellt eine Standardbitmap für die Symbolleiste, die Sie anpassen können, mit dem Visual C++- [Symbolleisten-Editor](../windows/toolbar-editor.md).

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Grundlegendes über Symbolleisten](../mfc/toolbar-fundamentals.md)

- [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)

- [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)

- [Arbeiten mit dem Symbolleisten-Steuerelement](../mfc/working-with-the-toolbar-control.md)

- [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)

- Die [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Klassen

## <a name="see-also"></a>Siehe auch

[Symbolleisten](../mfc/toolbars.md)<br/>
[Symbolleisten-Editor](../windows/toolbar-editor.md)
