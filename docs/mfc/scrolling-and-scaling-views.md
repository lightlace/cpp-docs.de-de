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
ms.openlocfilehash: acef79a89da88773da564fc965a607e2fd5b53f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626099"
---
# <a name="scrolling-and-scaling-views"></a>Bildlauf und Skalierung für Ansichten

MFC unterstützt, Ansichten, die einen Bildlauf durchführen und Ansichten, die automatisch auf die Größe des Rahmenfensters skaliert werden, in der sie angezeigt wird. Klasse `CScrollView` unterstützt beide Arten von Ansichten.

Weitere Informationen zu den Bildlauf und Skalierung, finden Sie unter Klasse [CScrollView](../mfc/reference/cscrollview-class.md) in die *MFC-Referenz*. Ein Beispiel für Bildlauf, finden Sie unter den [Scribble-Beispiels](../visual-cpp-samples.md).

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- Bildlauf in einer Ansicht

- Skalieren einer Ansicht

- [Koordinaten der Strukturansicht](/windows/desktop/gdi/window-coordinate-system)

##  <a name="_core_scrolling_a_view"></a> Bildlauf in einer Ansicht

Häufig ist die Größe eines Dokuments größer als die Größe, die seine Ansicht anzeigen kann. Dies kann auftreten, da die Daten des Dokuments erhöht oder der Benutzer verkleinert das Fenster, das die Ansicht von frames. In solchen Fällen muss die Ansicht einen Bildlauf unterstützen.

Jeder Ansicht kann behandeln, Bildlaufleisten-Nachrichten in der `OnHScroll` und `OnVScroll` Memberfunktionen. Können Sie entweder implementieren Bildlaufleisten--Nachrichtenverarbeitung in dieser Funktionen, die gesamte Arbeit tun sich selbst, oder Sie können die `CScrollView` -Klasse zur Verarbeitung von Bildlauf für Sie.

`CScrollView` führt Folgendes aus:

- Verwaltet Fenster-und Viewport und Zuordnungsmodi

- Führt einen Bildlauf automatisch als Reaktion auf Bildlaufleisten-Nachrichten

Sie können wie viel angeben, um das Scrollen für ein "Page" (wenn der Benutzer in einer Bildlaufleiste klickt) und eine "Linie" (wenn der Benutzer in einen Bildlaufpfeil klickt). Planen Sie diese Werte entsprechend die Art Ihrer Ansicht an. Beispielsweise empfiehlt es sich in 1-Pixel-Schritten für eine Grafikansicht jedoch in acht Inkrementen basierend auf der Zeilenhöhe im Text-Dokumenten zu scrollen.

##  <a name="_core_scaling_a_view"></a> Skalieren einer Ansicht

Wenn die Ansicht, um automatisch die Größe des zugehörigen Rahmenfenster angepasst werden soll, können Sie `CScrollView` für die Skalierung, anstatt das Durchführen eines Bildlaufs. Die logische Ansicht wird gestreckt oder verkleinert werden, genau entsprechend Clientbereich des Fensters. Eine skalierte Ansicht besitzt keine Bildlaufleisten.

## <a name="see-also"></a>Siehe auch

[Verwenden von Ansichten](../mfc/using-views.md)

