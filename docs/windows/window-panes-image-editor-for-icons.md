---
title: Fensterbereiche (Bildbearbeitung für Symbole) | Microsoft Docs
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
ms.openlocfilehash: e899729e70db089c1c55f00aa9c4196a22c67060
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892838"
---
# <a name="window-panes-image-editor-for-icons"></a>Fensterbereiche (Bildbearbeitung für Symbole)
Die Grafik-Editor-Fenster zeigt ein Bild in der Regel in zwei Bereiche, die durch eine Trennleiste getrennt. Eine Sicht ist die tatsächliche Größe und der andere wird vergrößert (der Standard-Vergrößerungsfaktor ist 6). Die Ansichten auf diese beiden Bereiche werden automatisch aktualisiert: von Ihnen in einem Bereich vorgenommenen Änderungen werden sofort in den anderen angezeigt. Die beiden Bereiche erleichtern Ihnen, auf eine vergrößerte Ansicht des Bilds, zu arbeiten, in dem Sie können einzelne Pixel unterscheiden und, zur gleichen Zeit, beobachten Sie die Auswirkungen Ihrer Arbeit für die Sicht tatsächliche Größe des Bilds.  
  
 Im linken Bereich wird verwendet, wie viel Speicherplatz wie (bis zur Hälfte des Fensters Bild) erforderlich, um die Vergrößerung der 1:1 (Standard) des Bilds anzuzeigen. Der rechte Bereich zeigt das vergrößerte Bild (6:1-Vergrößerung in der Standardeinstellung). Sie können [Ändern der Vergrößerung](../windows/changing-the-magnification-factor-image-editor-for-icons.md) in jedem Bereich mit der **vergrößern** tool die [Grafik-Editor-Symbolleiste](../windows/toolbar-image-editor-for-icons.md) oder mithilfe der Zugriffstasten.  
  
 Sie können den kleineren Bereich des Grafik-Editor-Fensters vergrößern und verwenden die beiden Bereiche an unterschiedliche geografischen Regionen ein großes Bild anzeigen. Klicken Sie in den Bereich, um ihn auszuwählen.  
  
 Sie können die relativen Größen der Bereiche ändern, indem Sie den Mauszeiger auf die Leiste für geteilte und die Leiste für geteilte in links oder rechts verschieben. Leiste für geteilte kann ganz auf beiden Seiten verschieben, wenn Sie nur einen Bereich bearbeiten möchten.  
  
 Wenn der Bereich des Grafik-Editor mit einem Faktor von 4 oder höher vergrößert wird, können Sie [Pixelraster anzeigen](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) , die die einzelnen Pixel in der Abbildung begrenzt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

