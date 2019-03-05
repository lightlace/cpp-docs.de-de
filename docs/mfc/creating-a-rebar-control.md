---
title: Erstellen eines Grundleisten-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
ms.openlocfilehash: 0fb651aef599b64b787d96a668e2e1496c1dff8e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274452"
---
# <a name="creating-a-rebar-control"></a>Erstellen eines Grundleisten-Steuerelements

[CReBarCtrl](../mfc/reference/crebarctrl-class.md) Objekte erstellt werden soll, bevor das übergeordnete Objekt sichtbar ist. Dies minimiert die Möglichkeiten der Darstellungsprobleme.

Beispielsweise werden Grundleisten-Steuerelemente (im Rahmen von Fensterobjekten verwendet) häufig als übergeordnete Fenster für die Symbolleisten-Steuerelemente verwendet. Daher ist das übergeordnete Element des Infoleisten-Steuerelements die Frame-Window-Objekt. Da die Frame-Window-Objekt das übergeordnete Element ist die `OnCreate` Member-Funktion (des übergeordneten Elements) ist eine ausgezeichnete Möglichkeit, das Grundleistensteuerelement zu erstellen.

Verwenden einer `CReBarCtrl` Objekt, Sie werden in der Regel gehen Sie folgendermaßen vor:

### <a name="to-use-a-crebarctrl-object"></a>Ein Objekt CReBarCtrl verwendet

1. Erstellen der [CReBarCtrl](../mfc/reference/crebarctrl-class.md) Objekt.

1. Rufen Sie [erstellen](../mfc/reference/crebarctrl-class.md#create) zum Erstellen von allgemeinen Infoleisten-Steuerelements von Windows, und fügen Sie ihn auf die `CReBarCtrl` -Objekt, wobei alle gewünschten Stile.

1. Laden Sie eine Bitmap mit einem Aufruf von [LoadBitmap](../mfc/reference/cbitmap-class.md#loadbitmap), wie der Hintergrund des Infoleiste-Steuerelements verwendet werden.

1. Erstellen Sie und initialisieren Sie alle untergeordneten Fensterobjekte (Symbolleisten, Dialogfeld-Steuerelemente und So weiter), die vom Objekt Infoleisten-Steuerelement enthalten sein werden.

1. Initialisiert eine **REBARBANDINFO** Struktur mit den erforderlichen Informationen für das Band zu eingefügt werden soll.

1. Rufen Sie [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) vorhandene untergeordnete Fenster eingefügt (z. B. `m_wndReToolBar`) in das neue Grundleistensteuerelement. Weitere Informationen zum Einfügen von Bändern in einem vorhandenen Grundleistensteuerelement, finden Sie unter [Grundleisten-Steuerelemente und Bänder](../mfc/rebar-controls-and-bands.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
