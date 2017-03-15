---
title: "How to: Open a Resource Script File in Text Format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource script files, opening in text format"
  - ".rc files, opening in text format"
  - "rc files, opening in text format"
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# How to: Open a Resource Script File in Text Format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt viele Situationen, in denen Sie die Inhalte der Ressourcenskriptdatei \(.rc\) Ihres Projekts anzeigen möchten, ohne dafür eine Ressource wie ein Dialogfeld im entsprechenden Ressourcen\-Editor zu öffnen.  Beispielsweise möchten Sie möglicherweise nach einer Zeichenfolge über alle Dialogfelder in der Ressourcendatei hinweg suchen, ohne dass Sie dafür jedes einzeln öffnen müssen.  
  
> [!NOTE]
>  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
 Sie können die Ressourcendatei einfach im Textformat öffnen, um alle darin enthaltenen Ressourcen anzuzeigen und um globale Vorgänge auszuführen, die durch den [Text\-Editor](assetId:///508e1f18-99d5-48ad-b5ad-d011b21c6ab1) unterstützt werden.  
  
> [!NOTE]
>  .rc\- oder resource.h\-Dateien werden von Ressourcen\-Editoren nicht direkt gelesen.  Der Ressourcencompiler kompiliert sie in .aps\-Dateien, die von den Ressourcen\-Editoren genutzt werden.  Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten.  Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind \(z. B. Kommentare\) während der Kompilierung verworfen.  Sobald die .aps\-Datei nicht mehr mit der .rc\-Datei synchron ist, wird die .rc\-Datei neu generiert \(z. B. überschreibt der Ressourcen\-Editor beim Speichern die .rc\-Datei und resource.h\-Datei\).  Alle Änderungen an den Ressourcen selbst bleiben in der .rc\-Datei, aber Kommentare gehen immer verloren, sobald die .rc\-Datei überschrieben wird.  Informationen zur Erhaltung von Kommentaren finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).  
  
### So öffnen Sie eine Ressourcenskriptdatei als Text  
  
1.  Wählen Sie im Menü **Datei** die Option **Öffnen**, und klicken Sie dann auf **Datei**.  
  
2.  Wechseln Sie im Dialogfeld **Datei öffnen** zur Ressourcenskriptdatei, die Sie im Textformat anzeigen möchten.  
  
3.  Markieren Sie die Datei, und klicken Sie dann auf den Dropdownpfeil auf der Schaltfläche **Öffnen** \(befindet sich auf der rechten Seite der Schaltfläche\).  
  
4.  Wählen Sie **Öffnen mit** aus dem Dropdownmenü aus.  
  
5.  Klicken Sie im Dialogfeld **Öffnen mit** auf **Quellcode\-Editor \(Text\)**.  
  
6.  Wählen Sie in der Dropdownliste **Öffnen als** die Option **Text** aus.  
  
     Die Ressource wird im Quellcode\-Editor geöffnet.  
  
 \- oder \-  
  
1.  Klicken Sie imProjektmappen\-Explorer mit der rechten Maustaste auf die RC\-Datei.  
  
2.  Wählen Sie im Kontextmenü **Öffnen mit** und dann **Quellcode\-Editor \(Text\)** aus.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)