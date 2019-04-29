---
title: Festlegen des CStatusBarCtrl-Objektmodus
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: a6d1a0edb356f9737aa287809dd8bca4146c1854
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307717"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Festlegen des CStatusBarCtrl-Objektmodus

Es gibt zwei Modi für einen `CStatusBarCtrl` Objekt: einfache und nicht einfache. In den meisten Fällen müssen Ihre Statusleisten-Steuerelement von einem oder mehreren Teilen zusammen mit Text und vielleicht ein Symbol oder Symbole. Dies wird als nicht einfacher Modus bezeichnet. Weitere Informationen zu diesen Modus, finden Sie unter [Initialisieren der Teile eines CStatusBarCtrl-Objekts](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).

Es gibt jedoch Fälle, in dem Sie nur eine einzelne Textzeile anzeigen müssen. In diesem Fall ist der einfache Modus für Ihre Anforderungen ausreichend. So ändern Sie den Modus der `CStatusBarCtrl` auf Simple Objekt, rufen Sie die [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) Member-Funktion. Sobald das StatusBar-Steuerelement im einfachen Modus ist, legen Sie den Text durch Aufrufen der `SetText` Memberfunktion wird die Weitergabe von 255 als Wert für die *nPane* Parameter.

Können Sie die [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) Funktion bestimmen, welcher Modus der `CStatusBarCtrl` Objekt befindet sich in.

> [!NOTE]
>  Wenn Statusobjekt Leiste aus zeigt nicht einfache, einfach geändert wird, oder umgekehrt, das Fenster wird sofort neu gezeichnet und, falls zutreffend, werden alle definierten Abschnitte automatisch wiederhergestellt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
