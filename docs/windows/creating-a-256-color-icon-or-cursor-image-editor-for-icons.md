---
title: Erstellen eines Symbols oder Cursors mit 256 Farben (Bildbearbeitung für Symbole)
ms.date: 11/04/2016
helpviewer_keywords:
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
ms.openlocfilehash: cd1100c05b41017fc89ccf58854cb8ed219a7873
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642755"
---
# <a name="creating-a-256-color-icon-or-cursor-image-editor-for-icons"></a>Erstellen eines Symbols oder Cursors mit 256 Farben (Bildbearbeitung für Symbole)

Mithilfe der **Image** -Editor, Symbolen und Cursorn können mit einem 256-Farben-Palette zur Auswahl groß (64 × 64) angepasst werden. Nach dem Erstellen der Ressource wird ein Stil für das Gerät ausgewählt.

### <a name="to-create-a-256-color-icon-or-cursor"></a>Erstellen eines 256-Farben-Symbols oder Cursors

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können einfach mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und klicken Sie auf **neu**.

3. Auf der **Image** Menü klicken Sie auf **neues Gerätebild**.

4. Wählen Sie die gewünschte Formatvorlage für das Bild mit 256 Farben.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Verwenden der 256-Farben-Palette](../windows/using-the-256-color-palette-image-editor-for-icons.md)<br/>
[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)