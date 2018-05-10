---
title: Konvertieren von Bitmaps in Symbolleisten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor, converting bitmaps
- toolbars [C++], converting bitmaps
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e80bee7ef9bfe52abf63ac959475c5d8dbcf0ece
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="converting-bitmaps-to-toolbars"></a>Konvertieren von Bitmaps in Symbolleisten
Sie können eine neue Symbolleiste erstellen, durch die Konvertierung einer Bitmap. Die Grafik aus der Bitmap, die in der Schaltflächenbilder für eine Symbolleiste konvertiert werden. Die Bitmap wird in der Regel mehrere Bilder in einer einzigen Bitmap mit einem Bild für jede Schaltfläche enthält. Bilder können eine beliebige Größe sein; Der Standardwert ist 16 Pixel breit und die Höhe des Bilds. Können Sie angeben, die Größe der Schaltflächenbilder in der [neue Symbolleistenressource (Dialogfeld)](../windows/new-toolbar-resource-dialog-box.md) bei Auswahl von Symbolleisten-Editor aus der **Image** in der Grafik-Editor im Menü.  
  
### <a name="to-convert-bitmaps-to-a-toolbar"></a>Konvertieren von Bitmaps in einer Symbolleiste  
  
1.  Öffnen Sie eine vorhandene Bitmapressource in der [bildbearbeitung](../windows/image-editor-for-icons.md). (Wenn die Bitmap in der RC-Datei noch nicht vorhanden ist, mit der rechten Maustaste in der RC-Datei, wählen Sie **Import** aus dem Kontextmenü aus, navigieren Sie zu der Bitmap, die Sie auf die RC-Datei hinzufügen möchten, und klicken Sie auf **öffnen**.)  
  
2.  Aus der **Image** Menü wählen **Symbolleisten-Editor**.  
  
     Die [neue Symbolleistenressource (Dialogfeld)](../windows/new-toolbar-resource-dialog-box.md) angezeigt wird. Sie können die Breite und Höhe der Symbolbilder Bitmap entsprechend ändern. Das Symbolleistenbild wird in der Symbolleisten-Editor angezeigt.  
  
3.  Um die Konvertierung zu beenden, ändern Sie den Befehl **ID** der Schaltfläche mit den [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Geben Sie den neuen **ID** , oder wählen Sie eine **ID** aus der Dropdown-Liste.  
  
    > [!TIP]
    >  Das Eigenschaftenfenster enthält eine PIN-Schaltfläche in der Titelleiste. Klicken auf diese Schaltfläche aktiviert oder deaktiviert automatisch im Hintergrund, für das Fenster. Um schnell alle Eigenschaften der Symbolleisten-Schaltfläche zu durchlaufen, ohne einzelne Eigenschaft erneut öffnen, deaktivieren Sie automatisch im Hintergrund, sodass das Eigenschaftenfenster geöffnet bleibt.  
  
 Sie können auch die Befehls-IDs der Schaltflächen auf der neuen Symbolleiste ändern, mit der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Informationen zum Bearbeiten der neue Symbolleiste finden Sie unter [erstellen, verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../windows/creating-moving-and-editing-toolbar-buttons.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 MFC oder ATL  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen neuer Symbolleisten](../windows/creating-new-toolbars.md)   
 [Symbolleisten-Editor](../windows/toolbar-editor.md)

