---
title: Verwenden der 256-Farben-Palette (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
helpviewer_keywords:
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
- colors [C++], icons and cursors
- color palettes, 256-color
- palettes, 256-color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
ms.openlocfilehash: 4e2f2c9ce58799756137bb47db42e52c97a43d39
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702894"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>Verwenden der 256-Farben-Palette (Bildbearbeitung für Symbole)

Mithilfe der **Image** -Editor, Symbolen und Cursorn können mit einem 256-Farben-Palette zur Auswahl groß (64 × 64) angepasst werden. Nach dem Erstellen der Ressource wird ein Stil für das Gerät ausgewählt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-create-a-256-color-icon-or-cursor"></a>Erstellen eines 256-Farben-Symbols oder Cursors

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und wählen Sie **neu**.

1. Auf der **Image** , wählen Sie im Menü **neues Gerätebild**.

1. Wählen Sie die gewünschte Formatvorlage für das Bild mit 256 Farben.

## <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Wählen Sie eine Farbe aus der 256-Farben-Palette für große Symbole

Um mit einer Auswahl aus der 256-Farben-Palette zu zeichnen, müssen Sie die Farben auswählen der **Farben** Palette in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md).

1. Wählen Sie die große Symbole oder Cursor, oder erstellen Sie eine neue große Symbole oder Cursor.

1. Wählen Sie eine Farbe aus der 256 Farben der **Farben** Palette in der **Farben** Fenster.

   Die ausgewählte Farbe wird die aktuelle Farbe in der **Farben** Palette in der **Farben** Fenster.

   > [!NOTE]
   > Die anfängliche Palette verwendet für 256-Farben-Images entspricht die Palette von zurückgegebenen der `CreateHalftonePalette` Windows-API. Alle Symbole, die für die Windows-Shell vorgesehen, sollten diese Palette verwenden, um Flimmern während der Realisierung der Palette zu vermeiden.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)
