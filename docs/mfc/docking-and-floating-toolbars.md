---
title: Andockbare und unverankerte Symbolleisten
ms.date: 11/04/2016
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
helpviewer_keywords:
- size [MFC], toolbars
- size
- frame windows [MFC], toolbar docking
- CBRS_ALIGN_ANY constant [MFC]
- palettes, floating
- toolbars [MFC], docking
- CBRS_SIZE_DYNAMIC constant [MFC]
- floating toolbars
- toolbars [MFC], size
- toolbars [MFC], floating
- fixed-size toolbars
- CBRS_SIZE_FIXED constant [MFC]
- toolbar controls [MFC], wrapping
- toolbars [MFC], wrapping
- floating palettes
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
ms.openlocfilehash: 01450dca56ad662c8db0a35f89749c4a288109b3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768133"
---
# <a name="docking-and-floating-toolbars"></a>Andockbare und unverankerte Symbolleisten

Die Microsoft Foundation Class-Bibliothek unterstützt die andockbare Symbolleisten. Eine andockbare Symbolleiste kann angefügt oder angedockt sind, klicken Sie auf jeder Seite des übergeordneten Fensters, oder es kann getrennt sein, in einem eigenen kleinen Rahmenfenster Fenster abgedockt. In diesem Artikel wird erläutert, wie andockbare Symbolleisten in Ihren Anwendungen verwendet wird.

Wenn Sie den Assistenten zum Generieren des Grundgerüsts Ihrer Anwendung verwenden, werden Sie aufgefordert, auszuwählen, ob das andockbare Symbolleisten angezeigt werden soll. Standardmäßig generiert der Anwendungs-Assistent den Code, der erforderlich ist, eine andockbare Symbolleiste in Ihrer Anwendung drei Aktionen ausführt:

- [Aktivieren Sie das Andocken in einem Rahmenfenster](#_core_enabling_docking_in_a_frame_window).

- [Aktivieren Sie das Andocken, einer Symbolleiste](#_core_enabling_docking_for_a_toolbar).

- [Symbolleiste (an das Rahmenfenster) Andocken](#_core_docking_the_toolbar).

Wenn eines dieser Schritte fehlen, wird Ihre Anwendung eine Standardsymbolleiste angezeigt. Die letzten beiden Schritte müssen für jede andockbare Symbolleiste in Ihrer Anwendung ausgeführt werden.

Andere in diesem Artikel behandelten Themen umfassen:

- [Lösen der Symbolleiste](#_core_floating_the_toolbar)

- [Dynamisches Ändern der Größe der Symbolleiste](#_core_dynamically_resizing_the_toolbar)

- [Einstellung Wrap Positionen für eine Symbolleiste mit festem Format](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

Finden Sie im allgemeinen MFC-Beispiel [DOCKTOOL](../overview/visual-cpp-samples.md) Beispiele.

##  <a name="_core_enabling_docking_in_a_frame_window"></a> Aktivieren des Andockens in einem Rahmenfenster

Symbolleisten an ein Framefenster Andocken zu können, muss die Rahmenfenster (oder das Ziel) aktiviert sein, um Andocken zu ermöglichen. Dies erfolgt mithilfe der [EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) -Funktion, die eine akzeptiert *DWORD* Parameter, der einen Satz von Format ist bits, der angibt, welcher Seite des Rahmenfensters Andocken angenommen. Wenn eine Symbolleiste ist angedockt werden und es gibt mehrere Seiten, die es angedockt werden kann, die Seiten in der an übergebene Parameter `EnableDocking` werden verwendet, in der folgenden Reihenfolge: oben, unten, links, rechts. Wenn Sie in der Lage sein möchten Steuerelement angedockt Balken überall, übergeben Sie **CBRS_ALIGN_ANY** zu `EnableDocking`.

##  <a name="_core_enabling_docking_for_a_toolbar"></a> Aktivieren des Andockens einer Symbolleiste

Nachdem Sie das Ziel für das Andocken vorbereitet haben, müssen Sie die Symbolleiste (oder die Quelle) in ähnlicher Weise vorbereiten. Rufen Sie [CControlBar:: EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking) für jede Symbolleiste, das Sie andocken möchten, Angeben des Ziels Seiten So docken Sie an, die auf die Symbolleiste sollte. Wenn keines der Seiten, die im Aufruf angegebenen `CControlBar::EnableDocking` entsprechen die Seiten, die zum Rahmenfenster Andocken aktiviert, die Symbolleiste kann nicht angedockt – es wird "float". Sobald es abgedockt wurde hat, bleibt er eine unverankerte Symbolleiste, die nicht an das Rahmenfenster andocken.

Wenn Sie der gewünschten Effekt dauerhaft verankerte Symbolleiste ist, rufen `EnableDocking` mit dem Parameter 0. Rufen Sie anschließend [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar). Die Symbolleiste bleibt unverankert, dauerhaft kann nicht an einer beliebigen Stelle andocken.

##  <a name="_core_docking_the_toolbar"></a> Andocken der Symbolleiste

Das Framework ruft [CFrameWnd:: DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar) Wenn der Benutzer versucht, auf die Symbolleiste für eine Seite des Rahmenfensters zu löschen, die andocken können.

Darüber hinaus können Sie diese Funktion zu einem beliebigen Zeitpunkt das Rahmenfenster Steuerleisten angedockt aufrufen. Dies erfolgt normalerweise während der Initialisierung. Mehr als eine Symbolleiste kann an einer bestimmten Seite des Rahmenfensters angedockt werden.

##  <a name="_core_floating_the_toolbar"></a> Lösen der Symbolleiste

Trennen eine andockbare Symbolleiste vom Rahmenfenster wird aufgerufen, lösen der Symbolleiste. Rufen Sie [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar) dazu. Geben Sie der Symbolleiste, um abgedockt werden, den Punkt, wo sie platziert werden soll, und eine Ausrichtungsstil, der bestimmt, ob die unverankerte Symbolleiste horizontal oder vertikal verläuft.

Das Framework ruft diese Funktion auf, wenn ein Benutzer eine Symbolleiste deaktiviert die Andockposition zieht und verwirft ihn an einem Speicherort, in dem Andocken nicht aktiviert ist. Dies kann eine beliebige Stelle innerhalb oder außerhalb des Rahmenfensters sein. Wie bei `DockControlBar`, Sie können diese Funktion auch aufrufen, während der Initialisierung.

Die MFC-Implementierung von andockbaren Symbolleisten bietet keine einiger erweiterter Features finden Sie in einigen Anwendungen, die mit Unterstützung für andockbare Symbolleisten. Features wie z. B. anpassbaren Symbolleisten werden nicht bereitgestellt.

##  <a name="_core_dynamically_resizing_the_toolbar"></a> Dynamisches Ändern der Größe der Symbolleiste

Ab Visual C++, Version 4.0 können Sie für Benutzer Ihrer Anwendung unverankerte Symbolleisten dynamisch ändern der Größe ermöglichen. In der Regel verfügt über eine Symbolleiste einer langen, lineare Form, die horizontal angezeigt. Aber Sie können der Symbolleiste auf die Ausrichtung und Form ändern. Wenn der Benutzer eine Symbolleiste mit einer vertikalen Seite des Rahmenfensters Dockt, ändert die Form z. B. auf einer vertikale Layout. Es ist auch möglich, in ein Rechteck mit mehreren Zeilen von Schaltflächen die Symbolleiste zu strukturieren.

Sie haben folgende Möglichkeiten:

- Geben Sie als ein Merkmal Symbolleiste dynamischen Größenänderung.

- Geben Sie als ein Merkmal Symbolleiste feste Größe.

Um diese zu unterstützen, es gibt zwei neue Toolbar-Stile für die Verwendung in Ihren aufrufen, um die [Symbolleistenformate](../mfc/reference/ctoolbar-class.md#create) Member-Funktion. Dies sind:

- **CBRS_SIZE_DYNAMIC** Steuerleiste ist dynamisch.

- **CBRS_SIZE_FIXED** Steuerleiste wurde behoben.

Der dynamische Größe-Stil kann Ihre Benutzer die Größe der Symbolleiste, während sie unverankert ist, aber nicht, während es angedockt ist. Die Symbolleiste umschließt"", falls erforderlich, um Form zu ändern, wenn der Benutzer seinen Rändern zieht.

Festem Format behält den Umbruch eine Symbolleiste, und beheben die Position der Schaltflächen in jeder Spalte. Der Benutzer der Anwendung kann die Form der Symbolleiste nicht ändern. Die Symbolleiste umschließt an angegebenen stellen, z. B. die Speicherorte der Trennzeichen zwischen den Schaltflächen. Diese Form verwaltet, ob die Symbolleiste angedockt oder unverankert ist. Der Effekt ist eine feste Palette mit mehreren Spalten mit Schaltflächen.

Sie können auch [CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) um einen Zustand und für Schaltflächen der Symbolleisten zurückzugeben. Eine der Stil der Schaltfläche bestimmt, wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert; der Status erfahren Sie, ob die Schaltfläche in einem umschlossenen Zustand befindet.

##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a> Einstellung Wrap Positionen für eine Symbolleiste mit festem Format

Bestimmen Sie für eine Symbolleiste mit festem Format die Symbolleiste Schaltfläche Indizes, die an denen die Symbolleiste umschließt. Der folgende Code zeigt die Vorgehensweise hierfür in des Hauptrahmenfenster `OnCreate` außer Kraft setzen:

[!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

Im allgemeinen MFC-Beispiel [DOCKTOOL](../overview/visual-cpp-samples.md) zeigt, wie Memberfunktionen von Klassen [CControlBar](../mfc/reference/ccontrolbar-class.md) und [CToolBar](../mfc/reference/ctoolbar-class.md) dynamische Layouts einer Symbolleiste zu verwalten. Die Datei EDITBAR angezeigt. CPP im DOCKTOOL.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Grundlegendes über Symbolleisten](../mfc/toolbar-fundamentals.md)

- [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)

- [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Siehe auch

[Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)
