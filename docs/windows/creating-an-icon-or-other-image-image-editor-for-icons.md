---
title: Erstellen eines Symbols oder anderen Bilds (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resource toolbars
- resources [Visual Studio], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bab69a9f7e62161d95ebcf788a05f776af88f10f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607233"
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>Erstellen eines Symbols oder anderen Bilds (Bildbearbeitung für Symbole)

Sie können ein neues Image (Bitmap, Symbol, Cursor oder Symbolleiste) erstellen und dann die bildbearbeitung verwenden, um ihre Darstellung anzupassen. Sie können auch eine neue Bitmap Standardressource erstellen eine [Vorlage](../windows/how-to-use-resource-templates.md).

### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Beim Hinzufügen einer neuen imageressource zu einem nicht verwalteten C++-Projekt

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource einfügen** aus dem Kontextmenü. (Wenn Sie bereits über eine vorhandene imageressource in der RC-Datei, z. B. einen Cursor, haben Sie können einfach mit der rechten Maustaste die **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der [Ressource einfügen (Dialogfeld)](../windows/add-resource-dialog-box.md), wählen Sie den Typ der Bildressource, die Sie erstellen möchten (**Bitmap**, z. B.) klicken Sie dann auf **neu**.

   Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp in der **Ressource einfügen** Dialogfeld es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Klicken Sie auf das Pluszeichen, um der Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und auf **neu**.

### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Beim Hinzufügen einer neuen imageressource zu einem Projekt in einer Programmiersprache.

1. In **Projektmappen-Explorer**, mit der rechten Maustaste in des Projektordners (z. B. `WindowsApplication1`).

2. Klicken Sie im Kontextmenü auf **hinzufügen**, wählen Sie dann **neues Element hinzufügen**.

3. In der **Kategorien** Bereich, erweitern Sie die **Lokale Projektelemente** Ordner, wählen Sie dann **Ressourcen**.

4. In der **Vorlagen** Bereich, wählen Sie den Ressourcentyp, die Sie Ihrem Projekt hinzufügen möchten.

   Die Ressource wird hinzugefügt, um das Projekt im **Projektmappen-Explorer** und die Ressource wird geöffnet, der [bildbearbeitung](../windows/image-editor-for-icons.md). Sie können nun alle Tools zur Verfügung, in dem Bild-Editor verwenden, so ändern Sie Ihr Image. Weitere Informationen zum Hinzufügen von Bildern zu einem verwalteten Projekt finden Sie unter [Laden eines Bildes zur Entwurfszeit](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).

   > [!NOTE]
   > Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt. Weitere Informationen finden Sie unter [Erstellen von Ressourcendateien](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) in die *(.NET Framework Developer's Guide*.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
[Konvertieren von Bitmaps in Symbolleisten](../windows/converting-bitmaps-to-toolbars.md)  
[Erstellen neuer Symbolleisten](../windows/creating-new-toolbars.md)  
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)