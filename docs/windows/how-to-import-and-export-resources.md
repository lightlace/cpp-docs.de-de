---
title: "How to: Import and Export Resources | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.resvw.resource.importing"
  - "vc.resvw.resource.importing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], exporting"
  - "graphics [C++], exporting"
  - "graphics [C++], importing"
  - "resources [Visual Studio], importing"
  - "bitmaps [C++], importing and exporting"
  - "toolbars [C++], importing"
  - "images [C++], importing"
  - "toolbars [C++], exporting"
  - "cursors [C++], importing and exporting"
  - "images [C++], exporting"
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# How to: Import and Export Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können grafische Ressourcen \(Bitmaps, Symbole, Cursor und Symbolleisten\), HTML\-Dateien und benutzerdefinierte Ressourcen für die Verwendung in Visual C\+\+ importieren.  Die können dieselben Dateitypen aus einem Visual C\+\+\-Projekt exportieren, um Dateien zu trennen, die außerhalb der Entwicklungsumgebung verwendet werden können.  
  
> [!NOTE]
>  Ressourcentypen wie Zugriffstasten, Dialogfelder und Zeichenfolgentabellen können weder im\- noch exportiert werden, da sie keine eigenständigen Dateitypen sind.  
  
### So importieren Sie eine einzelne Ressource in Ihre aktuelle Ressourcendatei  
  
1.  Klicken Sie mit der rechten Maustaste in der [Ressourcenansicht](../windows/resource-view-window.md) auf den Knoten für die Ressourcenskriptdatei \(\*.rc\), zu der Sie eine Ressource hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **Importieren**.  
  
3.  Suchen Sie nach dem Dateinamen der Bitmap\- \(.bmp\), Symbol\- \(.ico\), Cursor\- \(.cur\), HTML\- \(.html\) oder einer anderen zu importierenden Datei, und wählen Sie ihn aus.  
  
4.  Klicken Sie auf **OK**, um die Ressource zur ausgewählten Datei in der Ansicht **Ressource** hinzuzufügen.  
  
    > [!NOTE]
    >  Der Importvorgang funktioniert auf die gleiche Weise, und zwar unabhängig davon, welchen bestimmten Ressourcentyp Sie ausgewählt haben.  Die importierte Ressource wird automatisch zum richtigen Knoten für diesen Ressourcentyp hinzugefügt.  
  
### So exportieren Sie Bitmaps, Symbole oder Cursor als eine getrennte Datei \(für die Verwendung außerhalb von Visual C\+\+\)  
  
1.  Klicken Sie in der Ansicht **Ressource** mit der rechten Maustaste auf die zu exportierende Ressource.  
  
2.  Klicken Sie im Kontextmenü auf **Exportieren**.  
  
3.  Akzeptieren Sie im Dialogfeld **Ressource exportieren** den aktuellen Dateinamen, oder geben Sie einen neuen ein.  
  
4.  Wechseln Sie zum Ordner, in dem Sie die Datei speichern möchten, und klicken Sie auf **Exportieren**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)