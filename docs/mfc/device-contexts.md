---
title: Gerätekontexte
ms.date: 11/04/2016
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
ms.openlocfilehash: d5337e8d8b83a641458a15612803feeec3b6361c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508660"
---
# <a name="device-contexts"></a>Gerätekontexte

Ein Gerätekontext ist eine Windows-Datenstruktur, die Informationen über die Zeichnungs Attribute eines Geräts (z. b. eine Anzeige oder einen Drucker) enthält. Alle Zeichnungs Aufrufe werden über ein Gerätekontext Objekt durchgeführt, das die Windows-APIs zum Zeichnen von Linien, Formen und Text kapselt. Geräte Kontexte ermöglichen eine geräteunabhängige Zeichnung in Windows. Geräte Kontexte können verwendet werden, um auf den Bildschirm, den Drucker oder eine Metadatei zu zeichnen.

[CPaintDC](../mfc/reference/cpaintdc-class.md) -Objekte kapseln das gängige Idiom von Fenstern, den Aufruf `BeginPaint` der Funktion, das anschließende zeichnen im Gerätekontext und das anschließende `EndPaint` Aufrufen der Funktion. Der `CPaintDC` Konstruktor ruft `BeginPaint` für Sie auf, und der Dekonstruktor ruft `EndPaint`auf. Der vereinfachte Prozess besteht darin, das [CDC](../mfc/reference/cdc-class.md) -Objekt zu erstellen, zu zeichnen und `CDC` dann das Objekt zu zerstören. Im Rahmen des Frameworks ist ein Großteil dieses Prozesses auch automatisiert. Insbesondere wird Ihrer `OnDraw` Funktion ein `CPaintDC` bereits vorbereitetes (via)- `OnPrepareDC`Wert übermittelt, und Sie zeichnen sich einfach darauf aus. Sie wird durch das Framework zerstört, und der zugrunde liegende Gerätekontext wird für Windows bei Rückgabe des Aufrufes `OnDraw` der Funktion freigegeben.

[CClientDC](../mfc/reference/cclientdc-class.md) -Objekte kapseln das Arbeiten mit einem Gerätekontext, der nur den Client Bereich eines Fensters darstellt. Der `CClientDC` Konstruktor ruft die `GetDC` -Funktion auf, und der Dekonstruktor Ruft die `ReleaseDC` -Funktion auf. [Cwindowdc](../mfc/reference/cwindowdc-class.md) -Objekte Kapseln einen Gerätekontext, der das gesamte Fenster einschließlich seines Frames darstellt.

[Cmetafiledc](../mfc/reference/cmetafiledc-class.md) -Objekte kapseln das Zeichnen in eine Windows-Metadatendatei. Im Gegensatz zu der `CPaintDC` an `OnDraw`übergebenen muss in diesem Fall [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) selbst aufgerufen werden.

## <a name="mouse-drawing"></a>Maus Zeichnung

Die meisten Zeichen in einem Framework- `OnDraw` Programm – und damit die meisten Gerätekontext arbeiten – werden in der Member-Funktion der Sicht ausgeführt. Sie können jedoch weiterhin Gerätekontext Objekte für andere Zwecke verwenden. Um z. b. nach Verfolgungs Feedback für die Mausbewegung in einer Ansicht bereitzustellen, müssen Sie direkt in die Ansicht ziehen `OnDraw` , ohne darauf warten zu müssen, dass aufgerufen wird.

In einem solchen Fall können Sie ein [CClientDC](../mfc/reference/cclientdc-class.md) -Gerätekontext Objekt verwenden, um direkt in die Ansicht zu zeichnen.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Geräte Kontexte (Definition)](/windows/win32/gdi/device-contexts)

- [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)

- [Interpretieren der Benutzereingaben in einer Ansicht](../mfc/interpreting-user-input-through-a-view.md)

- [Linien und Kurven](/windows/win32/gdi/lines-and-curves)

- [Gefüllte Formen](/windows/win32/gdi/filled-shapes)

- [Schriftarten und Text](/windows/win32/gdi/fonts-and-text)

- [Farben](/windows/win32/gdi/colors)

- [Koordinaten Bereiche und Transformationen](/windows/win32/gdi/coordinate-spaces-and-transformations)

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)
