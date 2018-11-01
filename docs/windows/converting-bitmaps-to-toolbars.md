---
title: Konvertieren von Bitmaps in Symbolleisten (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor [C++], converting bitmaps
- toolbars [C++], converting bitmaps
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
ms.openlocfilehash: 1b40d43ef756151a743bbee32cd74a3ee100194e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563604"
---
# <a name="converting-bitmaps-to-toolbars-c"></a>Konvertieren von Bitmaps in Symbolleisten (C++)

Sie können eine neue Symbolleiste in einem C++-Projekt erstellen, durch die Konvertierung einer Bitmaps. Die Grafik aus dem Bitmap, die in der Schaltflächenbilder für eine Symbolleiste konvertiert werden. Die Bitmap wird in der Regel mehrere Images von Schaltfläche auf einer einzelnen Bitmap mit einem einzelnen Abbild für jede Schaltfläche enthält. Bilder können eine beliebige Größe aufweisen; Der Standardwert ist 16 Pixel breit und die Höhe des Bilds. Sie können angeben, die Größe der Schaltflächenbilder in der [neue Symbolleistenressource (Dialogfeld)](../windows/new-toolbar-resource-dialog-box.md) bei der Auswahl **Symbolleisten-Editor** aus der **Image** in der Grafik-Editor im Menü.

### <a name="to-convert-bitmaps-to-a-toolbar"></a>Konvertieren von Bitmaps zu einer Symbolleiste

1. Öffnen Sie eine vorhandene Bitmapressource in der [bildbearbeitung](../windows/image-editor-for-icons.md). (Wenn die Bitmap in der RC-Datei noch nicht vorhanden ist, mit der rechten Maustaste in der RC-Datei, wählen Sie **Import** aus dem Kontextmenü aus, navigieren Sie zu der Bitmap, die Sie auf die RC-Datei hinzufügen möchten, und klicken Sie dann **öffnen**.)

2. Von der **Image** Menü wählen **Symbolleisten-Editor**.

   Die [neue Symbolleistenressource (Dialogfeld)](../windows/new-toolbar-resource-dialog-box.md) angezeigt wird. Sie können die Breite und Höhe der Symbolbilder entsprechend die Bitmap ändern. Das Symbolleistenbild wird in der Symbolleisten-Editor angezeigt.

3. Ändern Sie den Befehl, um die Konvertierung abzuschließen, **ID** der Schaltfläche mit den [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Geben Sie den neuen **ID** oder wählen Sie eine **ID** aus der Dropdown-Liste.

   > [!TIP]
   > Die **Eigenschaften** Fenster enthält eine Stecknadel-Schaltfläche in der Titelleiste angezeigt. Klicken auf diese Schaltfläche aktiviert oder deaktiviert die **automatisch im Hintergrund** für das Fenster. Um schnell alle Eigenschaften der Symbolleisten-Schaltfläche zu durchlaufen, ohne dass die einzelne Eigenschaft erneut öffnen, aktivieren Sie **automatisch im Hintergrund** deaktiviert daher **Eigenschaften** Fenster stationär bleibt.

Sie können auch die Befehls-IDs der Schaltflächen auf die neue Symbolleiste ändern, mit der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Informationen zum Bearbeiten der neuen Symbolleiste finden Sie unter [erstellen, verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../windows/creating-moving-and-editing-toolbar-buttons.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Erstellen neuer Symbolleisten](../windows/creating-new-toolbars.md)<br/>
[Symbolleisten-Editor](../windows/toolbar-editor.md)