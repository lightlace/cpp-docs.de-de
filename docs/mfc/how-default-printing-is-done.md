---
title: Funktionsweise des Standarddrucks
ms.date: 11/04/2016
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
ms.openlocfilehash: 5f7971b48c9050e315b2fd57d2f3449517afa07e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295304"
---
# <a name="how-default-printing-is-done"></a>Funktionsweise des Standarddrucks

Dieser Artikel beschreibt die Standard-Druckvorgang in Windows in Bezug auf das MFC-Framework.

In MFC-Anwendungen, die View-Klasse verfügt über eine Memberfunktion mit dem Namen `OnDraw` , der den Zeichencode enthält. `OnDraw` verwendet einen Zeiger auf eine [CDC](../mfc/reference/cdc-class.md) -Objekt als Parameter. Dass `CDC` Objekt darstellt, den Gerätekontext aus, um das Bild erzeugten empfangen `OnDraw`. Wenn das Fenster des Dokuments empfängt eine [WM_PAINT](/windows/desktop/gdi/wm-paint) Nachricht, das Framework ruft `OnDraw` und übergibt einen Gerätekontext für den Bildschirm (eine [CPaintDC](../mfc/reference/cpaintdc-class.md) Objekt, das genau zu sein). Dementsprechend `OnDraw`durchläuft Sie die Ausgabe auf dem Bildschirm.

Bei der Programmierung für Windows ist die Ausgabe auf den Drucker sehr ähnlich ist, zum Senden der Ausgabe auf dem Bildschirm. Dies ist, da die Windows Graphics Device Interface (GDI) unabhängig von der Hardware ist. Sie können die gleichen GDI-Funktionen für die Bildschirmanzeige oder für das Drucken, indem Sie einfach mit den entsprechenden Gerätekontext verwenden. Wenn die `CDC` -Objekt, `OnDraw` empfängt stellt den Drucker, `OnDraw`durchläuft Sie die Ausgabe an den Drucker.

Hier wird erläutert, wie die MFC-Anwendungen einfach Drucken ohne zusätzlichen Aufwand ihrerseits ausführen können. Das Framework übernimmt das Dialogfeld Drucken anzeigen und erstellen einen Gerätekontext für den Drucker. Wenn der Benutzer den Befehl Drucken über das Menü Datei auswählt, wird der Ansicht übergeben dieser Gerätekontext zu `OnDraw`, die das Dokument auf dem Drucker zeichnet.

Es gibt jedoch einige wichtige Unterschiede zwischen Bildschirm- und drucken. Wenn Sie drucken möchten, müssen Sie das Dokument in unterschiedliche Seiten und die Anzeige, die sie einzeln nacheinander, anstelle der Anzeige unabhängig Bereich sichtbar ist in einem Fenster teilen. Daneben müssen Sie beachten Sie die Größe des Papiers (gibt an, ob es briefgröße liegt, legal-Format, oder einen Umschlag ist). Sie sollten sich in verschiedenen Ausrichtungen, wie Quer- oder Hochformat gedruckt. Die Microsoft Foundation Class-Bibliothek kann nicht vorhersagen, wie dieser Probleme in Ihrer Anwendung behandelt werden, damit es sich um ein Protokoll für die Sie zum Hinzufügen dieser Funktionen bietet.

Dass das Protokoll in diesem Artikel beschriebene [mehrseitige Dokumente](../mfc/multipage-documents.md).

## <a name="see-also"></a>Siehe auch

[Drucken](../mfc/printing.md)
