---
title: Größenänderungen bei Bildern (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41494e8b88f41c4c842e95e9f8a9f5da0247739f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605642"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Größenänderungen bei Bildern (Bildbearbeitung für Symbole)
Das Verhalten des Grafik-Editors bei größenänderungen bei Bildern, hängt davon ab, ob Sie wurde [ausgewählten](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) das gesamte Bild oder nur eines Teils davon.  
  
 Wenn die Auswahl nur einen Teil des Bilds enthält, der Bild-Editor reduziert die Auswahl durch das Löschen von Zeilen oder Spalten von Pixeln und füllen die frei werdenden Regionen mit der aktuellen Hintergrundfarbe oder streckt die Auswahl von Zeilen oder Spalten von Pixeln duplizieren.  
  
 Wenn die Auswahl auf das gesamte Bild enthält, der Bild-Editor entweder verkleinert und das Bild wird gestreckt oder schneidet und erweitert ihn.  
  
 Es gibt zwei Mechanismen zum Ändern der Bildgröße: Ziehpunkte und [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Sie können den Ziehpunkt zum Ändern der Größe des gesamten oder einen Teil eines Images ziehen. Ziehpunkte, die Sie ziehen können, sind gefüllt. Sie können keine Handles ziehen, die leer sind. Sie können im Eigenschaftenfenster zum Ändern der Größe nur des gesamten Bilds nicht für eine ausgewählte Komponente verwenden.  
  
 ![Ziehpunkte in einer Bitmap](../mfc/media/vcimageeditorsizinghandles.gif "VcImageEditorSizingHandles")  
Ziehpunkte  
  
> [!NOTE]
>  Wenn Sie die Kachel Grid-Option ausgewählt haben die [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md), klicken Sie dann Ändern der Größe von Snapshots an der nächsten Kachel. Wenn nur die Pixelraster Option ist (Standardeinstellung), ausgewählt Ändern der Größe von Snapshots und dem nächsten verfügbaren Pixel.  
  
-   [Größenänderung eines ganzen Bilds](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Abschneiden oder Erweitern eines ganzen Bildes](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Verkleinern oder Strecken eines ganzen Bildes](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Verkleinern oder Strecken eines Teiles eines Bildes](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)