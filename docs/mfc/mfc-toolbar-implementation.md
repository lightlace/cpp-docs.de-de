---
title: "Implementieren der MFC-Symbolleiste | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bitmaps [C++], Symbolleiste"
  - "Schaltflächen [C++], MFC-Symbolleisten"
  - "CToolBar-Klasse, Erstellen von Symbolleisten"
  - "CToolBarCtrl-Klasse, Implementieren von Symbolleisten"
  - "Andocken von Symbolleisten"
  - "Unverankerte Symbolleisten"
  - "MFC-Symbolleisten"
  - "QuickInfos [C++], Aktivieren"
  - "Symbolleisten-Steuerelemente [MFC]"
  - "Symbolleisten [C++]"
  - "Symbolleisten [C++], Erstellen"
  - "Symbolleisten [C++], Andocken"
  - "Symbolleisten [C++], unverankert"
  - "Symbolleisten [C++], Implementieren von MFC-Symbolleisten"
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Implementieren der MFC-Symbolleiste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Symbolleiste ist eine [Steuerleiste](../mfc/control-bars.md), die die Bitmapbilder von Steuerelementen enthält.  Diese Bilder können sich wie Druckknöpfe, Kontrollkästchen oder Optionsfelder verhalten.  MFC stellt die Klasse [CToolbar](../mfc/reference/ctoolbar-class.md) für die Verwaltung von Symbolleisten bereit.  
  
 Wenn Sie sie aktivieren, können Benutzer von MFC\-Symbolleisten diese an den Rand eines Fensters andocken, oder an einer beliebigen Stelle im Anwendungsfenster "abdocken".  MFC unterstützt keine anpassbaren Symbolleisten wie in der Entwicklungsumgebung.  
  
 MFC unterstützt auch QuickInfos: kleine Popupfenster, in denen der Zweck einer Symbolleistenschaltfläche beschrieben wird, wenn Sie die Maus über die Schaltfläche positionieren.  Wenn der Benutzer eine Symbolleisten\-Schaltfläche drückt, wird standardmäßig eine Statuszeichenfolge in der Statusleiste \(falls vorhanden\) angezeigt.  Sie können die Aktualisierung der "aufleuchtenden" Statusleiste aktivieren, damit die Statuszeichenfolge angezeigt wird, wenn die Maus über die Schaltfläche positioniert wird, ohne dass sie gedrückt wird.  
  
> [!NOTE]
>  Ab MFC 4.0 werden Symbolleisten und QuickInfo mit der Funktionalität von Windows 95 und höher anstelle der vorherigen, MFC\-spezifischen Implementierung implementiert.  
  
 Für die Abwärtskompatibilität behält MFC die ältere Symbolleistenimplementierung in der Klasse **COldToolBar** bei.  In der Dokumentation für frühere Versionen wird MFC **COldToolBar** unter `CToolBar` beschrieben.  
  
 Erstellen Sie die erste Symbolleiste im Programm, indem Sie die Symbolleistenoption im Anwendungs\-Assistenten auswählen.  Sie können auch weitere Symbolleisten erstellen.  
  
 Die folgenden werden in diesem Artikel eingeführt:  
  
-   [Schaltflächen der Symbolleiste](#_core_toolbar_buttons)  
  
-   [Andockbare und unverankerte Symbolleisten](#_core_docking_and_floating_toolbars)  
  
-   [Symbolleisten und QuickInfo](#_core_toolbars_and_tool_tips)  
  
-   [Die Klassen CToolBar und CToolBarCtrl](#_core_the_ctoolbar_and_ctoolbarctrl_classes)  
  
-   [Die Symbolleistenbitmap](#_core_the_toolbar_bitmap)  
  
##  <a name="_core_toolbar_buttons"></a> Schaltflächen der Symbolleiste  
 Die Schaltflächen in einer Symbolleiste sind den Elementen in einem Menü analog.  Beide Arten von Benutzeroberflächen\-Objekten generieren Befehle, die das Programm bearbeitet, indem es Handlerfunktionen bereitstellt.  Häufig duplizieren Symbolleisten\-Schaltflächen die Funktionalität von Menübefehlen und stellen eine alternative Benutzeroberfläche mit derselben Funktionalität bereit.  Solche Duplizierung wird einfach angeordnet, indem die Schaltfläche und das Menüelement die gleiche ID erhalten.  
  
 Sie können die Schaltflächen in einer Symbolleiste so erstellen, dass sie als Druckknöpfe, Kontrollkästchen oder Optionsfelder angezeigt werden und sich entsprechend verhalten.  Weitere Informationen finden Sie in der Dokumentation der [CToolBar](../mfc/reference/ctoolbar-class.md)\-Klasse.  
  
##  <a name="_core_docking_and_floating_toolbars"></a> Andockbare und unverankerte Symbolleisten  
 Eine MFC\-Symbolleiste kann:  
  
-   fest entlang der Seite des übergeordneten Fensters geöffnet stehen.  
  
-   vom Benutzer gezogen und an einer oder mehreren Seiten des von Ihnen angegebenen übergeordneten Fensters "angedockt" oder angefügt werden.  
  
-   vom Rahmenfenster "abgedockt" oder gelöst werden und im eigenen kleinen Rahmenfenster angezeigt werden, sodass der Benutzer es an eine beliebige Position verschieben kann.  
  
-   im unverankerten Modus in der Größe verändert werden.  
  
 Weitere Informationen finden Sie im Artikel [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md).  
  
##  <a name="_core_toolbars_and_tool_tips"></a> Symbolleisten und QuickInfo  
 MFC\-Symbolleisten können als "QuickInfo" angezeigt werden. Hierbei handelt es sich um kleine Fenster, die eine Kurztextbeschreibung mit dem Zweck einer Symbolleisten\-Schaltfläche enthalten.  Wenn der Benutzer die Maus über eine Symbolleisten\-Schaltfläche bewegt, bieten die Popupfenster mit den QuickInfos einen Hinweis an.  Weitere Informationen finden Sie im Artikel [Symbolleisten\-QuickInfo](../mfc/toolbar-tool-tips.md).  
  
##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> Die Klassen CToolBar und CToolBarCtrl  
 Sie verwalten die Symbolleisten der Anwendung über die Klasse [CToolBar](../mfc/reference/ctoolbar-class.md).  Ab MFC 4.0 ist `CToolBar` erneut implementiert, sodass das allgemeine Steuerelement für Symbolleisten verwendet werden kann, das unter Windows 95 oder höher und Windows NT 3.51 oder höher verfügbar ist.  
  
 Diese Neuimplementierung führt zu weniger MFC\-Code in Symbolleisten, da MFC die Betriebssystemunterstützung ausnutzt.  Das Neuimplementierung verbessert auch die Funktionalität.  Sie können `CToolBar`\-Memberfunktionen verwenden, um Symbolleisten zu bearbeiten, oder Sie können einen Verweis auf das zugrunde liegende [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)\-Objekt erhalten und seine Memberfunktionen für Symbolleistenanpassung sowie zusätzliche Funktionen aufrufen.  
  
> [!TIP]
>  Wenn Sie in die ältere MFC\-Implementierung von `CToolBar` investiert haben, ist diese Unterstützung weiterhin verfügbar.  Weitere Informationen finden Sie im Artikel [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md).  
  
 Siehe auch das allgemeine Beispiel [DOCKTOOL](../top/visual-cpp-samples.md) zu MFC.  
  
##  <a name="_core_the_toolbar_bitmap"></a> Die Symbolleistenbitmap  
 Ein erstelltes `CToolBar`\-Objekt erstellt das Symbolleistenbild, indem es eine einzelne Bitmap lädt, das ein Bild für jede Schaltfläche enthält.  Der Anwendungs\-Assistent erstellt eine Standardbitmap für die Symbolleiste, das Sie mit dem [Symbolleisten\-Editor](../mfc/toolbar-editor.md) von Visual C\+\+ anpassen können.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Grundlagen zu Symbolleisten](../mfc/toolbar-fundamentals.md)  
  
-   [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)  
  
-   [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)  
  
-   [Arbeiten mit dem ToolBar\-Steuerelement](../mfc/working-with-the-toolbar-control.md)  
  
-   [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
-   Die Klassen [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
## Siehe auch  
 [Symbolleisten](../mfc/toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)