---
title: Erstellen eines Gerätebilds (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.icon
- vc.editors.newimagetype
- vc.editors.customimage
- vc.editors.opendeviceimage
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
- New <Device> Image Type dialog box [C++]
- Custom Image dialog box [C++]
- Open <Device> Image dialog box [C++]
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
ms.openlocfilehash: ce1069f6f410d7a60d631461086ca8870ef679c0
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560295"
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>Erstellen eines Gerätebilds (Bildbearbeitung für Symbole)

Bei der Erstellung ein neues Symbol oder Cursor-Ressource, die **Image** Editor erstellt zunächst ein Image eines bestimmten Formats (32 × 32, 16 Farben für Symbole und 32 × 32, Monochrom für Cursor). Sie können dann Hinzufügen von Bildern in verschiedenen Größen und Formate zu dem ersten Symbol oder Cursor und jedes zusätzliche Image Bedarf bearbeiten, für die verschiedenen Anzeigegeräten. Sie können auch ein Bild mit einem Ausschneiden und Einfügen-Vorgang aus einem vorhandenen Imagetyp oder aus einer Bitmap in einem Grafikprogramm erstellte bearbeiten.

Beim Öffnen der Ressource Symbol oder Cursor in die [bildbearbeitung](../windows/image-editor-for-icons.md), das Bild, das das aktuelle Anzeigegerät am ehesten entspricht, wird standardmäßig geöffnet.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="new-ltdevicegt-image-type-dialog-box"></a>Neue &lt;Gerät&gt; Bildtyp (Dialogfeld)

Die **neu &lt;Gerät&gt; Bildtyp** Dialogfeld können Sie ein neues Gerätebild eines angegebenen Typs erstellt. Zum Öffnen der **neu \<Gerät > Image** wählen Sie im Dialogfeld **Neuer Bildtyp** auf die **Image** im Menü. Die folgenden Eigenschaften enthalten sind **Image Zieltyp** und **benutzerdefinierte**.

### <a name="target-image-type"></a>Ziel-Bildtyp

Listet die verfügbaren Images. Wählen Sie den Image-Typ, die, den Sie öffnen möchten:

||||
|-|-|-|
|– 16 x 16, 16 Farben|-48 x 48, 16 Farben|-96 x 96, 16 Farben|
|– 16 x 16, 256 Farben|-48 x 48, 256 Farben|-96 x 96, 256 Farben|
|- 16 x 16, Monochrome|-48 x 48, Monochrom|-96 x 96, Monochrom|
|-32 x 32, 16 Farben|-64 x 64-16 Farben||
|-32 x 32, 256 Farben|-64 x 64, 256 Farben||
|-32 x 32, Monochrom|-64 x 64, Monochrom||

> [!NOTE]
> Alle vorhandenen Bilder werden in dieser Liste nicht angezeigt werden.

### <a name="custom"></a>Benutzerdefiniert

Öffnet die **benutzerdefiniertes Image** Dialogfeld, in dem Sie ein neues Image mit einer benutzerdefinierten Größe und Anzahl der Farben erstellen können.

Die **benutzerdefiniertes Image** Dialogfeld können Sie ein neues Image mit einer benutzerdefinierten Größe und Anzahl der Farben zu erstellen. Die folgenden Eigenschaften enthalten sind:

|Eigenschaft|Beschreibung|
|---|---|
|**Width**|Dient zur Eingabe der Breite des benutzerdefinierten Images in Pixel (1-512, Max. 2048).|
|**Height**|Dient zur Eingabe der Höhe für das benutzerdefinierte Image in Pixel (1-512, Max. 2048).|
|**Farben**|Ein Eingabefeld für die Anzahl der Farben für das benutzerdefinierte Image auswählen: 2, 16 und 256.|

## <a name="open-ltdevicegt-image-dialog-box"></a>Open &lt;Gerät&gt; Bild (Dialogfeld)

Verwenden der **öffnen &lt;Gerät&gt; Image** Dialogfeld zum Öffnen von Gerätebildern in C++-Projekten. Vorhandene Images mit der Geräte in der aktuellen Ressourcendatei (Bilder, die Teil der aktuellen Ressource) aufgeführt. Die folgende Eigenschaft enthalten ist:

|Eigenschaft|Beschreibung|
|---|---|
|**Aktuellen Images**|Listet die Images, die in der Ressource enthalten. Wählen Sie den Image-Typ, die, den Sie öffnen möchten.|

## <a name="to-create-a-new-icon-or-cursor"></a>Erstellen Sie ein neues Symbol oder cursor

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und wählen Sie **neu**. Für Symbole erstellt diese Aktion eine Symbolressource mit 32 × 32 Pixel, 16 Farben. Bei Cursorn 32 × 32 Pixel, wird die Monochrome (2 Farben)-Abbild erstellt.

   Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp in der **Ressource einfügen** Dialogfeld es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Wählen Sie das Pluszeichen, um die Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und wählen **neu**.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)<br/>
[Menü "Bild"](../windows/image-menu-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)<br/>
