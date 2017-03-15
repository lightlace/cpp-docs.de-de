---
title: "Andockbare und frei positionierbare Symbolleisten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBRS_SIZE_DYNAMIC"
  - "CBRS_SIZE_FIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBRS_ALIGN_ANY-Konstante"
  - "CBRS_SIZE_DYNAMIC-Konstante"
  - "CBRS_SIZE_FIXED-Konstante"
  - "Symbolleisten mit fester Größe"
  - "Unverankerte Paletten"
  - "Unverankerte Symbolleisten"
  - "Rahmenfenster, Symbolleisten andocken"
  - "Paletten, unverankert"
  - "Größe"
  - "Größe, Symbolleisten"
  - "Symbolleisten-Steuerelemente [MFC], Mit Wrapper umschließen"
  - "Symbolleisten [C++], Andocken"
  - "Symbolleisten [C++], unverankert"
  - "Symbolleisten [C++], Größe"
  - "Symbolleisten [C++], Mit Wrapper umschließen"
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Andockbare und frei positionierbare Symbolleisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Microsoft Foundation Class\-Bibliothek unterstützt andockbare Symbolleisten.  eine andockbare Symbolleiste kann an E\-Mail\-Nachrichten angehängt, oder angedockt wurde, an jede Seite des übergeordneten Fensters oder zu ihr kann, in einem eigenen Minirahmenfenster getrennt werden oder lösen.  Dieser Artikel beschreibt, wie einzelne andockbare Symbolleisten in Anwendungen.  
  
 Wenn Sie im Anwendungs\-Assistenten verwenden, um das Skelett der Anwendung zu generieren, werden Sie aufgefordert auszuwählen, dass Sie, andockbare Symbolleisten soll.  Standardmäßig generiert der Anwendungs\-Assistent den Code, der die drei Aktionen auszuführen, die erforderlich sind, eine andockbare Symbolleiste in der Anwendung zu platzieren:  
  
-   [Aktivieren Sie das Andocken in einem Rahmenfenster](#_core_enabling_docking_in_a_frame_window).  
  
-   [Aktivieren Sie das Andocken für eine Symbolleiste](#_core_enabling_docking_for_a_toolbar).  
  
-   [Docken Sie die Symbolleiste \(an das Rahmenfenster\)](#_core_docking_the_toolbar).  
  
 Wenn diese Schritte fehlen, zeigt die Anwendung eine Standardsymbolleiste an.  Die letzten beiden Schritte müssen für jede einzelne andockbare Symbolleiste in der Anwendung ausgeführt werden.  
  
 Andere Themen beschrieben in diesem Artikeleinschließung:  
  
-   [Frei verschieben der Symbolleiste](#_core_floating_the_toolbar)  
  
-   [Die Symbolleiste dynamisch angepasst wird](#_core_dynamically_resizing_the_toolbar)  
  
-   [Festlegen von Umbruchspositionen für eine KorrigierteFormatsymbolleiste](#_core_setting_wrap_positions_for_a_fixed.2d.style_toolbar)  
  
 Siehe das Beispiel [DOCKTOOL](../top/visual-cpp-samples.md) allgemeine MFC für Beispiele.  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a> Aktivieren des Andockens in einem Rahmenfenster  
 Um Symbolleisten zu einem Rahmenfenster anzudocken, müssen das Rahmenfenster \(oder Ziel\) aktiviert werden um das Andocken zu ermöglichen.  Dies wird mithilfe der [CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md)\-Funktion durchgeführt, die einen `DWORD` akzeptiert Parameter, der ein Satz von Stilbitangebens ist, welcher Seite des Rahmenfensters das Andocken angenommen wird.  Wenn einer Symbolleiste im Begriff ist angedockt werden und mehrere Seiten vorhanden sind, dass es angedockt werden kann, werden die Seiten, die ein In\-Parameter übergeben wird von `EnableDocking` angegeben werden, in der folgenden Reihenfolge verwendet: oberen, unteren, linken, rechten.  Wenn Sie möchten, Steuerleisten an beliebigen Stellen andocken möchten, übergeben Sie `CBRS_ALIGN_ANY` in `EnableDocking`.  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a> Aktivieren des Andockens für eine Symbolleiste  
 Nachdem Sie das Ziel für das Andocken vorbereitet haben, müssen Sie die Symbolleiste \(oder Quelle\) in ähnliche Weise vorbereiten.  Aufruf [CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md) für jede Symbolleiste, das Sie andocken möchten, Zielseiten angibt, an die die Symbolleisten angedockt werden sollen.  Wenn keine der Seiten, die im Aufruf von `CControlBar::EnableDocking` mit den Seiten aktiviert werden zum Andocken vorgesehenen das Rahmenfenster, Symbolleiste angegeben werden, nicht angedockt werden kann \- es an.  Eine nicht angedockte Symbolleiste bleibt unverankert und kann im Rahmenfenster nicht wieder angedockt werden.  
  
 Wenn die Auswirkungen, den gewünschten, dauerhaft eine angedockte Symbolleiste, rufen `EnableDocking` mit einem Parameter von 0 ist.  Anschließend rufen Sie [CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md).  Die Symbolleiste bleibt unverankert, dauerhaft, kann an beliebigen Stellen andocken möchten.  
  
##  <a name="_core_docking_the_toolbar"></a> Andocken der Symbolleiste  
 Das Framework ruft [CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md) auf, wenn der Benutzer versucht, Symbolleiste auf einer Seite des Rahmenfensters abzulegen, das Andocken können.  
  
 Außerdem können Sie diese Funktion jederzeit aufrufen, um im Rahmenfenster Steuerleisten anzudocken.  Dies wird normalerweise während der Initialisierung verwendet.  Unzulässigerweise eine Symbolleiste kann zu einer bestimmten Seite des Rahmenfensters angedockt werden.  
  
##  <a name="_core_floating_the_toolbar"></a> Frei verschieben der Symbolleiste  
 eine andockbare Symbolleiste vom Rahmenfenster trennt, wird unverankert der Symbolleiste aufgerufen.  Aufruf [CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md), um dazu.  Geben Sie der " werden an, Symbolleiste, dem Punkt, an dem sie eingefügt werden soll, und einen Ausrichtungsformat, das bestimmt, ob die unverankerte Symbolleiste horizontal oder vertikal ist.  
  
 Das Framework ruft diese Funktion auf, wenn ein Benutzer eine Symbolleiste aus seinem angedockte Position ziehen und sie in einem Verzeichnis ablegt, in dem das Andocken nicht aktiviert ist.  Dies kann innerhalb oder außerhalb des Rahmenfensters sein.  Wie bei `DockControlBar`, können Sie diese Funktion während der Initialisierung aufrufen.  
  
 Die MFC\-Implementierung von andockbaren Symbolleisten bietet nicht einige der erweiterten Features, die in mehreren Anwendungen genutzt werden, die einzelne andockbare Symbolleisten unterstützen.  Funktionen wie anpassbare Symbolleisten werden nicht bereitgestellt.  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a> Die Symbolleiste dynamisch angepasst wird  
 Seit Version 4.0 von Visual C\+\+, können Sie sie aktivieren für Benutzer der Anwendung, unverankerte Symbolleisten seine Größe zu ändern.  Normalerweise verfügt eine Symbolleiste eine lange, lineare Form, horizontal angezeigt.  Sie können jedoch die Ausrichtung und die Form Symbolleiste ändern.  Wenn Benutzer eine Symbolleiste für eine der vertikalen Seiten des Rahmenfensters das Andocken, ändert die Form in einem vertikalen Layout.  Es ist auch möglich, die Symbolleiste in ein Rechteck mit mehreren Zeilen von Schaltflächen umzugestalten.  
  
 Folgende Aktionen sind möglich:  
  
-   Geben Sie als Symbolleistenmerkmal dynamische Größenanpassung an.  
  
-   Option feste Größe als Symbolleistenmerkmal.  
  
 Um diese Unterstützung bereitzustellen, gibt es zwei neue Symbolleistenformate zur Verwendung in den Aufrufen an die Memberfunktion [CToolBar::Create](../Topic/CToolBar::Create.md).  Dies sind:  
  
-   **CBRS\_SIZE\_DYNAMIC** Steuerleiste ist dynamisch.  
  
-   **CBRS\_SIZE\_FIXED** Steuerleiste wird behoben.  
  
 Das dynamische Format der Größe können den Benutzer die Symbolleiste Größe ändern, das unverankert ist, jedoch nicht in sie angedockt ist.  Die Symbolleiste "Aufgabe" um bei Bedarf, um sich als die Benutzerzieh zu verformen seine Kanten.  
  
 Das Größe feste Format verwaltet die Umbruchszustände einer Symbolleiste bei und die Position der Schaltflächen in jeder Spalte.  Der Benutzer Ihrer Anwendung kann die Form der Symbolleiste nicht ändern.  Die Symbolleistenumbrüche an bestimmten Orten, z Speicherorten von Trennzeichen zwischen den Schaltflächen.  Sie verwaltet diese Form bei, dass die Symbolleiste oder unverankert angedockt ist.  Der Effekt ist eine feste Palette mit mehreren Spalten von Schaltflächen.  
  
 Sie können [CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) verwenden, um einem Zustand zurückversetzen und für Schaltflächen auf den Symbolleisten zu formatieren.  Das Format einer Schaltfläche bestimmt, wie die Schaltfläche angezeigt wird und wie sie auf Benutzereingaben reagiert; der Zustand übermittelt sicher, dass die Schaltfläche in einem eingebundenen Zustand ist.  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed.2d.style_toolbar"></a> Festlegen von Umbruchs\-Positionen für eine Korrigierte\-Format\-Symbolleiste  
 Eine Symbolleiste mit dem Größe korrigierten Format, an denen besondere Symbolleistenschaltflächenindizes die Symbolleiste umbrochen werden.  Der folgende Code zeigt, wie Sie dies in `OnCreate` Überschreibung des Hauptrahmenfensters:  
  
 [!CODE [NVC_MFCDocViewSDI#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#10)]  
  
 Die [DOCKTOOL](../top/visual-cpp-samples.md) zeigt MFC allgemeinen Beispiel, wie von Memberfunktionen von Klassen [CControlBar](../mfc/reference/ccontrolbar-class.md) und [CToolBar](../mfc/reference/ctoolbar-class.md) verwendet, um dynamisches Layout einer Symbolleiste zu verwalten.  Siehe die Datei EDITBAR.CPP in DOCKTOOL.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Grundlagen zu Symbolleisten](../mfc/toolbar-fundamentals.md)  
  
-   [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)  
  
-   [Mit der alten Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
## Siehe auch  
 [Implementieren der MFC\-Symbolleiste](../mfc/mfc-toolbar-implementation.md)