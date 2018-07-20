---
title: 'Symbole und Cursor: Bildressourcen für Anzeigegeräte (Bildbearbeitung für Symbole) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- image resources, display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices, creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a977629cbae140afa1463a7765f193a7519e1f68
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881909"
---
# <a name="icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons"></a>Symbole und Cursor: Bildressourcen für Anzeigegeräte (Bildbearbeitung für Symbole)
Symbole und Cursor sind grafische Ressourcen, die mehrere Bilder in verschiedenen Größen und Farbschemas für verschiedene Arten von Anzeigegeräten enthalten können. Außerdem weist ein Cursor einen „Hotspot“ auf, den Ort, den Windows zum Nachverfolgen seiner Position verwendet. Sowohl Symbole als auch Cursor werden mit dem Bild-Editor bearbeitet, wie Bitmaps und andere Bilder auch.  
  
 Wenn Sie ein neues Symbol oder einen neuen Cursor erstellen, erstellt der Bild-Editor zunächst ein Bild eines Standardtyps. Das Bild ist anfänglich mit der Bildschirmfarbe (transparent) gefüllt. Wenn es sich bei dem Bild um einen Cursor handelt, befindet sich der Hotspot anfangs in der oberen linken Ecke (Koordinaten 0,0).  
  
 Standardmäßig unterstützt der Bild-Editor die Erstellung weiterer Bilder für die in der folgenden Tabelle aufgelisteten Geräte. Sie können Bilder für andere Geräte erstellen, indem Sie im Dialogfeld [Benutzerdefiniertes Bild](custom-image-dialog-box-image-editor-for-icons.md)die Parameter für Breite, Höhe und Anzahl der Farben eingeben.  
  
> [!NOTE]
>  Mit der Bildbearbeitung können Sie 32-Bit-Bilder anzeigen, sie aber nicht bearbeiten.  
  
|Farbe|Breite (in Pixel)|Höhe (in Pixel)|  
|-----------|----------------------|-----------------------|  
|Monochrom|16|16|  
|Monochrom|32|32|  
|Monochrom|48|48|  
|Monochrom|64|64|  
|Monochrom|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [Erstellen eines neuen Bilds für ein Gerät (Symbol oder Cursor)](../windows/creating-a-device-image-image-editor-for-icons.md)  
  
-   [Hinzufügen eines Bildes für ein anderes Anzeigegerät](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [Kopieren eines Gerätebildes](../windows/copying-a-device-image-image-editor-for-icons.md)  
  
-   [Löschen eines Gerätebildes](../windows/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [Erstellen transparenter oder invertierter Bereiche in Gerätebildern](../windows/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [Erstellen eines Symbols oder Cursors mit 256 Farben](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [Festlegen des Hotspots eines Cursors](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)   
 [Symbole](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [Cursor](http://msdn.microsoft.com/library/windows/desktop/ms646970)

