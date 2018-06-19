---
title: Fensterobjekte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63b8d8dbde679d030eddd77fae6ca1fab519fdac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385270"
---
# <a name="window-objects"></a>Fensterobjekte
MFC stellt die Klasse [CWnd](../mfc/reference/cwnd-class.md) zum Kapseln der `HWND` Handle eines Fensters. Die `CWnd` Objekt ist ein C++-Fensterobjekt, unterscheidet der `HWND` , die ein Windows darstellt Fenster aber, die sie enthält. Verwenden Sie `CWnd` Klassen zu leiten Sie ein eigene untergeordnete Fenster, oder verwenden Sie eines der vielen MFC-Klassen abgeleitet `CWnd`. Klasse `CWnd` ist die Basisklasse für alle Fenster, einschließlich der Frame-Fensters, Dialogfelder, untergeordnete Fenster, Steuerelemente und Steuerleisten wie Symbolleisten. Ein gutes Verständnis der [die Beziehung zwischen einem C++-Fensterobjekt und einem HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) ist entscheidend für die effektive Programmierung mit MFC.  
  
 MFC bietet einige Standardfunktionen und Verwaltung von Windows, aber Sie können eine eigene Klasse von ableiten `CWnd` und seine Memberfunktionen zur Anpassung von bereitgestellten Funktionen verwenden. Sie können untergeordnete Fenster erstellen, durch das Erstellen einer `CWnd` Objekt und der Aufruf der [erstellen](../mfc/reference/cwnd-class.md#create) Member Funktion dann Anpassen der untergeordneten Fenster mit `CWnd` Memberfunktionen. Können Sie Objekte, die von abgeleiteten einbetten [CView](../mfc/reference/cview-class.md), z. B. Formularansichten oder Strukturansichten in einem Rahmenfenster. Und Sie können mehrere Ansichten von Dokumenten über Teilfenster, von der Klasse bereitgestellten unterstützen [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).  
  
 Jedes Objekt abgeleitet Klasse `CWnd` eine meldungszuordnung, über die Sie Zuordnen von Windows-Meldungen oder Befehls-IDs in Ihrem eigenen Handler enthält.  
  
 Die allgemeine Literatur zum Programmieren von Windows eine gute Ressource zum Erlernen der Verwendung ist die `CWnd` Memberfunktionen kapseln die `HWND` APIs.  
  
## <a name="functions-for-operating-on-a-cwnd"></a>Funktionen, die für den Betrieb einer CWnd  
 `CWnd` und die zugehörige [abgeleitete Fensterklassen](../mfc/derived-window-classes.md) bieten Konstruktoren, Destruktoren und Memberfunktionen zum Initialisieren des Objekts die zugrunde liegenden Windows-Strukturen erstellen und Zugriff auf das gekapselte `HWND`. `CWnd` bietet außerdem Memberfunktionen, die Windows-APIs zu, zum Senden von Nachrichten, die Zugriff auf das Fenster Status kapseln, Konvertieren von Koordinaten, aktualisieren, scrollen, den Zugriff auf die Zwischenablage, und viele andere Tasks. Die meisten Windows-Fenster-Management-APIs, die nehmen eine `HWND` Argument werden als Memberfunktionen der gekapselt `CWnd`. Die Namen der Funktionen und die zugehörigen Parameter bleiben der `CWnd` Memberfunktion. Weitere Informationen zu den Windows-APIs, die durch gekapselte `CWnd`, finden Sie unter Klasse [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="cwnd-and-windows-messages"></a>CWnd und Windows-Meldungen  
 Einer der Hauptzwecke von `CWnd` besteht darin, eine Schnittstelle bereitzustellen, für die Behandlung von Windows-Meldungen, z. B. `WM_PAINT` oder `WM_MOUSEMOVE`. Viele der Memberfunktionen der `CWnd` Handler für standard-Nachrichten sind – die mit dem Bezeichner ab **Afx_msg** und das Präfix "On", z. B. `OnPaint` und **OnMouseMove**. [Behandlung und Zuordnung Meldungen](../mfc/message-handling-and-mapping.md) Nachrichten und Meldungsbehandlung ausführlich behandelt. Die Informationen es gilt gleichermaßen für das Framework Windows- und diejenigen, die Sie selbst für besondere Zwecke erstellen.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Die Beziehung zwischen einem C++-Fensterobjekt und einem HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Abgeleitete Fensterklassen](../mfc/derived-window-classes.md)  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)  
  
-   [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Arbeiten mit Fensterobjekten](../mfc/working-with-window-objects.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md): Objekte, die Windows-Gerät zeichnen unabhängig machen  
  
-   [Grafikobjekte](../mfc/graphic-objects.md): Stifte, Pinsel, Schriftarten, Bitmaps, Paletten, Regionen  
  
## <a name="see-also"></a>Siehe auch  
 [Windows](../mfc/windows.md)

