---
title: Funktionsweise des Standarddrucks
ms.date: 11/04/2016
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
ms.openlocfilehash: 5019bcad769c4b7cdb699facef145a21d9b5e11c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508417"
---
# <a name="how-default-printing-is-done"></a>Funktionsweise des Standarddrucks

Dieser Artikel erläutert den Standarddruck Prozess in Windows in Bezug auf das MFC-Framework.

In MFC-Anwendungen hat die Ansichts Klasse eine Member- `OnDraw` Funktion mit dem Namen, die den gesamten Zeichnungs Code enthält. `OnDraw`nimmt einen Zeiger auf ein [CDC](../mfc/reference/cdc-class.md) -Objekt als Parameter an. Dieses `CDC` Objekt stellt den Gerätekontext dar, der das von `OnDraw`erzeugte Bild empfangen soll. Wenn das Fenster, in dem das Dokument angezeigt wird, eine [WM_PAINT](/windows/win32/gdi/wm-paint) - `OnDraw` Nachricht empfängt, ruft das Framework einen Gerätekontext für den Bildschirm (ein [CPaintDC](../mfc/reference/cpaintdc-class.md) -Objekt, das spezifisch ist) ab und übergibt es an ihn. Dementsprechend wird `OnDraw`die Ausgabe auf den Bildschirm geleitet.

Beim Programmieren für Windows ist das Senden der Ausgabe an den Drucker sehr ähnlich wie das Senden der Ausgabe an den Bildschirm. Dies liegt daran, dass die Windows Graphics Device Interface (GDI) Hardware unabhängig ist. Sie können die gleichen GDI-Funktionen für die Bildschirm Anzeige oder zum Drucken einfach mithilfe des entsprechenden Geräte Kontexts verwenden. Wenn das `CDC` Objekt, `OnDraw` das empfängt, den Drucker `OnDraw`darstellt, wird die Ausgabe an den Drucker gesendet.

Auf diese Weise wird erläutert, wie MFC-Anwendungen einen einfachen Druck ausführen können, ohne dass ein zusätzlicher Aufwand erforderlich ist. Das Framework kümmert sich um das Anzeigen des Dialog Felds drucken und das Erstellen eines Geräte Kontexts für den Drucker. Wenn der Benutzer den Befehl Drucken aus dem Menü Datei auswählt, übergibt die Ansicht diesen Gerätekontext `OnDraw`an, sodass das Dokument auf dem Drucker gezeichnet wird.

Es gibt jedoch einige bedeutende Unterschiede zwischen Druck und Bildschirm Anzeige. Wenn Sie drucken, müssen Sie das Dokument in verschiedene Seiten aufteilen und nacheinander anzeigen, anstatt den Teil anzuzeigen, der in einem Fenster sichtbar ist. Als Konsequenz müssen Sie die Größe des Papiers berücksichtigen (unabhängig davon, ob es sich um eine Buch Größe, eine gesetzliche Größe oder einen Umschlag handelt). Möglicherweise möchten Sie in verschiedenen Ausrichtungen drucken, wie z. b. Querformat oder Hochformat. Der Microsoft Foundation Class-Bibliothek kann nicht vorhersagen, wie Ihre Anwendung diese Probleme behandelt, sodass Sie ein Protokoll bereitstellt, mit dem Sie diese Funktionen hinzufügen können.

Dieses Protokoll wird im Artikel [mehrseitige Dokumente](../mfc/multipage-documents.md)beschrieben.

## <a name="see-also"></a>Siehe auch

[Drucken](../mfc/printing.md)
