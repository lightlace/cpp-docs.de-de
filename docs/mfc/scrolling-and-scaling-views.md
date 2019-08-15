---
title: Bildlauf und Skalierung für Ansichten
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
ms.openlocfilehash: 7064880c5ceef8e7dc3e35bb7ef5bc700b0842d2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511229"
---
# <a name="scrolling-and-scaling-views"></a>Bildlauf und Skalierung für Ansichten

MFC unterstützt Sichten, die einen Bildlauf durchführen, und Sichten, die automatisch auf die Größe des Rahmen Fensters skaliert werden. \- `CScrollView` Klasse unterstützt beide Arten von Sichten.

Weitere Informationen zum Scrollen und Skalieren finden Sie unter Class [CScrollView](../mfc/reference/cscrollview-class.md) in der *MFC-Referenz*. Ein Beispiel für einen Bildlauf finden Sie im [Scribble](../overview/visual-cpp-samples.md)-Beispiel.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- Scrollen einer Ansicht

- Skalieren einer Ansicht

- [Koordinaten anzeigen](/windows/win32/gdi/window-coordinate-system)

##  <a name="_core_scrolling_a_view"></a>Scrollen einer Ansicht

Häufig ist die Größe eines Dokuments größer als die Größe, die in der Ansicht angezeigt werden kann. Dies kann der Fall sein, wenn sich die Daten des Dokuments erhöhen oder der Benutzer das Fenster verkleinert, das die Ansicht bildet. In solchen Fällen muss die Sicht den Bildlauf unterstützen.

Jede Ansicht kann Bild Lauf leisten Meldungen in Ihren `OnHScroll` -und-Member- `OnVScroll` Funktionen verarbeiten. Sie können entweder die Verarbeitung der Bild Lauf Leiste in diesen Funktionen implementieren, die gesamte Arbeit erledigen, oder Sie können die- `CScrollView` Klasse verwenden, um den Bildlauf für Sie zu verarbeiten.

`CScrollView` führt Folgendes aus:

- Verwalten von Fenstern und viewportgrößen und Karten Modi

- Führt in Reaktion auf Bild Lauf leisten Meldungen automatisch einen Bildlauf durch.

Sie können angeben, wie viel ein Bildlauf für eine "Seite" durchführen soll (wenn der Benutzer in eine Schiebe leisten Schaltfläche klickt) und eine "Linie" (wenn der Benutzer auf einen Bild Lauf Pfeil klickt). Planen Sie diese Werte entsprechend der Art ihrer Ansicht. Beispielsweise können Sie in 1-Pixel-Schritten für eine Grafik Ansicht einen Bildlauf durchführen, aber in Schritten basierend auf der Zeilenhöhe in Textdokumenten.

##  <a name="_core_scaling_a_view"></a>Skalieren einer Ansicht

Wenn Sie möchten, dass die Ansicht automatisch an die Größe des Rahmen Fensters angepasst wird, können `CScrollView` Sie anstelle eines Bildlaufs für die Skalierung verwenden. Die logische Ansicht wird gestreckt oder verkleinert, sodass Sie exakt an den Client Bereich des Fensters angepasst wird. Eine skalierte Ansicht hat keine Scrollleisten.

## <a name="see-also"></a>Siehe auch

[Verwenden von Ansichten](../mfc/using-views.md)
