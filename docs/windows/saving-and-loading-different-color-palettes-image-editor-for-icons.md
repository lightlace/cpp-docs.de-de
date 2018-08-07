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
ms.openlocfilehash: 14cad19c53e8cd741bf16bab49420169e93f6af6
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606971"
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Speichern und Laden von verschiedenen Farbpaletten (Bildbearbeitung für Symbole)
Sie können das Speichern und Laden Sie eine Farbpalette mit [Farben angepasst](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (Standardmäßig wird die zuletzt verwendete Farbpalette beim Start von Visual Studio automatisch geladen.)  
  
> [!TIP]
>  Da die Bildbearbeitung nicht die standardmäßige Farbpalette wiederherstellen kann, sollten Sie diese unter einem Namen, wie z. B. standard.pal oder default.pal speichern, damit Sie die Standardeinstellungen problemlos wiederherstellen können.  
  
### <a name="to-save-a-custom-colors-palette"></a>So speichern Sie eine benutzerdefinierte Farbpalette  
  
1.  Von der **Image** Menü wählen **Palette speichern**.  
  
2.  Navigieren Sie zu dem Verzeichnis, in dem Sie die Farbpalette speichern möchten, und geben Sie einen Namen für die Palette ein.  
  
3.  Klicken Sie auf **Speichern**.  
  
### <a name="to-load-a-custom-colors-palette"></a>So laden Sie eine benutzerdefinierte Farbpalette  
  
1.  Von der **Image** Menü wählen **Palette laden**.  
  
2.  In der [Palettenfarben laden (Dialogfeld)](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), navigieren Sie zum richtigen Verzeichnis, und wählen Sie die Palette, die Sie laden möchten. Farbpaletten werden mit der Dateierweiterung „.pal“ gespeichert.  
  
## <a name="requirements"></a>Anforderungen  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)