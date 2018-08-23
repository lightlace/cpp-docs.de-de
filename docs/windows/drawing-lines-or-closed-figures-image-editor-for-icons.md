---
title: Zeichnen von Linien oder geschlossenen Körpern (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- closed figures, drawing
- lines [C++], painting
- lines [C++], drawing
- Image editor [C++], drawing lines
- shapes, drawing
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d1eba17d961db9ec96e4250e49c10ecad5b75b4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590729"
---
# <a name="drawing-lines-or-closed-figures-image-editor-for-icons"></a>Zeichnen von Linien oder geschlossenen Körpern (Bildbearbeitung für Symbole)

Die Bild-Editor-tools für das Zeichnen von Linien und geschlossene Figuren, die alle auf die gleiche Weise funktioniert: Sie setzen Sie die Einfügemarke an einem bestimmten Punkt, und ziehen Sie auf einen anderen. Für Zeilen sind folgende Punkte der Endpunkte. Diese Punkte sind geschlossenen Figuren gegenüberliegenden Ecke eines Rechtecks umgebenden in der Abbildung.

Zeilen werden in eine Breite bestimmt, indem die aktuelle Auswahl der Pinsel gezeichnet, und gerahmter Abbildungen hängt von der aktuellen Breite Auswahl gezeichnet werden. Linien und alle Zahlen, sowohl mit einem Frame versehen und gefüllt ist, werden gezeichnet, wenn Sie mit die rechten Maustaste drücken in der aktuellen Vordergrundfarbe, wenn Sie die linke Maustaste drücken oder in der aktuellen Hintergrundfarbe.

### <a name="to-draw-a-line"></a>So zeichnen Sie eine Linie

1. Auf der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) (oder von der **Image** Menü **Tools** Befehl), klicken Sie auf die **Zeile** Tool.

2. Bei Bedarf einen Pinsel und Farben auswählen:

   - In der [Farben (Palette)](../windows/colors-window-image-editor-for-icons.md), klicken Sie auf die linke Maustaste gedrückt, wählen Sie eine Vordergrundfarbe oder der rechten Maustaste auf eine Hintergrundfarbe auswählen.

   - In der [Optionsauswahl](../windows/toolbar-image-editor-for-icons.md), klicken Sie auf eine Form den Pinsel, die Sie verwenden möchten, die darstellt.

3. Platzieren Sie den Mauszeiger am Anfangspunkt der Linie.

4. Ziehen Sie in Endpunkts der Linie.

### <a name="to-draw-a-closed-figure"></a>Um eine geschlossene Form zu zeichnen.

1. Auf der **Bild-Editor** Symbolleiste (oder von der **Image** Menü **Tools** Befehl), klicken Sie auf eine **Zeichnen geschlossener Körper** Tool.

   Die **Zeichnen geschlossener Körper** Tools erstellen Zahlen auf der jeweiligen Schaltfläche dargestellt.

2. Bei Bedarf eine Linienstärke und Farben auswählen.

3. Bewegen Sie den Zeiger auf eine Ecke des rechteckigen Bereichs, in dem Sie in der Abbildung zeichnen möchten.

4. Ziehen Sie den Mauszeiger auf die diagonal gegenüber Ecke aus.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)  
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)  
[Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)