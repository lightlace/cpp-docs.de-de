---
title: "Image Editor for Icons | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.cursor.F1"
  - "vc.editors.icon.F1"
  - "vc.editors.cursor"
  - "vc.editors.bitmap.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors, images"
  - "resource editors, graphics"
  - "Image editor [C++]"
  - "resource editors, Image editor"
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Image Editor for Icons
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Bildbearbeitung verfügt über zahlreiche Tools zum Erstellen und Bearbeiten von Bildern sowie über Funktionen, die Sie beim Erstellen von Bitmaps für Symbolleisten unterstützen. Zusätzlich zu Bitmaps, Symbolen und Cursorn können Sie Bilder im GIF\- oder JPEG\-Format bearbeiten. Zu diesem Zweck verwenden Sie die Befehle aus dem Menü **Bild** und die Tools auf der Symbolleiste der **Bildbearbeitung**.  
  
 Von der Bildbearbeitung werden die folgenden Aufgaben unterstützt:  
  
-   [Bearbeiten von grafischen Ressourcen](../mfc/editing-graphical-resources-image-editor-for-icons.md)  
  
-   [Arbeiten mit Farben](../mfc/working-with-color-image-editor-for-icons.md)  
  
-   [Arbeiten mit Symbolen und Cursorn: Bildressourcen für Anzeigegeräte](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
  
-   [Verwenden von Zugriffstasten für den Grafik\-Editor](../mfc/accelerator-keys-image-editor-for-icons.md)  
  
 Das Fenster der Bildbearbeitung enthält zwei Ansichten eines Bilds. Die beiden Bereiche werden von einem Fensterteiler unterteilt. Zum Ändern der relativen Größe der Fensterbereiche kann der Fensterteiler seitlich gezogen werden. Der aktive Bereich ist von einem Markierungsrahmen umgeben.  
  
 Das Fenster der Bildbearbeitung kann entsprechend Ihren Anforderungen und Prioritäten angepasst werden. Sie können den [Vergrößerungsfaktor ändern](../mfc/changing-the-magnification-factor-image-editor-for-icons.md) und das [Pixelraster ein\- oder ausblenden](../mfc/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md).  
  
> [!NOTE]
>  Mit der Bildbearbeitung können Sie 32\-Bit\-Bilder anzeigen, sie aber nicht bearbeiten.  
  
## Visual Studio\-Bildbibliothek  
 Sie können die Visual Studio\-Bildbibliothek kostenlos herunterladen. Sie enthält zahlreiche Animationen, Bitmaps und Symbole, die Sie in Ihren Anwendungen verwenden können. Weitere Informationen über das Herunterladen der Bibliothek finden Sie unter [Die Visual Studio\-Bildbibliothek](../Topic/The%20Visual%20Studio%20Image%20Library.md).  
  
## Verwaltete Ressourcen  
 Mit der [Bildbearbeitung](../mfc/binary-editor.md) und dem Binär\-Editor ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio\-Ressourcen\-Editoren nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 Keine  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)   
 [Symbole](http://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)