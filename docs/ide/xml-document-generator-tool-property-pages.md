---
title: "Eigenschaftenseiten f&#252;r das Tool XML-Dokument-Generator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCXDCMakeTool.ValidateIntelliSense"
  - "VC.Project.VCXDCMakeTool.SuppressStartupBanner"
  - "VC.Project.VCXDCMakeTool.DocumentLibraryDependencies"
  - "VC.Project.VCXDCMakeTool.OutputDocumentFile"
  - "VC.Project.VCXDCMakeTool.AdditionalDocumentFiles"
dev_langs: 
  - "C++"
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Eigenschaftenseiten f&#252;r das Tool XML-Dokument-Generator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Eigenschaftenseite für das Tool XML\-Dokument\-Generator macht die Funktionen von xdcmake.exe verfügbar.  Wenn der Quellcode Dokumentationskommentare enthält und [\/doc \(Verarbeiten von Dokumentationskommentaren\)](../build/reference/doc-process-documentation-comments-c-cpp.md) angegeben ist, führt xdcmake.exe XDC\-Dateien in einer XML\-Datei zusammen.  Informationen zum Hinzufügen von Dokumentationskommentaren zu Quellcode finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
> [!NOTE]
>  Die Optionen für xdcmake.exe in der Entwicklungsumgebung \(Eigenschaftenseiten\) unterscheiden sich von den Optionen bei Verwendung von xdcmake.exe in der Befehlszeile.  Informationen zum Verwenden von xdcmake.exe in der Befehlszeile finden Sie unter [XDCMake\-Verweis](../ide/xdcmake-reference.md).  
  
## UIElement-Liste  
 **Startbanner unterdrücken**  
 Unterdrückt die Copyrightmeldung.  
  
 **Zusätzliche Dokumentdateien**  
 Zusätzliche Verzeichnisse, in denen das Projektsystem nach XDC\-Dateien suchen soll.  xdcmake sucht immer nach vom Projekt generierten XDC\-Dateien.   Es können mehrere Verzeichnisse angegeben werden.  
  
 **Ausgabedokumentdatei**  
 Name und Verzeichnis der XML\-Ausgabedatei.  Informationen zum Verwenden von Makros zum Angeben von Verzeichnissen finden Sie unter [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md).  
  
 **Dokumentbibliothekabhängigkeiten**  
 Wenn das Projekt über eine Abhängigkeit von einem LIB\-Projekt in der Lösung verfügt, können Sie XDC\-Dateien aus dem LIB\-Projekt in XML\-Dateien für das aktuelle Projekt verarbeiten.  
  
## Siehe auch  
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)   
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)