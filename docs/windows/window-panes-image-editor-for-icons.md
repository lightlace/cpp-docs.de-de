---
title: Fensterbereiche (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
- Image editor [C++], magnification
- grids, pixel
- pixel grid, Image editor
- Image editor [C++], pixel grid
- Image editor [C++], grid settings
- grid settings, Image editor
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
ms.openlocfilehash: 72b7cf056147cdbd216d861f0e710da423951c5a
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560308"
---
# <a name="window-panes-image-editor-for-icons"></a>Fensterbereiche (Bildbearbeitung für Symbole)

Die **Bildbearbeitung** Fenster zeigt ein Bild in der Regel in zwei Bereiche, die durch eine Teilerleiste getrennt. Eine Ansicht ist die tatsächliche Größe und der andere wird vergrößert (der Standard-Vergrößerungsfaktor ist 6). Die Ansichten auf diese beiden Bereiche werden automatisch aktualisiert: Änderungen in einem Bereich sofort in die andere angezeigt werden. Die beiden Bereiche erleichtern Sie auf eine vergrößerte Ansicht des Images, arbeiten in der können Sie einzelne Pixel unterscheiden und beobachten zur gleichen Zeit, die Auswirkungen Ihrer Arbeit auf die tatsächliche Größe anzeigen des Bilds.

Im linken Bereich wird so viel Speicherplatz wie erforderlich ist (bis zur Hälfte der der **Image** Fenster) um 1:1 Vergrößerung (Standard) Ihres Images anzuzeigen. Der rechte Bereich zeigt der vergrößerte Abbildung (6:1 Vergrößerung standardmäßig). Sie können ändern, dass die Vergrößerung in jedem Bereich mit der **Magnify** tool die [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) oder mithilfe der Zugriffstasten.

Sie können die kleineren Bereich vergrößern der **Bildbearbeitung** Fenster und verwenden Sie die beiden Bereiche, um verschiedene Bereiche des ein großes Bild anzuzeigen. Wählen Sie in den Bereich, um es auszuwählen.

Sie können die relativen Größen der Bereiche ändern, indem Sie den Mauszeiger auf dem Fensterteiler angezeigt, und verschieben Leiste für geteilte nach rechts oder links. Leiste für geteilte kann ganz auf beiden Seiten verschieben, wenn Sie nur einen Bereich arbeiten möchten.

Wenn die **Bildbearbeitung** Bereich vergrößert, um den Faktor 4 oder höher ist, können Sie ein Pixelraster, die die einzelnen Pixel in der Abbildung begrenzt anzeigen.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-change-the-magnification-factor"></a>Ändern des Vergrößerungsfaktors

In der Standardeinstellung die **Image** -Editor zeigt die Ansicht im linken Bereich mit der tatsächlichen Größe und die Ansicht im rechten Bereich auf 6 Mal tatsächliche Größe. Die Vergrößerungsfaktor (in der Statusleiste am unteren Rand des Arbeitsbereichs) ist das Verhältnis zwischen der tatsächlichen Größe des Bilds und die angezeigte Größe. Der Standardfaktor 6 und der Bereich liegt zwischen 1 und 10.

1. Wählen Sie die **Bildbearbeitung** Bereich, dessen Vergrößerungsfaktor ändern möchten.

1. Auf der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md), wählen Sie den Pfeil rechts neben der [Tool vergrößern](../windows/toolbar-image-editor-for-icons.md) , und wählen Sie im Untermenü des Vergrößerungsfaktors: **1 X**, **2 X**, **6 X**, oder **8 X**.

   > [!NOTE]
   > Auf einen Vergrößerungsfaktor nicht aufgelistet, die der **Magnify** tool können Sie die Zugriffstasten.

## <a name="to-display-or-hide-the-pixel-grid"></a>Zum Anzeigen oder Ausblenden des Pixelrasters

Für alle **Bildbearbeitung** Bereiche mit einem Vergrößerungsfaktor von 4 oder höher können Sie ein Raster, das die einzelnen Pixel in der Abbildung begrenzt anzeigen.

1. Auf der **Image** , wählen Sie im Menü **Rastereinstellungen**.

1. Wählen Sie die **Pixelraster** Kontrollkästchen, um das Raster anzeigen oder deaktivieren Sie das Kontrollkästchen, um das Raster auszublenden.

> [!TIP]
> Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)