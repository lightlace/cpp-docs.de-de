---
title: "Opening a Resource for Binary Editing | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.binary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary data, editing"
  - "resources [Visual Studio], opening for binary editing"
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Opening a Resource for Binary Editing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So öffnen Sie eine Windows\-Desktopressource zur Binärbearbeitung  
  
1.  Wählen Sie in der [Ressourcenansicht](../windows/resource-view-window.md) die bestimmte Ressourcendatei aus, die Sie bearbeiten möchten.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Klicken Sie mit der rechten Maustaste auf die Ressource, und klicken Sie im Kontextmenü auf **Binärdaten öffnen**.  
  
    > [!NOTE]
    >  Wenn Sie das Fenster [Ressourcenansicht](../windows/resource-view-window.md) verwenden, um eine Ressource in einem Format zu öffnen, das von Visual Studio nicht erkannt wird \(etwa eine RCDATA\- oder eine benutzerdefinierte Ressource\), wird die Ressource automatisch im Binär\-Editor geöffnet.  
  
### So öffnen Sie eine verwaltete Ressource für die Binärbearbeitung  
  
1.  Wählen Sie im Projektmappen\-Explorer die bestimmte Ressourcendatei aus, die Sie bearbeiten möchten.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Ressource, und wählen Sie im Kontextmenü **Öffnen mit** aus.  
  
3.  Wählen Sie im Dialogfeld **Öffnen mit** den **Binär\-Editor** aus.  
  
    > [!NOTE]
    >  Mit der [Bildbearbeitung](../mfc/image-editor-for-icons.md) und dem [Binär\-Editor](../mfc/binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio\-Ressourcen\-Editoren nicht unterstützt.  
  
    > [!NOTE]
    >  Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 ![Binär&#45;Editor](../mfc/media/vcbinaryeditor2.png "vcBinaryEditor2")  
Binärdaten für ein Dialogfeld in der Darstellung im Binär\-Editor  
  
 Nur bestimmte ASCII\-Werte werden im Binär\-Editor dargestellt \(0x20 bis 0x7E\). Erweiterte Zeichen werden im Bereich „ASCII\-Wert“ des Binär\-Editors \(dem rechten Bereich\) als Punkte dargestellt. Die "druckbaren" Zeichen sind die ASCII\-Werte 32 bis 126.  
  
> [!NOTE]
>  Wenn Sie den Binär\-Editor für eine Ressource verwenden möchten, die bereits in einem anderen Editor\-Fenster bearbeitet wird, schließen Sie zuerst das andere Editor\-Fenster.  
  
 **Anforderungen**  
  
 Keine  
  
## Siehe auch  
 [Binary Editor](../mfc/binary-editor.md)