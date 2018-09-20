---
title: Gerätekontexte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27203b5b93d69c29df29e64f872efb8e5f1828e1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437639"
---
# <a name="device-contexts"></a>Gerätekontexte

Ein Gerätekontext ist eine Windows-Datenstruktur, die mit Informationen über die Zeichnungsattribute eines Geräts z. B. einer Bildschirmanzeige oder einen Drucker. Alle Zeichenbefehle erfolgen über ein Gerät-Context-Objekt, die der Windows-APIs zum Zeichnen von Linien, Formen und Text kapselt. Gerätekontexte ermöglichen geräteunabhängige Zeichnung in Windows. Gerätekontexte können verwendet werden, auf dem Bildschirm, an den Drucker oder auf einer Metadatei zu zeichnen.

[CPaintDC](../mfc/reference/cpaintdc-class.md) Objekte kapseln, die allgemeine Vorgehensweise von Windows, das Aufrufen der `BeginPaint` -Funktion, und klicken Sie dann in den Gerätekontext zu zeichnen, wird beim Aufruf der `EndPaint` Funktion. Die `CPaintDC` Konstruktoraufrufe `BeginPaint` für Sie und der Destruktor ruft `EndPaint`. Vereinfachte Prozess ist die Erstellung der [CDC](../mfc/reference/cdc-class.md) Objekt gezeichnet werden soll, und anschließend Zerstören der `CDC` Objekt. Im Framework ist ein Großteil dieses Prozesses automatisiert. Insbesondere Ihre `OnDraw` Funktion übergeben wird eine `CPaintDC` bereits vorbereitet (über `OnPrepareDC`), und ziehen Sie einfach hinein. Es wird durch das Framework zerstört und der zugrunde liegenden Gerätekontext für Windows freigegeben ist, bei der Rückgabe aus dem Aufruf von Ihrem `OnDraw` Funktion.

[CClientDC](../mfc/reference/cclientdc-class.md) Objekte kapseln arbeiten mit einem Gerätekontext, die nur den Clientbereich eines Fensters darstellt. Die `CClientDC` Konstruktor ruft die `GetDC` -Funktion und der Destruktor ruft die `ReleaseDC` Funktion. [CWindowDC](../mfc/reference/cwindowdc-class.md) Objekte kapseln einen Gerätekontext, die das gesamte Fenster, einschließlich des Rahmens darstellt.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md) Objekte zeichnen in einer Windows-Metadatei zu kapseln. Im Gegensatz zu den `CPaintDC` übergeben `OnDraw`, müssen Sie in diesem Fall aufrufen [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) selbst.

## <a name="mouse-drawing"></a>Zeichnen mit der Maus

Die meisten Zeichnen in einem Frameworkprogramm – und somit die meisten-Gerätekontext – erfolgt in der Ansicht `OnDraw` Member-Funktion. Sie können allerdings weiterhin gerätekontextobjekten für andere Zwecke verwenden. Z. B. um nachverfolgung Feedback für das Verschieben der Maus in einer Ansicht bereitzustellen, müssen Sie direkt in die Ansicht zu zeichnen, ohne zu warten `OnDraw` aufgerufen werden.

In diesem Fall können Sie eine [CClientDC](../mfc/reference/cclientdc-class.md) gerätkontextobjekt direkt in die Ansicht zu zeichnen.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Gerätekontexte (Definition)](https://msdn.microsoft.com/library/windows/desktop/dd183553)

- [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)

- [Interpretieren der Benutzereingaben in einer Ansicht](../mfc/interpreting-user-input-through-a-view.md)

- [Linien und Kurven](https://msdn.microsoft.com/library/windows/desktop/dd145028)

- [Gefüllte Formen](https://msdn.microsoft.com/library/windows/desktop/dd162714)

- [Schriftarten und text](/windows/desktop/gdi/fonts-and-text)

- [Farben](https://msdn.microsoft.com/library/windows/desktop/dd183450)

- [Koordinatensysteme und Transformationen](https://msdn.microsoft.com/library/windows/desktop/dd183475)

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)

