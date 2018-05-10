---
title: Öffnen eine Ressource für die Binärbearbeitung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- resources [Visual Studio], opening for binary editing
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c09cd825a5974422eaf757419f4ce890f5123100
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="opening-a-resource-for-binary-editing"></a>Öffnen einer Ressource für die Binärbearbeitung
### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>So öffnen Sie eine Windows-Desktopressource zur Binärbearbeitung  
  
1.  Wählen Sie in der [Ressourcenansicht](../windows/resource-view-window.md)die bestimmte Ressourcendatei aus, die Sie bearbeiten möchten.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Klicken Sie mit der rechten Maustaste auf die Ressource, und klicken Sie im Kontextmenü auf **Binärdaten öffnen** .  
  
    > [!NOTE]
    >  Wenn Sie das Fenster [Ressourcenansicht](../windows/resource-view-window.md) verwenden, um eine Ressource in einem Format zu öffnen, das von Visual Studio nicht erkannt wird (etwa eine RCDATA- oder eine benutzerdefinierte Ressource), wird die Ressource automatisch im Binär-Editor geöffnet.  
  
### <a name="to-open-a-managed-resource-for-binary-editing"></a>So öffnen Sie eine verwaltete Ressource für die Binärbearbeitung  
  
1.  Wählen Sie im Projektmappen-Explorer die bestimmte Ressourcendatei aus, die Sie bearbeiten möchten.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Ressource, und wählen Sie im Kontextmenü **Öffnen mit** aus.  
  
3.  Wählen Sie im Dialogfeld **Öffnen mit** den **Binär-Editor**aus.  
  
    > [!NOTE]
    >  Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.  
  
    > [!NOTE]
    >  Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).   
  
 ![Binär-Editor](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")  
Binärdaten für ein Dialogfeld in der Darstellung im Binär-Editor  
  
 Nur bestimmte ASCII-Werte werden im Binär-Editor dargestellt (0x20 bis 0x7E). Erweiterte Zeichen werden im Bereich „ASCII-Wert“ des Binär-Editors (dem rechten Bereich) als Punkte dargestellt. Die "druckbaren" Zeichen sind die ASCII-Werte 32 bis 126.  
  
> [!NOTE]
>  Wenn Sie den Binär-Editor für eine Ressource verwenden möchten, die bereits in einem anderen Editor-Fenster bearbeitet wird, schließen Sie zuerst das andere Editor-Fenster.  
  
 **Anforderungen**  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Binary Editor](binary-editor.md)

