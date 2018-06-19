---
title: Andockbare und unverankerte Symbolleisten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 430af2344888696e3cbf053677ef59c7249b50bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352788"
---
# <a name="docking-and-floating-toolbars"></a>Andockbare und unverankerte Symbolleisten
Die Microsoft Foundation Class-Bibliothek unterstützt die andockbare Symbolleisten. Eine andockbare Symbolleiste angefügt oder angedockt sind, klicken Sie auf jeder Seite des übergeordneten Fensters, oder es kann getrennt sein, in einem eigenen Minirahmenfenster umfließt. In diesem Artikel erläutert die andockbare Symbolleisten in Ihren Anwendungen verwenden.  
  
 Wenn Sie den Assistenten zum Generieren des Grundgerüsts Ihrer Anwendung verwenden, werden Sie aufgefordert, auszuwählen, ob das andockbare Symbolleisten angezeigt werden soll. Der Anwendungs-Assistent generiert standardmäßig Code, der erforderlich ist, eine andockbare Symbolleiste in der Anwendung drei Aktionen ausführt:  
  
-   [Aktivieren des Andockens in einem Rahmenfenster](#_core_enabling_docking_in_a_frame_window).  
  
-   [Aktivieren Sie das Andocken für eine Symbolleiste](#_core_enabling_docking_for_a_toolbar).  
  
-   [Andocken die Symbolleiste (an das Rahmenfenster)](#_core_docking_the_toolbar).  
  
 Wenn eines dieser Schritte fehlen, wird die Anwendung eine Standardsymbolleiste angezeigt. Die letzten beiden Schritte müssen für jede einzelne andockbare Symbolleiste in der Anwendung ausgeführt werden.  
  
 Andere Themen in diesem Artikel beschriebene beinhalten:  
  
-   [Lösen der Symbolleiste](#_core_floating_the_toolbar)  
  
-   [Dynamisches Ändern der Größe der Symbolleiste](#_core_dynamically_resizing_the_toolbar)  
  
-   [Einstellung Wrap Positionen für eine Symbolleiste-Stil](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)  
  
 Finden Sie im allgemeinen MFC-Beispiel [DOCKTOOL](../visual-cpp-samples.md) Beispiele.  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a> Aktivieren des Andockens in einem Rahmenfenster  
 Symbolleisten an ein Framefenster andocken möchten, muss die Rahmenfenster (oder das Ziel) aktiviert sein, um Andocken zu ermöglichen. Dies erfolgt mithilfe der [EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) -Funktion, die eine Überladung `DWORD` bits-Parameter, der einen Satz von Stil ist, der angibt, welcher Seite des Rahmenfensters Andocken akzeptiert. Wenn eine Symbolleiste ist angedockt werden und es sind mehrere Seiten, die es angedockt werden kann, die Seiten in der an übergebene Parameter `EnableDocking` dienen in der folgenden Reihenfolge: oben, unten, links, rechts. Wenn Sie in der Lage sein soll, Steuerelement angedockt Steuerleisten überall, übergeben Sie `CBRS_ALIGN_ANY` auf `EnableDocking`.  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a> Aktivieren des Andockens für eine Symbolleiste  
 Nachdem Sie das Ziel zum Andocken vorbereitet haben, müssen Sie die Symbolleiste (oder die Quelle) in ähnlicher Weise vorbereiten. Rufen Sie [CControlBar:: EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking) Angabe des Ziels Seiten für jede Symbolleiste, das Sie andocken möchten, die die Symbolleiste angedockt werden soll. Wenn keines der Seiten, die im Aufruf angegeben `CControlBar::EnableDocking` entsprechen der Seiten, die zum Rahmenfenster Andocken aktiviert, die Symbolleiste kann nicht angedockt – es wird float. Sobald er umfließt wurde hat, bleibt er unverankerte Symbolleiste, kann die Frame-Fensters angedockt.  
  
 Wenn Sie der gewünschten Effekt dauerhaft unverankerte Symbolleiste ist, rufen Sie `EnableDocking` mit einem Parameter 0. Rufen Sie anschließend [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar). Die Symbolleiste bleibt unverankert, dauerhaft kann nicht an einer beliebigen Stelle andocken.  
  
##  <a name="_core_docking_the_toolbar"></a> Andocken der Symbolleiste  
 Das Framework ruft [CFrameWnd:: DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar) Wenn der Benutzer versucht, auf die Symbolleiste auf einer Seite des Rahmenfensters zu löschen, die andocken können.  
  
 Darüber hinaus können Sie diese Funktion zu einem beliebigen Zeitpunkt das Rahmenfenster Steuerleisten angedockt aufrufen. Dies erfolgt normalerweise während der Initialisierung. Mehr als eine Symbolleiste kann an eine bestimmte Seite des Rahmenfensters angedockt werden.  
  
##  <a name="_core_floating_the_toolbar"></a> Lösen der Symbolleiste  
 Trennen eine andockbare Symbolleiste vom Rahmenfenster wird aufgerufen, lösen der Symbolleiste. Rufen Sie [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar) dazu. Geben Sie der Symbolleiste, um umfließt sein, den Punkt, wo es platziert werden soll, und eine Ausrichtung-Formatvorlage, die bestimmt, ob die unverankerte Symbolleiste horizontal oder vertikal ist.  
  
 Das Framework ruft diese Funktion auf, wenn ein Benutzer eine Symbolleiste deaktiviert an die Andockposition zieht und löscht ihn an einem Speicherort, in dem Andocken nicht aktiviert ist. Dies kann an einer beliebigen Stelle innerhalb oder außerhalb des Rahmenfensters sein. Wie bei `DockControlBar`, Sie können diese Funktion auch aufrufen, während der Initialisierung.  
  
 Die MFC-Implementierung von andockbare Symbolleisten bietet keine einige erweiterte Funktionen, die in einigen Anwendungen, die andockbare Symbolleisten unterstützen. Funktionen, z. B. anpassbaren Symbolleisten werden nicht bereitgestellt.  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a> Dynamisches Ändern der Größe der Symbolleiste  
 Ab Visual C++, Version 4.0 können Sie für Benutzer der Anwendung dynamisch unverankerte Symbolleisten Größe ermöglichen. Normalerweise weist eine Symbolleiste eine Form lange, lineare, die horizontal angezeigt. Sie können jedoch ändern der Symbolleiste auf die Ausrichtung und die Form. Wenn der Benutzer eine Symbolleiste für eine der vertikalen Seiten des Rahmenfensters angedockt, ändert die Form z. B. einem vertikalen Layout. Es ist auch möglich, in ein Rechteck mit mehreren Zeilen von Schaltflächen die Symbolleiste zu strukturieren.  
  
 Sie haben folgende Möglichkeiten:  
  
-   Geben Sie dynamische größenfunktion als ein Merkmal der Symbolleiste.  
  
-   Geben Sie als ein Merkmal Symbolleiste feste Größe.  
  
 Um diese zu unterstützen, es gibt zwei neue Symbolleiste Stile für die Verwendung in Ihren Aufrufen an die [Symbolleistenformate](../mfc/reference/ctoolbar-class.md#create) Memberfunktion. Dies sind:  
  
-   **CBRS_SIZE_DYNAMIC** Steuerleiste ist dynamisch.  
  
-   **CBRS_SIZE_FIXED** Steuerleiste ist unveränderlich.  
  
 Die dynamische Größe-Stil kann Ihre Benutzer die Größe der Symbolleiste, während er unverankert ist, aber nicht, während es angedockt ist. Die Symbolleiste "dient als Wrapper für", falls erforderlich, um Form zu ändern, wie der Benutzer seinen Rändern zieht.  
  
 Festem Format behält den Umbruch eine Symbolleiste, und korrigieren die Position der Schaltflächen in jeder Spalte. Der Benutzer der Anwendung kann nicht die Form der Symbolleiste zu ändern. Die Symbolleiste, die zur angegebenen Orten, wie z. B. die Speicherorte der Trennzeichen zwischen den Schaltflächen eingebunden werden. Er behält diese Form, ob die Symbolleiste angedockt oder unverankert ist. Der Effekt ist eine feste Palette mit mehreren Spalten der Schaltflächen.  
  
 Sie können auch [CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) ein Zustand und den Stil für Schaltflächen auf der Symbolleisten zurückgeben. Eine Schaltfläche Stil bestimmt wie die Schaltfläche angezeigt wird und wie er auf Benutzereingaben reagiert. der Status gibt, ob die Schaltfläche in einem umbrochenen Zustand befindet.  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a> Einstellung Wrap Positionen für eine Symbolleiste-Stil  
 Für eine Symbolleiste mit festem Format zugeordnete Symbolleiste Schaltfläche Indizes, die an denen die Symbolleiste umschlossen werden soll. Der folgende Code zeigt die Vorgehensweise hierfür in Ihrem Hauptrahmenfenster `OnCreate` außer Kraft setzen:  
  
 [!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]  
  
 Im allgemeinen MFC-Beispiel [DOCKTOOL](../visual-cpp-samples.md) zeigt, wie Memberfunktionen von Klassen [CControlBar](../mfc/reference/ccontrolbar-class.md) und [CToolBar](../mfc/reference/ctoolbar-class.md) zum dynamisches Layout einer Symbolleiste zu verwalten. Die Datei EDITBAR angezeigt. CPP im DOCKTOOL.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Grundlagen zu Symbolleisten](../mfc/toolbar-fundamentals.md)  
  
-   [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)  
  
-   [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)

