---
title: Fensterbereiche (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b4177313a9fa05d160935e6602454ff6c73ab34f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398747"
---
# <a name="window-panes-image-editor-for-icons"></a>Fensterbereiche (Bildbearbeitung für Symbole)

Die **Bildbearbeitung** Fenster zeigt ein Bild in der Regel in zwei Bereiche, die durch eine Teilerleiste getrennt. Eine Ansicht ist die tatsächliche Größe und der andere wird vergrößert (der Standard-Vergrößerungsfaktor ist 6). Die Ansichten auf diese beiden Bereiche werden automatisch aktualisiert: Änderungen in einem Bereich sofort in die andere angezeigt werden. Die beiden Bereiche erleichtern Sie auf eine vergrößerte Ansicht des Images, arbeiten in der können Sie einzelne Pixel unterscheiden und beobachten zur gleichen Zeit, die Auswirkungen Ihrer Arbeit auf die tatsächliche Größe anzeigen des Bilds.

Im linken Bereich wird so viel Speicherplatz wie erforderlich ist (bis zur Hälfte der der **Image** Fenster) um 1:1 Vergrößerung (Standard) Ihres Images anzuzeigen. Der rechte Bereich zeigt der vergrößerte Abbildung (6:1 Vergrößerung standardmäßig). Können Sie [Ändern der Vergrößerung](../windows/changing-the-magnification-factor-image-editor-for-icons.md) in jedem Bereich mit der **Magnify** tool die [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) oder mithilfe der Zugriffstasten.

Sie können die kleineren Bereich vergrößern der **Bildbearbeitung** Fenster und verwenden Sie die beiden Bereiche, um verschiedene Bereiche des ein großes Bild anzuzeigen. Klicken Sie im Bereich, um es auszuwählen.

Sie können die relativen Größen der Bereiche ändern, indem Sie den Mauszeiger auf dem Fensterteiler angezeigt, und verschieben Leiste für geteilte nach rechts oder links. Leiste für geteilte kann ganz auf beiden Seiten verschieben, wenn Sie nur einen Bereich arbeiten möchten.

Wenn die **Bildbearbeitung** Bereich ist, vergrößert, um den Faktor 4 oder höher, können Sie [Pixelraster anzeigen](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) , die die einzelnen Pixel in der Abbildung begrenzt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)