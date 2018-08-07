---
title: Öffnen einer Ressource für die Binärbearbeitung | Microsoft-Dokumentation
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
ms.openlocfilehash: 428c62db8f1444f497d6fede7affea34560b4b0e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605954"
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
  
1.  In **Projektmappen-Explorer**, wählen Sie die bestimmte Ressourcendatei, die Sie bearbeiten möchten.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Ressource, und wählen Sie im Kontextmenü **Öffnen mit** aus.  
  
3.  Wählen Sie im Dialogfeld **Öffnen mit** den **Binär-Editor**aus.  
  
    > [!NOTE]
    >  Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.  
  
    > [!NOTE]
    >  Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).   
  
 ![Binär-Editor](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")  
Binärdaten für ein Dialogfeld in der Darstellung im Binär-Editor  
  
 Nur bestimmte ASCII-Werte werden im Binär-Editor dargestellt (0x20 bis 0x7E). Erweiterte Zeichen werden im Bereich „ASCII-Wert“ des Binär-Editors (dem rechten Bereich) als Punkte dargestellt. Die "druckbaren" Zeichen sind die ASCII-Werte 32 bis 126.  
  
> [!NOTE]
>  Wenn Sie den Binär-Editor für eine Ressource verwenden möchten, die bereits in einem anderen Editor-Fenster bearbeitet wird, schließen Sie zuerst das andere Editor-Fenster.  
  
## <a name="requirements"></a>Anforderungen  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Binary Editor](binary-editor.md)