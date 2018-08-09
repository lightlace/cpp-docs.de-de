---
title: Arbeiten mit Farben (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
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
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors, Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37e469b18af727bea29681b284fd123bcce64c93
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647419"
---
# <a name="working-with-color-image-editor-for-icons"></a>Arbeiten mit Farben (Bildbearbeitung für Symbole)
Die **Bildbearbeitung** enthält viele Features, die speziell behandelt und Anpassen von Farben. Sie können eine Vorder- oder Hintergrund Farbe festlegen, füllen von begrenzten Bereichen mit Farbe oder eine andere Farbe auf ein Bild, als die aktuelle Vorder- oder Hintergrund Farbe auswählen. Sie können auf Tools verwenden die [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) zusammen mit den Farben (Palette) in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md) Images erstellen.  
  
 Alle Farben für Monochrom und 16 Farben-Images werden angezeigt, der **Farben** Palette in der **Farben** Fenster. Zusätzlich zu den 16 Standardfarben können Sie eigene benutzerdefinierten Farben erstellen. Ändern der Farben in der Palette ändert sich sofort auf die entsprechende Farbe im Bild aus.  
  
 Beim Arbeiten mit 256-Farben-Symbol und der Cursor-Images, die **Farben** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) verwendet wird. Weitere Informationen finden Sie unter [Erstellen eines 256-Farben-Symbols oder Cursors](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).  
  
> [!NOTE]
>  Mithilfe der **Bildbearbeitung**, können Sie die 32-Bit-Images anzeigen, aber nicht bearbeiten.  
  
 True Color-Bilder können auch erstellt werden. "True" farbbeispiele werden jedoch nicht angezeigt, in der vollständigen Palette in der **Farben** Fenster; sie nur in den Vorder- oder Hintergrund Indikator Farbbereich angezeigt werden. "True" Farben werden erstellt, mit der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Weitere Informationen finden Sie unter [anpassen oder Ändern von Farben](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 Sie können benutzerdefinierte Farbpaletten auf Datenträger speichern und erneut geladen werden, je nach Bedarf. Die zuletzt verwendeten Farben-Palette ist in der Registrierung gespeichert und beim nächsten start von Visual Studio automatisch geladen.  
  
-   [Auswählen von Vordergrund- oder Hintergrundfarben](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [Füllen von begrenzten Bereichen eines Bilds mit einer Farbe](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [Übertragen einer Farbe eines Bildes auf andere Elemente](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [Auswählen eines transparenten oder deckenden Hintergrunds](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [Invertieren der Farben in einer Auswahl](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [Anpassen oder Ändern von Farben](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [Speichern und Laden von verschiedenen Farbpaletten](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   