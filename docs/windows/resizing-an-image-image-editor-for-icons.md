---
title: Größenänderungen bei Bildern (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
- size [C++], images
- images [C++], cropping
- images [C++], extending
- Image editor [C++], cropping or extending images
- Image editor [C++], shrinking and stretching images
- images [C++], stretching
- images [C++], shrinking
- bitmaps [C++], shrinking
- bitmaps [C++], stretching
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
ms.openlocfilehash: d88a4cccff5b9b7b6303329782b7367cb953b13d
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484967"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Größenänderungen bei Bildern (Bildbearbeitung für Symbole)

Das Verhalten der **Image** -Editor beim Ändern der Bildgröße, hängt davon ab, ob Ihr [ausgewählten](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) das gesamte Bild oder nur eines Teils davon.

Wenn die Auswahl nur einen Teil des Bilds, enthält die **Image** Editor reduziert die Auswahl durch Löschen von Zeilen oder Spalten von Pixeln, und füllen die frei werdenden Regionen mit der aktuellen Hintergrundfarbe. Sie können auch die Auswahl Strecken, durch das Duplizieren von Zeilen oder Spalten von Pixeln.

Wenn die Auswahl auf das gesamte Bild, enthält die **Image** Editor entweder verkleinert und das Bild wird gestreckt oder schneidet und erweitert ihn.

Es gibt zwei Mechanismen zum Ändern der Bildgröße: Ziehpunkte und [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Sie Ziehen der Ziehpunkte, um die Größe des gesamten oder einen Teil eines Bilds zu ändern. Ziehpunkte, die Sie ziehen können, sind gefüllt. Sie können keine Handles ziehen, die leer sind. Verwenden der **Eigenschaften** Fenster zum Ändern der Größe des gesamtes image nur nicht für eine ausgewählte Komponente.

![Ziehpunkte in einer Bitmap](../mfc/media/vcimageeditorsizinghandles.gif "VcImageEditorSizingHandles")<br/>
Ziehpunkte

> [!NOTE]
> Wenn man die **Kachel Raster** gewählten Option in der [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md), klicken Sie dann Ändern der Größe von Snapshots an der nächsten Kachel. Wenn nur die **Pixelraster** Option ist aktiviert (Standardeinstellung), Ändern der Größe von Snapshots und dem nächsten verfügbaren Pixel.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-resize-an-entire-image-using-the-properties-window"></a>Zum Ändern der Größe eines ganzen Bilds mithilfe des Eigenschaftenfensters

1. Öffnen Sie das Bild, dessen Eigenschaften Sie ändern möchten.

1. In der **Breite** und **Höhe** Dialogfelder in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), geben Sie die Dimensionen, die Sie möchten.

   Wenn Sie die Größe des Bilds erhöhen, das **Image** -Editor wird das Bild an der rechten Seite nach unten, oder beide erweitert und füllt den neuen Bereich in der aktuellen Hintergrundfarbe. Das Bild wird nicht gestreckt.

   Wenn Sie die Größe des Bilds, verkürzen die **Image** Editor schneidet das Bild auf den rechten oder unteren Rand oder beides.

   > [!NOTE]
   > Können Sie die **Breite** und **Höhe** Eigenschaften, die nur das gesamte Bild nicht zum Ändern der Größe eines markierten Größe zu ändern.

## <a name="to-crop-or-extend-an-entire-image"></a>Zuschneiden oder Erweitern eines ganzen Bildes

1. Wählen Sie das gesamte Bild.

   Wenn Teil des Images derzeit ausgewählt ist, und Sie das gesamte Bild auswählen möchten, wählen Sie eine beliebige Stelle auf das Bild außerhalb des Rahmens der aktuellen Auswahl.

1. Ziehen Sie einen Ziehpunkt, bis das Bild auf die richtige Größe hat.

In der Regel die **Image** Editor schneidet oder ein Bild vergrößert, wenn Sie deren Größe ändern, indem Sie einen der Ziehpunkte verschieben. Gedrückter der **UMSCHALT** gedrückt, während Sie einen der Ziehpunkte, Verschieben der **Image** Editor verkleinert wird oder das Bild gestreckt.

## <a name="to-shrink-or-stretch-an-entire-image"></a>So verkleinern oder Strecken eines ganzen Bildes

1. Wählen Sie das gesamte Bild.

   Wenn ein Teil des Images derzeit ausgewählt ist, und Sie das gesamte Bild auswählen möchten, wählen Sie eine beliebige Stelle auf das Bild außerhalb des Rahmens der aktuellen Auswahl.

1. Halten Sie die **UMSCHALT** gedrückt, und ziehen Sie einen Ziehpunkt, bis das Bild auf die richtige Größe hat.

## <a name="to-shrink-or-stretch-part-of-an-image"></a>So verkleinern oder Strecken Teil eines Images

1. Wählen Sie den Teil des Abbilds aus, die Sie anpassen möchten. Weitere Informationen finden Sie unter [Markieren eines Bildbereichs des Bilds](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md).

1. Ziehen Sie die Ziehpunkte, bis die Auswahl der richtigen Größe ist.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)