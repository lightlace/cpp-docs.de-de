---
title: Erstellen eines Gerätebilds (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.icon
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
ms.openlocfilehash: 322205e22edf2624784ddb8f294bcf5e73af06f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447754"
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>Erstellen eines Gerätebilds (Bildbearbeitung für Symbole)

Bei der Erstellung ein neues Symbol oder Cursor-Ressource, die **Image** Editor erstellt zunächst ein Image eines bestimmten Formats (32 × 32, 16 Farben für Symbole und 32 × 32, Monochrom für Cursor). Sie können dann Hinzufügen von Bildern in verschiedenen Größen und Formate zu dem ersten Symbol oder Cursor und jedes zusätzliche Image Bedarf bearbeiten, für die verschiedenen Anzeigegeräten. Sie können ein Bild auch bearbeiten, indem eine Ausschneiden und Einfügen-Operation aus einem vorhandenen Imagetyp oder aus einer Bitmap in einem Grafikprogramm erstellte.

Beim Öffnen der Ressource Symbol oder Cursor in die [bildbearbeitung](../windows/image-editor-for-icons.md), das Bild, das das aktuelle Anzeigegerät am ehesten entspricht, wird standardmäßig geöffnet.

### <a name="to-create-a-new-icon-or-cursor"></a>Erstellen Sie ein neues Symbol oder cursor

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können einfach mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und klicken Sie auf **neu**. Für Symbole erstellt dies eine Symbolressource mit 32 × 32 Pixel, 16 Farben. Bei Cursorn 32 × 32 Pixel, wird die Monochrome (2 Farben)-Abbild erstellt.

   Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp in der **Ressource einfügen** Dialogfeld es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Klicken Sie auf das Pluszeichen, um der Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und auf **neu**.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)