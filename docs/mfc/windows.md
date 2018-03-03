---
title: Windows | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], window
- windows [MFC]
- MFC, windows
- window objects [MFC], MFC Framework
ms.assetid: dd92bf34-842e-40fe-8aea-3028b55314d5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e81be5ef0216f7d8a28ea7d5046c127f18670a6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows"></a>Windows
Diese Artikelreihe werden Windows-Objekte in der MFC-Framework behandelt. Leiten Sie alle MFC-Fenster von Klasse [CWnd](../mfc/reference/cwnd-class.md), einschließlich der Frame-Fensters, Ansichten, Dialogfelder und Steuerelemente.  
  
 Die erste Gruppe von Artikeln beschreibt [Fensterobjekten](../mfc/window-objects.md) im Allgemeinen. Finden Sie in dieser Gruppe für allgemeine Informationen zu C++ Windows-Objekte, wie sie einen HWND kapseln und ihre Verwendung beim Erstellen eigener Windows, z. B. untergeordnete Fenster.  
  
 Die zweite Gruppe von Artikeln wird beschrieben, [Rahmenfenster](../mfc/frame-windows.md)– Windows, die einen Rahmen um Inhalt gestellt – insbesondere. Finden Sie in dieser Gruppe für Informationen zur Verwaltung der MFC-Framework Rahmenfenster und die Inhalte, die sie, z. B. Steuerleisten und Ansichten Rahmen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
 *Themen zur Windows-Objekte im Allgemeinen*  
  
-   [Fensterobjekte](../mfc/window-objects.md)  
  
-   [Beziehung zwischen C++ und einem HWND behandelt.](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Abgeleitete Fensterklassen](../mfc/derived-window-classes.md)  
  
-   [Erstellen von Fensterobjekten](../mfc/creating-windows.md)  
  
-   [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)  
  
-   [Registrieren von Fensterklassen""](../mfc/registering-window-classes.md)  
  
-   [Arbeiten mit Fensterobjekten](../mfc/working-with-window-objects.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md): Objekte, die Windows-Zeichnung geräteunabhängige stellen  
  
-   [Grafikobjekte](../mfc/graphic-objects.md): Stifte, Pinsel, Schriftarten, Bitmaps, Paletten, Regionen  
  
 *Themen zu Rahmenfenstern*  
  
-   [Rahmenfenster](../mfc/frame-windows.md): Windows-Objekte, die Frames bereitstellen  
  
-   [Rahmenfenster und Ansichten](../mfc/frame-windows.md)  
  
-   [Rahmenfensterklassen](../mfc/frame-window-classes.md)  
  
-   [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)  
  
-   [Ändern der Stile eines mit MFC erstellten Fensters](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Welche von Rahmenfenstern](../mfc/what-frame-windows-do.md)  
  
-   [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)  
  
-   [Verwalten von MD/untergeordneten Fenstern (das MDICLIENT-Fenster)](../mfc/managing-mdi-child-windows.md)  
  
-   [Verwalten von Menüs, Steuerleisten und Zugriffstasten](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [CFrameWnd](../mfc/reference/cframewnd-class.md)  
  
-   [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
  
-   [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
  
-   [Verwenden von Ansichten](../mfc/using-views.md)  
  
-   [Mehrere Dokumenttypen, Ansichten und Rahmenfenster (Splitterfenster)](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Nachrichten (Zuordnungen und Handlerfunktionen)](../mfc/messages.md)  
  
 *Erstellen und Zerstören von Windows*  
  
-   [Allgemeine Ablauffolge bei der Fenstererstellung](../mfc/general-window-creation-sequence.md)  
  
-   [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
-   [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)  
  
 *Splitterfenster erstellen*  
  
-   [Splitterfenster erstellen](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
 *Verwalten von untergeordneten Fenstern und der aktuellen Ansicht*  
  
-   [Verwalten von untergeordneten MDI-Fenster](../mfc/managing-mdi-child-windows.md)  
  
-   [Verwalten der aktuellen Ansicht](../mfc/managing-the-current-view.md)  
  
-   [Verwalten von Menüs, Steuerleisten und Zugriffstasten](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 *Arbeiten Sie mit Gerätekontexte und Fensterstile*  
  
-   [Verwenden von Stiften und andere Grafikobjekte in einem Gerätekontext](../mfc/graphic-objects.md)  
  
-   [Ändern der Stile eines mit MFC erstellten Fensters](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Symbolleisten](../mfc/toolbars.md)   
 [Statusleisten](../mfc/status-bars.md)   
 [Dialogleisten](../mfc/dialog-bars.md)

