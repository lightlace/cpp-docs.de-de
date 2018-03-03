---
title: "Arbeiten mit Farben (Bildbearbeitung für Symbole) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ad0c7df6804667c3bd243668193283ecee61c8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-color-image-editor-for-icons"></a>Arbeiten mit Farben (Bildbearbeitung für Symbole)
Grafik-Editor enthält viele Funktionen, die speziell behandelt und Anpassen von Farben an. Sie können eine Vorder- oder Hintergrund Farbe festlegen, füllen von begrenzten Bereichen mit Farbe oder wählen Sie eine Farbe auf ein Bild, als die aktuelle Vorder- oder Hintergrund Farbe verwendet werden. Können Sie Tools auf die [Grafik-Editor-Symbolleiste](../windows/toolbar-image-editor-for-icons.md) zusammen mit Farben (Palette) in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md) um Images zu erstellen.  
  
 Alle Farben für Monochrom und 16 Farben Bilder werden in den Farben (Palette) im Fenster "Farben" angezeigt. Zusätzlich zu den 16 Standardfarben können Sie eigene benutzerdefinierten Farben erstellen. Ändern der Farben in der Palette ändert sich sofort auf die entsprechende Farbe in der Abbildung aus.  
  
 Beim Arbeiten mit 256 Farben Symbol-als auch Cursor images, der Eigenschaft "Farben" in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) verwendet wird. Weitere Informationen finden Sie unter [Erstellen eines 256-Farben-Symbols oder Cursors](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).  
  
> [!NOTE]
>  Mit der Bildbearbeitung können Sie 32-Bit-Bilder anzeigen, sie aber nicht bearbeiten.  
  
 "True" Farbe Bilder können auch erstellt werden. "True" Farbmuster werden jedoch nicht in der vollständige Palette in das Fenster "Farben" angezeigt. Sie werden nur im Bereich Anzeige Vorder- oder Hintergrund Farbe angezeigt. "True" Farben werden erstellt, mit der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Weitere Informationen finden Sie unter [anpassen oder Ändern von Farben](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 Sie können benutzerdefinierte Farbpaletten auf dem Datenträger zu speichern und Bedarf neu geladen werden. Die zuletzt verwendete Farbpalette ist in der Registrierung gespeichert und das nächste Mal starten von Visual Studio automatisch geladen.  
  
-   [Auswählen von Vordergrund- oder Hintergrundfarben](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [Füllen von begrenzten Bereichen eines Bildes mit einer Farbe](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [Übertragen einer Farbe eines Bildes auf andere Elemente](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [Auswählen eines transparenten oder deckenden Hintergrundes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [Invertieren der Farben in einer Markierung](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [Anpassen oder Ändern von Farben](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [Speichern und Laden von verschiedenen Farbpaletten](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   

