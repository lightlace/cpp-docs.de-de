---
title: Rahmenfenster | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame widows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14dabd345f47b064f78a4e9a3dede834bddeb9d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="frame-windows"></a>Rahmenfenster
Wenn eine Anwendung unter Windows ausgeführt wird, interagiert der Benutzer mit Dokumenten im Frame-Fensters angezeigt. Einem Dokumentrahmenfenster besteht aus zwei wesentlichen Komponenten: Frames und den Inhalt, der sie frames. Einem Dokumentrahmenfenster kann eine [Einzeldokumentoberfläche](../mfc/sdi-and-mdi.md) Rahmenfenster (SDI) oder ein [mehrerer dokumentoberflächen](../mfc/sdi-and-mdi.md) (MDI) untergeordnetes Fenster. Windows verwaltet die meisten der Benutzerinteraktion mit dem Rahmenfenster: verschieben und Ändern der Größe des Fensters, schließen und minimieren und maximieren. Sie verwalten den Inhalt innerhalb des Rahmens.  
  
## <a name="frame-windows-and-views"></a>Rahmenfenster und Ansichten  
 Die MFC-Grundstruktur verwendet Rahmenfenster Ansichten enthalten. Die zwei Komponenten – Rahmen und Inhalt – dargestellt und von zwei verschiedenen Klassen in MFC verwaltet werden. Eine Frame-Fensterklasse verwaltet den Frame und View-Klasse verwaltet den Inhalt. Das Fenster "ist ein untergeordnetes Element des Rahmenfensters. Zeichnen und andere Benutzerinteraktion mit dem Dokument erfolgen in der Ansicht Clientbereich, nicht das Rahmenfenster Clientbereichs. Das Rahmenfenster stellt einen sichtbaren Rahmen um eine Sicht, die mit einer Titelleiste und Standardfenster-Steuerelemente, z. B. ein Systemmenü, Schaltflächen zum Minimieren und Maximieren Sie das Fenster, und steuert die Größe des Fensters. Der "Inhalt" bestehen des Clientbereichs des Fensters, das von einem untergeordneten Fenster vollständig belegt wird – die Sicht. Die folgende Abbildung zeigt die Beziehung zwischen einem Rahmenfenster und einer Ansicht.  
  
 ![Frame-Fensteransicht](../mfc/media/vc37fx1.gif "vc37fx1")  
Rahmenfenster und -ansicht  
  
## <a name="frame-windows-and-splitter-windows"></a>Rahmenfenster und Splitterfenster  
 Eine andere häufige Anordnung für mehrere Ansichten, in der Regel mit Rahmen um das Rahmenfenster ist ein [unterteiltes Fenster](../mfc/multiple-document-types-views-and-frame-windows.md). In einem Splitterfenster ist das Rahmenfenster Clientbereichs von einem Splitterfenster kann belegt, die wiederum mehrere untergeordnete Fenster, Bereiche, die Ansichten sind aufgerufen.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
 **Themen zu allgemeinen Rahmenfenstern**  
  
-   [Fensterobjekte](../mfc/window-objects.md)  
  
-   [Rahmenfensterklassen](../mfc/frame-window-classes.md)  
  
-   [Die vom Anwendungs-Assistenten erstellten Rahmenfensterklassen](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Fensterstile Frame](../mfc/frame-window-styles-cpp.md)  
  
-   [Welche von Rahmenfenstern](../mfc/what-frame-windows-do.md)  
  
 **Themen zum Verwenden von Rahmenfenstern**  
  
-   [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
-   [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)  
  
-   [Verwalten von untergeordneten MDI-Fenster](../mfc/managing-mdi-child-windows.md)  
  
-   [Verwalten der aktuellen Ansicht](../mfc/managing-the-current-view.md) in einem Rahmenfenster, die mehr als eine Ansicht enthält.  
  
-   [Verwalten von Menüs, Steuerleisten und Zugriffstasten (andere Objekte, die das Rahmenfenster Abstand gemeinsam verwenden)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 **Themen zu speziellen Funktionalitäten von Rahmenfenstern**  
  
-   [Ziehen und Ablegen von Dateien](../mfc/dragging-and-dropping-files-in-a-frame-window.md) im Datei-Explorer oder Datei-Manager in einem Rahmenfenster  
  
-   [Reagieren auf dynamischen Datenaustausch (DDE)](../mfc/responding-to-dynamic-data-exchange-dde.md)  
  
-   [Halbmodaler Zustand: kontextbezogene Hilfe zu Windows (anderer Fensteraktionen)](../mfc/orchestrating-other-window-actions.md)  
  
-   [Halbmodaler Zustand: Drucken und die Seitenansicht (anderer Fensteraktionen)](../mfc/orchestrating-other-window-actions.md)  
  
 **Themen für andere Arten von Fenstern**  
  
-   [Verwenden von Ansichten](../mfc/using-views.md)  
  
-   [Dialogfelder](../mfc/dialog-boxes.md)  
  
-   [Steuerelemente](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows](../mfc/windows.md)

