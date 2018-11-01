---
title: Fensterobjekte
ms.date: 11/04/2016
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
ms.openlocfilehash: 3e20ef1f3643b9e802c7cdc399d3436ceadeae79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566698"
---
# <a name="window-objects"></a>Fensterobjekte

MFC stellt die Klasse [CWnd](../mfc/reference/cwnd-class.md) zum Kapseln der `HWND` Handle eines Fensters. Die `CWnd` Objekt ist ein C++-Fensterobjekt, unterscheidet der `HWND` , das eine Windows darstellt Fenster jedoch, die sie enthält. Verwenden Sie `CWnd` Klassen Ihre eigenen untergeordneten Fensters abgeleitet werden, oder verwenden Sie eine der vielen MFC-Klassen abgeleitet `CWnd`. Klasse `CWnd` ist die Basisklasse für alle Fenster, einschließlich der Frame-Fensters, Dialogfelder, untergeordnete Fenster, Steuerelemente und Schiebeleisten-Steuerelemente wie beispielsweise Symbolleisten. Ein gutes Verständnis der [die Beziehung zwischen einem C++-Fensterobjekt und einem HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) ist von entscheidender Bedeutung für die effektive Programmierung mit MFC.

MFC stellt einige Standardfunktionen und Verwaltung von Windows, aber Sie können eine eigene Klasse von ableiten `CWnd` und seine Memberfunktionen verwenden, um die bereitgestellten Funktionen anzupassen. Sie können untergeordnete Fenster erstellen, durch das Erstellen einer `CWnd` -Objekt ab, und rufen die [erstellen](../mfc/reference/cwnd-class.md#create) Member Funktion und dann anpassen, die untergeordneten Fenster verwenden `CWnd` Memberfunktionen. Sie können abgeleitete Objekte einbetten [CView](../mfc/reference/cview-class.md), z. B. Formularansichten oder Strukturansichten, in einem Rahmenfenster. Und Sie können mehrere Ansichten von Dokumenten über das Splitter-Bereiche, von der Klasse bereitgestellten unterstützen [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).

Jedes Objekt von Klasse abgeleitet `CWnd` eine meldungszuordnung, die über das können Sie Windows-Nachrichten zuordnen oder Befehls-IDs an Ihre eigenen Handler enthält.

Der allgemeine Literatur zum Programmieren für Windows eine gute Ressource für die Verwendung ist die `CWnd` Member-Funktionen, die Kapseln der `HWND` APIs.

## <a name="functions-for-operating-on-a-cwnd"></a>Funktionen für den Betrieb einer CWnd

`CWnd` und die zugehörige [abgeleitete Fensterklassen](../mfc/derived-window-classes.md) bieten Konstruktoren, Destruktoren und Memberfunktionen, die zum Initialisieren des Objekts, die zugrunde liegenden Windows-Strukturen zu erstellen und Zugriff auf das gekapselte `HWND`. `CWnd` bietet außerdem Memberfunktionen, die Windows-APIs zu, zum Senden von Nachrichten, die Zugriff auf das Fenster des Zustand kapseln, Konvertieren von Koordinaten, aktualisieren, scrollen, den Zugriff auf die Zwischenablage, und viele andere Aufgaben. Die meisten Windows-Fenster-Management-APIs, die Ausführen einer `HWND` Argument werden als Memberfunktionen der gekapselt `CWnd`. Die Namen der Funktionen und deren Parameter bleiben der `CWnd` Member-Funktion. Weitere Informationen zu den Windows-APIs, die durch gekapselte `CWnd`, finden Sie unter Klasse [CWnd](../mfc/reference/cwnd-class.md).

## <a name="cwnd-and-windows-messages"></a>CWnd- und Windows-Meldungen

Einer der Hauptzweck von `CWnd` besteht darin, eine Schnittstelle für die Behandlung von Windows-Meldungen, z. B. WM_PAINT- oder WM_MOUSEMOVE bereitzustellen. Die Memberfunktionen der Anzahl `CWnd` werden Handler für standard-Meldungen, die mit dem Bezeichner ab **Afx_msg** und das Präfix "On" wie z. B. `OnPaint` und `OnMouseMove`. [Nachrichten, behandeln und Zuordnung](../mfc/message-handling-and-mapping.md) werden Nachrichten und Meldungsbehandlung ausführlich behandelt. Die Informationen dort gilt gleichermaßen für die Framework Windows und diejenigen, die Sie selbst für besondere Zwecke erstellen.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Die Beziehung zwischen einem C++-Fensterobjekt und einem HWND](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [Abgeleitete Fensterklassen](../mfc/derived-window-classes.md)

- [Erstellen von Fenstern](../mfc/creating-windows.md)

- [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)

- [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Arbeiten mit Fensterobjekten](../mfc/working-with-window-objects.md)

- [Gerätekontexte](../mfc/device-contexts.md): Objekte, die Windows-Gerät zeichnen unabhängig machen

- [Grafikobjekte](../mfc/graphic-objects.md): Stifte, Pinsel, Schriftarten, Bitmaps, Paletten, Bereiche

## <a name="see-also"></a>Siehe auch

[Windows](../mfc/windows.md)

