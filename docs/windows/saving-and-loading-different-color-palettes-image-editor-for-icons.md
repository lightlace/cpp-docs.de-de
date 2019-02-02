---
title: Speichern und Laden von verschiedenen Farbpaletten (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.color
- vc.editors.loadcolorpalette
helpviewer_keywords:
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
- color palettes
- Load Palette Colors dialog box [C++]
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
ms.openlocfilehash: fd2664407d33d8e3ed594921501b7f80e6c8850b
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560269"
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Speichern und Laden von verschiedenen Farbpaletten (Bildbearbeitung für Symbole)

Sie können das Speichern und Laden eine **Farben** Palette mit [Farben angepasst](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (Standardmäßig die **Farben** zuletzt verwendete Farbpalette wird automatisch geladen, wenn Sie Visual Studio starten.)

> [!TIP]
> Da die **Image** -Editor verfügt über keine Möglichkeit zum Wiederherstellen der standardmäßigen **Farben** Palette, speichern Sie die Standardeinstellung **Farben** unter einem Namen wie z. B.  *Standard.PAL* oder *default.pal* , damit Sie die Standardeinstellungen problemlos wiederherstellen können.

Verwenden Sie die **Palettenfarben laden** Dialogfeld spezielle Farbpaletten, die für die Verwendung in Ihrem C++-Projekt zu laden. Die folgenden Eigenschaften enthalten sind:

|Eigenschaft|Beschreibung|
|---|---|
|**Suchen in**|Gibt den Speicherort einer Datei oder eines Ordners gefunden werden sollen. Wählen Sie den Pfeil, um einen anderen Speicherort auswählen, oder wählen Sie das Ordnersymbol auf der Symbolleiste können Sie Ebenen zu verschieben.|
|**Dateiname**|Dient zur Eingabe der Name der Datei, die Sie öffnen möchten. Um schnell eine Datei zu suchen, die Sie zuvor erstellt haben, wählen Sie den Dateinamen in der Dropdown-Liste, sofern verfügbar.<br/><br/>Wenn Sie für eine Datei durchsuchen, können Sie Sternchen (*) als Platzhalter verwenden. Sie können z. B. eingeben \*.\* um eine Liste aller Dateien anzuzeigen. Sie können auch den vollständigen Pfad einer Datei, z. B. C:\My Documents\MyColorPalette.pal eingeben oder \\\NetworkServer\MyFolder\MyColorPalette.pal.|
|**Dateityp**|Listet die Typen der anzuzeigenden Dateien. Palette (*. PAL) ist der Standardtyp für die Datei für Farbpaletten.|

## <a name="to-save-a-custom-colors-palette"></a>So speichern Sie eine benutzerdefinierte Farbpalette

1. Von der **Image** Menü wählen **Palette speichern**.

1. Navigieren Sie zu dem Verzeichnis, in dem Sie die Farbpalette speichern möchten, und geben Sie einen Namen für die Palette ein.

1. Klicken Sie auf **Speichern**.

## <a name="to-load-a-custom-colors-palette"></a>So laden Sie eine benutzerdefinierte Farbpalette

1. Von der **Image** Menü wählen **Palette laden**.

1. In der **Palettenfarben laden** Dialogfeld Feld, navigieren Sie zum richtigen Verzeichnis aus, und wählen Sie die Palette, die Sie laden möchten. **Farbe** Paletten werden mit der Erweiterung. PAL gespeichert.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)