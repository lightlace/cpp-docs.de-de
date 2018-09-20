---
title: Speichern und Laden von verschiedenen Farbpaletten (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50e74c65e080b11583e6ff1e591ef612b17e9533
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438885"
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Speichern und Laden von verschiedenen Farbpaletten (Bildbearbeitung für Symbole)

Sie können das Speichern und Laden eine **Farben** Palette mit [Farben angepasst](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (Standardmäßig die **Farben** zuletzt verwendete Farbpalette wird automatisch geladen, wenn Sie Visual Studio starten.)

> [!TIP]
> Da die **Image** -Editor verfügt über keine Möglichkeit zum Wiederherstellen der standardmäßigen **Farben** Palette, speichern Sie die Standardeinstellung **Farben** unter einem Namen wie z. B.  *Standard.PAL* oder *default.pal* , damit Sie die Standardeinstellungen problemlos wiederherstellen können.

### <a name="to-save-a-custom-colors-palette"></a>So speichern Sie eine benutzerdefinierte Farbpalette

1. Von der **Image** Menü wählen **Palette speichern**.

2. Navigieren Sie zu dem Verzeichnis, in dem Sie die Farbpalette speichern möchten, und geben Sie einen Namen für die Palette ein.

3. Klicken Sie auf **Speichern**.

### <a name="to-load-a-custom-colors-palette"></a>So laden Sie eine benutzerdefinierte Farbpalette

1. Von der **Image** Menü wählen **Palette laden**.

2. In der [Palettenfarben laden (Dialogfeld)](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), navigieren Sie zum richtigen Verzeichnis, und wählen Sie die Palette, die Sie laden möchten. **Farbe** Paletten werden mit der Erweiterung. PAL gespeichert.

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)