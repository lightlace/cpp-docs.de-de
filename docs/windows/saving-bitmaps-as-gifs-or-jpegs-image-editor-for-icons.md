---
title: Speichern von Bitmaps als GIFs oder JPEGs (Bildbearbeitung für Symbole) | Microsoft Docs
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
- .gif files, saving bitmaps as
- jpg files, saving bitmaps as
- jpeg files, saving bitmaps as
- .jpg files, saving bitmaps as
- Image editor [C++], converting image formats
- gif files, saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files, saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aed35f50e8cb874cea833439150b717034244b95
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>Speichern von Bitmaps als GIFs oder JPEGs (Bildbearbeitung für Symbole)
Wenn Sie eine Bitmap erstellen, wird das Bild im Bitmapformat (BMP) erstellt. Sie können jedoch das Bild als GIF- oder JPEG oder in anderen Formaten Grafiken speichern.  
  
> [!NOTE]
>  Dieser Prozess gilt nicht für Symbole und Cursor.  
  
### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Zum Erstellen und speichern eine Bitmap als GIF- oder JPEG  
  
1.  Aus der **Datei** Menü wählen **öffnen**, klicken Sie dann auf **Datei**.  
  
2.  In der **Dialogfeld neue Datei**, klicken Sie auf die **Visual C++** Ordner, wählen Sie dann **Bitmapdatei (BMP)** in der **Vorlagen** Feld, und klicken Sie auf  **Open**.  
  
     Die Bitmap wird geöffnet, der **Image** Editor.  
  
3.  Nehmen Sie Änderungen an der neuen Bitmap, nach Bedarf.  
  
4.  Mit der Bitmap, die noch geöffnet, in der **Image** -Editor, klicken Sie auf **speichern *Filename*BMP als** auf die **Datei** Menü.  
  
5.  In der **Datei speichern unter** Dialogfeld Geben Sie den Namen, die auf die Datei und die Erweiterung, die das Dateiformat bezeichnet, Sie in möchten, erhalten sollen die **Dateiname** Feld. Zum Beispiel: MeineDatei.gif.  
  
     **Hinweis** müssen Sie erstellen oder öffnen Sie die Bitmap außerhalb von Ihrem Projekt, um ihn als ein anderes Dateiformat zu speichern. Wenn Sie beim Erstellen oder öffnen Sie diese in Ihrem Projekt die **speichern unter** Befehl ist nicht verfügbar. Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
6.  Klicken Sie auf **Speichern**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

