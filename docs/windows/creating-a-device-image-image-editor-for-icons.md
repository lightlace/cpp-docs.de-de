---
title: "Erstellen eines Gerätebilds (Bildbearbeitung für Symbole) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices
- display devices, creating image
- images [C++], creating for display devices
- icons [C++], inserting
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d68a9d35471e43296cade829700fc6c5b311ce2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>Erstellen eines Gerätebilds (Bildbearbeitung für Symbole)
Wenn Sie eine neue Symbols oder Cursors mit Ressource, das Bild-Editor erstellen erstellt zunächst ein Bild in einem bestimmten Format (32 x 32, 16 Farben für Symbole und 32 x 32, Monochrom für Cursor). Sie können Bilder in verschiedenen Größen und Formate auf das erste Symbol oder Cursor hinzufügen und jede zusätzliche Bild nach Bedarf für die verschiedenen Anzeigegeräte bearbeiten. Sie können ein Bild auch durch Ausschneiden und Einfügen aus einem vorhandenen Image-Typ oder von einer Bitmap in einem Graphics-Programm erstellt bearbeiten.  
  
 Beim Öffnen der Symbols oder Cursors mit Ressourcen in der [bildbearbeitung](../windows/image-editor-for-icons.md), das Bild, das das aktuellen Anzeigegerät am ehesten entspricht, wird standardmäßig geöffnet.  
  
### <a name="to-create-a-new-icon-or-cursor"></a>So erstellen ein neues Symbol oder cursor  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste der RC-Datei, und wählen Sie dann **Ressource einfügen** aus dem Kontextmenü. (Falls Sie eine Bildressource in der RC-Datei, z. B. einen Cursor, noch können Sie einfach auf Rechtsklicken der **Cursor** Ordner, und wählen **Cursor einfügen** aus dem Kontextmenü.)  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  In der [Dialogfeld "Ressource einfügen"](../windows/add-resource-dialog-box.md)Option **Symbol** oder **Cursor** , und klicken Sie auf **neu**. Für Symbole wird hierdurch eine Symbolressource mit 32 x 32 Pixel und 16 Farben erstellt. Bei Cursorn 32 x 32 Pixel, wird die Bildtypen (2-Farbe) erstellt.  
  
     Wenn ein Pluszeichen (**+**) wird neben der Image-Ressourcentyp im angezeigt, die **Ressource einfügen** (Dialogfeld), es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Klicken Sie auf das Pluszeichen (+) erweitern die Liste der Vorlagen, wählen Sie eine Vorlage, und klicken Sie auf **neu**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 **Anforderungen**  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)
