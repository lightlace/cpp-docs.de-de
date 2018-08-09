---
title: Verwenden der 256-Farben-Palette (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- colors, icons and cursors
- cursors, color
- color palettes, 256-color
- palettes, 256-color
- icons, color
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be817ac4bddcc169ab2ecb3a9106e9594642e2f0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645151"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>Verwenden der 256-Farben-Palette (Bildbearbeitung für Symbole)
Um mit einer Auswahl aus der 256-Farben-Palette zu zeichnen, müssen Sie die Farben aus der Farbpalette auswählen der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md).  
  
### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Wählen Sie eine Farbe aus der 256-Farben-Palette für große Symbole  
  
1.  Wählen Sie die große Symbole oder Cursor, oder erstellen Sie eine neue große Symbole oder Cursor.  
  
2.  Wählen Sie eine Farbe aus der 256 Farben der **Farben** Palette in der **Farben** Fenster.  
  
     Die ausgewählte Farbe wird die aktuelle Farbe in der Farbpalette der **Farben** Fenster.  
  
    > [!NOTE]
    >  Die anfängliche Palette verwendet für 256-Farben-Images entspricht die Palette von zurückgegebenen der `CreateHalftonePalette` Windows-API. Alle Symbole, die für die Windows-Shell vorgesehen, sollten diese Palette verwenden, um Flimmern während der Realisierung der Palette zu vermeiden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Erstellen eines 256-Farben-Symbols oder Cursors](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)   
 [Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)