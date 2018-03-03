---
title: "Ändern der Größe eines Bilds (Bildbearbeitung für Symbole) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f856c5cf825fd9032ce64afbd09d3bed83ea40f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Größenänderungen bei Bildern (Bildbearbeitung für Symbole)
Das Verhalten der Bild-Editor beim Ändern der Bildgröße, hängt davon ab, ob Sie wurde [ausgewählten](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) das gesamte Bild oder einen Teil davon.  
  
 Wenn die Auswahl nur einen Teil des Abbilds enthält, die Grafik-Editor verkleinert die Auswahl durch das Löschen von Zeilen oder Spalten von Pixeln und füllen die frei werdenden Regionen mit der aktuellen Hintergrundfarbe, oder es gestreckt wird die Auswahl durch Duplizieren, Zeilen oder Spalten von Pixeln.  
  
 Wenn die Auswahl auf das gesamte Bild enthält, die Grafik-Editor entweder verkleinert und das Bild wird gestreckt oder abgeschnitten und erweitert sie.  
  
 Es gibt zwei Mechanismen zum Ändern der Bildgröße: Ziehpunkte und [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Sie können die Ziehpunkte zum Ändern der Größe des gesamten oder einen Teil eines Images ziehen. Ziehpunkte, die Sie ziehen können, sind gefüllt. Sie können keine Handles ziehen, die leer sind. Sie können im Eigenschaftenfenster ändern Sie das gesamte Bild nur nicht auf einen ausgewählten Teil.  
  
 ![Ziehpunkte in einer Bitmap](../mfc/media/vcimageeditorsizinghandles.gif "VcImageEditorSizingHandles")  
Ziehpunkte  
  
> [!NOTE]
>  Die Kachel Raster-Option ausgewählt haben die [Rastereinstellungen (Dialogfeld)](../windows/grid-settings-dialog-box-image-editor-for-icons.md), dann Größenänderung wird an die nächste Kachel Rasterlinie ausgerichtet. Wenn nur die Pixelraster Option ist (Standardeinstellung) ausgewählt Ändern der Größe von Momentaufnahmen zum nächsten verfügbaren Pixel.  
  
-   [Größenänderung eines ganzen Bildes](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Abschneiden oder Erweitern eines ganzen Bildes](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Verkleinern oder Strecken eines ganzen Bildes](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Verkleinern oder Strecken eines Teiles eines Bildes](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

