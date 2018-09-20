---
title: Speichern von Bitmaps als GIFs oder JPEGs (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- .gif files [C++], saving bitmaps as
- jpg files [C++], saving bitmaps as
- jpeg files [C++], saving bitmaps as
- .jpg files [C++], saving bitmaps as
- Image editor [C++], converting image formats
- gif files [C++], saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files [C++], saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11eea641132a608bf780f9adcc7cfeafad0950d5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383134"
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>Speichern von Bitmaps als GIFs oder JPEGs (Bildbearbeitung für Symbole)

Wenn Sie eine Bitmap zu erstellen, wird das Bild im Bitmapformat (BMP) erstellt. Sie können jedoch das Image als GIF- oder JPEG oder in anderen Grafikformaten speichern.

> [!NOTE]
> Dieser Prozess gilt nicht für Symbole und Cursor.

### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Zum Erstellen und speichern eine Bitmap als GIF- oder JPEG

1. Von der **Datei** Menü wählen **öffnen**, klicken Sie dann auf **Datei**.

2. In der **neuen Dateidialogfeld**, klicken Sie auf die **Visual C++** Ordner, wählen Sie dann **Bitmapdatei (BMP)** in die **Vorlagen** ein, und klicken Sie auf  **Open**.

   Die Bitmap wird im der **Image** Editor.

3. Nehmen Sie Änderungen an der neuen Bitmap, je nach Bedarf.

4. Mit der Bitmap, die noch geöffnet, in der **Image** -Editor, klicken Sie auf **speichern *Dateiname*BMP als** auf die **Datei** Menü.

5. In der **Datei speichern unter** Dialogfeld Geben Sie den Namen, erhalten die Datei und die Erweiterung, die das Dateiformat gibt an, Sie in möchten, sollen, die **Dateiname** Feld. Z. B. *: MeineDatei.gif*.

   > [!NOTE]
   > Sie müssen erstellen oder öffnen die Bitmap außerhalb des Projekts, um ihn als ein anderes Dateiformat zu speichern. Wenn Sie beim Erstellen oder öffnen Sie diese in Ihrem Projekt die **speichern** Befehl nicht verfügbar. Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

6. Klicken Sie auf **Speichern**.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="see-also"></a>Siehe auch

[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)