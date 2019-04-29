---
title: Zeichnen in einer Ansicht
ms.date: 11/04/2016
helpviewer_keywords:
- drawing [MFC], in views
- views [MFC], printing
- views [MFC], updating
- printing [MFC], views
- views [MFC], rendering
- printing views [MFC]
- paint messages in view class [MFC]
- device contexts, screen drawings
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
ms.openlocfilehash: bc461347b56379976cdf62014507e3a15529f081
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408021"
---
# <a name="drawing-in-a-view"></a>Zeichnen in einer Ansicht

Zeichnen von fast allen in Ihrer Anwendung erfolgt in der Ansicht `OnDraw` Member-Funktion, die Sie in Ihrer Ansichtsklasse überschreiben müssen. (Die Ausnahme ist die Maus zeichnen, die in beschriebenen [Interpretieren der Benutzereingaben mit einer Benutzeransicht](../mfc/interpreting-user-input-through-a-view.md).) Ihre `OnDraw` außer Kraft setzen:

1. Ruft Daten ab, durch den Aufruf des Dokuments Memberfunktionen, die Sie bereitstellen.

1. Zeigt die Daten durch Aufrufen von Memberfunktionen der ein Gerät-Context-Objekt, das an das Framework übergibt `OnDraw`.

Wenn Daten eines Dokuments in irgendeiner Weise geändert wird, muss die Sicht neu gezeichnet werden, um die Änderungen widerzuspiegeln. Dies geschieht normalerweise, wenn der Benutzer eine Änderung über eine Sicht auf das Dokument trifft. In diesem Fall ruft die Ansicht des Dokuments [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) Memberfunktion versucht, alle Ansichten des gleichen Dokuments selbst aktualisieren zu benachrichtigen. `UpdateAllViews` Ruft jede Ansicht [OnUpdate](../mfc/reference/cview-class.md#onupdate) Member-Funktion. Die standardmäßige Implementierung des `OnUpdate` macht die Ansicht des gesamten Clientbereich ungültig. Sie können überschreiben, um nur solche Bereiche von den Clientbereich für ungültig zu erklären, die die geänderten Teile des Dokuments zugeordnet, werden soll.

Die `UpdateAllViews` Memberfunktion der Klasse `CDocument` und `OnUpdate` Memberfunktion der Klasse `CView` können Sie die Informationen, die beschreiben, welche Teile des Dokuments geändert wurden übergeben. Dieser Hinweismechanismus "" können Sie den Bereich zu beschränken, den die Sicht neu gezeichnet werden muss. `OnUpdate` übernimmt zwei Hinweisargumente für "". Die erste *lHint*, des Typs **LPARAM**, können Sie alle Daten, die Ihnen, während der zweite gefällt übergeben *pHint*, des Typs `CObject`*, ermöglicht die Übergabe ein Zeigers auf ein beliebiges Objekt abgeleitet von `CObject`.

Wenn eine Sicht ungültig wird, sendet Windows eine **WM_PAINT** Nachricht. Der Ansicht [OnPaint](../mfc/reference/cwnd-class.md#onpaint) Handlerfunktion beantwortet die Nachricht durch Erstellen eines Objekts Gerätekontext Klasse [CPaintDC](../mfc/reference/cpaintdc-class.md) und ruft der Ansicht des `OnDraw` Member-Funktion. Sie normalerweise keine override schreiben `OnPaint` Handler-Funktion.

Ein [Gerätekontext](../mfc/device-contexts.md) ist eine Windows-Datenstruktur, die Informationen über die Zeichnungsattribute eines Geräts z. B. einer Bildschirmanzeige oder einen Drucker enthält. Alle Zeichenbefehle erfolgen über ein Gerät-Context-Objekt. Für das Zeichnen auf dem Bildschirm `OnDraw` übergeben eine `CPaintDC` Objekt. Es wird für das Zeichnen auf einem Drucker, übergeben einen [CDC](../mfc/reference/cdc-class.md) Objekt für den aktuellen Drucker einrichten.

Code zum Zeichnen in der Ansicht zunächst Ruft einen Zeiger auf das Dokument ab und anschließend werden Zeichenbefehle über den Gerätekontext. Im folgenden einfachen `OnDraw` Beispiel veranschaulicht den Prozess:

[!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]

In diesem Beispiel definieren Sie die `GetData` Funktion wie ein Member der Dokumentklasse abgeleiteten.

Das Beispiel gibt die Zeichenfolge ein, aus dem Dokument, in der Ansicht zentriert wird. Wenn die `OnDraw` Aufruf ist für das Zeichnen des Bildschirms, das `CDC` Objekt übergeben wurde *pDC* ist eine `CPaintDC` , dessen Konstruktor wurde bereits aufgerufen. `BeginPaint`. Aufrufe der Funktionen zum Zeichnen erfolgen über den Gerätekontext Zeiger. Informationen über Gerätekontexte und Zeichenbefehle finden Sie in der Klasse [CDC](../mfc/reference/cdc-class.md) in die *MFC-Referenz* und [arbeiten mit Fensterobjekten](../mfc/working-with-window-objects.md).

Weitere Beispiele zum Schreiben `OnDraw`, finden Sie unter den [MFC-Beispiele](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Ansichten](../mfc/using-views.md)
