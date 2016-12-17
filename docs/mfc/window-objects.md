---
title: "Fensterobjekte"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rahmenfenster [C++], C++-Fensterobjekte"
  - "HWND"
  - "HWND, Fensterobjekte"
  - "Nachrichten [C++], Windows"
  - "MFC [C++], Fenster"
  - "Objekte [C++], Fenster"
  - "Visual C++, Fensterobjekte"
  - "Fenstermeldungen [C++]"
  - "Fensterobjekte [C++]"
  - "Fenster [C++], C++-Fensterobjekte"
  - "Windows-Fenster [C++]"
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Fensterobjekte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC\-Zubehörklasse [CWnd](../mfc/reference/cwnd-class.md), um den `HWND` eines Handles Fensters zu kapseln.  Das `CWnd`\-Objekt ist Window\-Objekt einen C\+\+\-Compiler, das von `HWND`, das ein Windows\-Fenster jedoch Manifestfragmenten es darstellt.  Verwenden Sie `CWnd`, um eigene Klassen des untergeordneten Fensters zu berechnen, oder verwenden Sie eine der zahlreichen MFC\-Klassen, die von `CWnd` abgeleitet werden.  Klasse `CWnd` ist die Basisklasse für alle Fenster, einschließlich Rahmenfenster, Dialogfelder, Fenster, Steuerelemente und untergeordnete Steuerleisten wie Symbolleisten.  Ein gutes Kenntnisse eines [die Beziehung zwischen Window\-Objekt einer C\+\+\-Datei und das HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) ist für die effektive Programmierung mit MFC entscheidend.  
  
 MFC stellt einige Standardfunktionalität und Verwaltung von Fenstern, aber Sie können eine eigene Klasse von `CWnd` ableiten und die Memberfunktionen verwenden, um die bereitgestellte Funktionen anpassen.  Sie können untergeordnete Fenster, indem Sie ein `CWnd`\-Objekt konstruiert und die zugehörige Memberfunktion [Erstellen](../Topic/CWnd::Create.md) erstellen, dann aufrufen, passen die untergeordneten Fenster mit `CWnd`\-Memberfunktionen an.  Sie können die Objekte einbetten, die von [CView](../mfc/reference/cview-class.md), z Formularansichten oder Strukturansichten, in einem Rahmenfenster abgeleitet werden.  Außerdem können Sie die verschiedenen Ansichten der Dokumente zu Splitterbereiche unterstützen, der Klasse [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).  
  
 Jedes Objekt, das von der `CWnd`\-Klasse abgeleitet ist, enthält eine Meldungszuordnung, durch die Windows\-Meldungen Sie oder Befehls\-IDs in eigenen Handler zuordnen können.  
  
 Die allgemeinen Themen über das Programmieren für Windows ist eine gute Ressource zum Erlernen, wie die Memberfunktionen `CWnd` verwendet, die die `HWND` \- APIs kapseln.  
  
## Funktionen zum Funktionieren auf CWnd  
 `CWnd` und der [abgeleitete Fensterklassen](../mfc/derived-window-classes.md) bieten Konstruktoren, Destruktoren und Memberfunktionen, um das Objekt initialisieren, die zugrunde liegenden Windows\-Strukturen zu erstellen, und auf gekapselte `HWND` zuzugreifen.  `CWnd` stellt ebenfalls Memberfunktionen, Windows\-APIs zum Senden von Meldungen kapseln und auf den Zustand des Fensters zugreifen und Koordinaten konvertieren und aktualisieren und wechseln und die Zwischenablage und auf viele andere Aufgaben zugreifen.  Die meisten Windows\-FensterVerwaltung APIs, die ein `HWND` als Argument annehmen, werden Memberfunktionen von `CWnd` gekapselt.  Die Namen der Funktionen und die Parameter werden in der `CWnd`\-Memberfunktion beibehalten.  Ausführliche Informationen über Windows\-APIs, die von einem `CWnd` gekapselt werden, finden Sie unter [CWnd](../mfc/reference/cwnd-class.md)\- Klasse.  
  
## CWnd Windows\-Meldungen und  
 Einer der wichtigsten Objekte von `CWnd` sind, eine Schnittstelle für das Behandeln von Windows\-Meldungen, wie `WM_PAINT` oder `WM_MOUSEMOVE` bereitstellen.  Viele der Memberfunktionen von `CWnd` werden Handler für Standardmeldungen \- Anfang mit dem Bezeichner **afx\_msg** und dem Präfix "," z `OnPaint` und **OnMouseMove** aktiviert.  [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md) Abdeckungsmeldungen Meldungsbehandlung und detailliert.  Die Informationen dort gelten gleichermaßen für den Fenstern und denen Framework zu, die Sie selbst für besondere Zwecke erstellen.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Die Beziehung zwischen Window\-Objekt einer C\+\+\-Datei und das HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Abgeleitete Fensterklassen](../mfc/derived-window-classes.md)  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)  
  
-   [Trennen von CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Arbeiten mit Fensterobjekten](../mfc/working-with-window-objects.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md): Objekte, die Windows\-Zeichnen geräteunabhängig machen  
  
-   [Grafikobjekte](../mfc/graphic-objects.md): Pinsel, Stifte, Schriftarten, Bitmaps, Paletten, Bereiche  
  
## Siehe auch  
 [Windows](../mfc/windows.md)