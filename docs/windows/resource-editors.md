---
title: "Resource Editors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.editors.resource"
  - "vc.resvw.resource.editors"
  - "vs.resvw.resource.editors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors [C++], resource"
  - "editors [C++]"
  - "resource editors"
  - "Windows [C++], application resource editing"
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Resource Editors
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Ressourcen\-Editor ist eine spezialisierte Umgebung zum Erstellen oder Ändern von Ressourcen, die in einem Visual Studio\-Projekt enthalten sind. Die Ressourcen\-Editoren von Visual Studio teilen Techniken und Schnittstellen, die Sie beim schnellen und einfachen Erstellen und Ändern von Anwendungsressourcen unterstützen. Mithilfe von Ressourcen\-Editoren können Sie [Ressourcen im entsprechenden Editor anzeigen und bearbeiten](../mfc/viewing-and-editing-resources-in-a-resource-editor.md) sowie [Ressourcen in der Vorschau anzeigen](../mfc/previewing-resources.md).  
  
 Wenn Sie eine Ressource erstellen oder öffnen, wird automatisch der entsprechende Editor geöffnet.  
  
 **Hinweis** Da verwaltete Projekte keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im **Projektmappen\-Explorer** öffnen. Mit der [Bildbearbeitung](../mfc/image-editor-for-icons.md) und dem [Binär\-Editor](../mfc/binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio\-Ressourcen\-Editoren nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
|Verwenden Sie...|Zur Bearbeitung von...|  
|----------------------|----------------------------|  
|[Zugriffstasten\-Editor](../mfc/accelerator-editor.md)|Zugriffstastentabellen in Visual C\+\+\-Projekten.|  
|[Binär\-Editor](../mfc/binary-editor.md)|Binäre Daten und benutzerdefinierte Ressourcen in Visual C\+\+\-, Visual Basic\- oder Visual C\#\-Projekten.|  
|[Dialog\-Editor](../mfc/dialog-editor.md)|Dialogfelder in Visual C\+\+\-Projekten.|  
|[HTML\-Designer](../Topic/HTML%20Designer.md)|HTML\-Seiten in der Entwurfsansicht und in der HTML\-Ansicht. Einschränkung: Sie können keine HTML\-Seiten ändern, die sich in EXE\- oder DLL\-Dateien befinden, da die Änderungen nicht zurück in die EXE\- oder DLL\-Dateien importiert werden.|  
|[Grafik\-Editor](../mfc/image-editor-for-icons.md)|Bitmaps, Symbole, Cursor und andere Bilddateien in Visual C\+\+\-, Visual Basic\- oder Visual C\#\-Projekten.|  
|[Menü\-Editor](../mfc/menu-editor.md)|Menüressourcen in Visual C\+\+\-Projekten.|  
|[Ribbon\-Editor](../mfc/ribbon-designer-mfc.md)|Menübandressourcen in MFC\-Projekten.|  
|[Zeichenfolgen\-Editor](../mfc/string-editor.md)|Zeichenfolgentabellen in Visual C\+\+\-Projekten.|  
|[Symbolleisten\-Editor](../mfc/toolbar-editor.md)|Symbolleistenressourcen in Visual C\+\+\-Projekten. Der Symbolleisten\-Editor ist Teil des Grafik\-Editors.|  
|[Versionsinfo\-Editor](../mfc/version-information-editor.md)|Versionsinformationen in Visual C\+\+\-Projekten.|  
  
## Anforderungen  
 Keine  
  
## Siehe auch  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Menüs und weitere Ressourcen](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)