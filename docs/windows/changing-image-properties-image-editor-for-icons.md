---
title: Ändern von Bildeigenschaften (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [C++], properties
- Image editor [C++], Properties window
- Properties window, image editor
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 286e71b427bd39df6c493c7727b66ef27b72c766
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314338"
---
# <a name="changing-image-properties-image-editor-for-icons"></a>Ändern von Bildeigenschaften (Bildbearbeitung für Symbole)

Sie können festlegen, oder Ändern der Eigenschaften eines Image mithilfe der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

### <a name="to-change-an-images-properties"></a>So ändern Sie die Bildeigenschaften

1. Öffnen Sie das Abbild in der **Image** Editor.

2. In der **Eigenschaften** Fenster ANY- oder all-Eigenschaften für das Image zu ändern.

   |Eigenschaft|Beschreibung|
   |--------------|-----------------|
   |**Farben**|Gibt an, das Farbschema für das Image. Wählen Sie **Monochrom**, **16**, oder **256**, oder **True Color**. Wenn Sie bereits das Image mit einem 16-Farben-Palette gezeichnet haben, durch die Auswahl **Monochrom** bewirkt, dass Ersetzungen von Schwarz und weiß, für die Farben in der Abbildung. Kontrast wird nicht immer beibehalten: z. B. benachbarte Bereiche Rot-Grün sind in Schwarz umgewandelt.|
   |**Filename**|Gibt den Namen der Bilddatei. Standardmäßig weist Visual Studio ein Basisdateiname, entfernen die ersten vier Zeichen ("IDB_") erstellt, aus der Standard-Ressourcen-ID (IDB_BITMAP1) und die entsprechende Erweiterung hinzugefügt. Der Name der Datei für das Bild in diesem Beispiel `BITMAP1.bmp`. Könnten Sie den Namen es `MYBITMAP1.bmp`.|
   |**Höhe**|Legt die Höhe des Bilds (in Pixel) fest. Der Standardwert ist 48. Das Bild ist beschnitten, oder ein leerer Bereich unterhalb des Bildes hinzugefügt.|
   |**ID**|Legt den Ressourcenbezeichner fest. Um ein Bild, Microsoft Visual Studio, in der Standardeinstellung weist den nächsten verfügbaren Bezeichner in einer Reihe: IDB_BITMAP1, IDB_BITMAP2 und so weiter. Ähnliche Namen werden für Symbole und Cursor verwendet.|
   |**Palette**|Ändert die Farbeigenschaften. Doppelklicken Sie auf eine Farbe auswählen und Anzeigen der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Definieren Sie die Farbe, indem Sie RGB- oder HSL-Werte in die entsprechenden Textfelder eingeben.|
   |**SaveCompressed**|Gibt an, ob das Bild in einem komprimierten Format ist. Diese Eigenschaft ist schreibgeschützt. Visual Studio erlaubt Ihnen das Speichern von Bildern in einem komprimierten Format, jedoch nicht damit für alle Bilder, die in Visual Studio erstellt wird, diese Eigenschaft wird **"false"**. Wenn Sie ein komprimiertes Bild (erstellt in einem anderen Programm) in Visual Studio öffnen, wird diese Eigenschaft **"true"**. Wenn Sie ein komprimiertes Bild mithilfe von Visual Studio speichern, werden nicht komprimiert, und diese Eigenschaft wird auf zurückgesetzt **"false"**.|
   |**Breite**|Legt die Breite des Bilds (in Pixel) fest. Der Standardwert für Bitmaps gleich 48. Das Bild ist beschnitten, oder ein leerer Bereich rechts neben das bestehende Image hinzugefügt.|

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)  
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)