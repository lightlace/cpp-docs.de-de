---
title: "Eigenschaftenseiten für das XML-Dokument-Generator-Tool | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs: C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc09dafc0f07bc16a11dd255419440b6464456c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="xml-document-generator-tool-property-pages"></a>Eigenschaftenseiten für das Tool XML-Dokument-Generator
Die Eigenschaftenseite "Tool zum Generieren von XML-Dokument" macht die Funktionalität von xdcmake.exe. XDCMake.exe führt XDC-Dateien in eine XML-Datei zusammen, wenn der Quellcode Dokumentationskommentare enthält und [/doc (Verarbeiten von Dokumentationskommentaren) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md) angegeben wird,. Finden Sie unter [empfohlene Tags für Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) Informationen zum Hinzufügen von Dokumentationskommentaren auf den Quellcode.  
  
> [!NOTE]
>  XDCMake.exe-Optionen in der Entwicklungsumgebung (Eigenschaftenseiten) unterscheiden sich von den Optionen, wenn xdcmake.exe in der Befehlszeile verwendet wird. Informationen zum Verwenden von xdcmake.exe in der Befehlszeile finden Sie unter [XDCMake-Verweis](../ide/xdcmake-reference.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Startbanner unterdrücken**  
 Unterdrückt die Copyrightmeldung.  
  
 **Zusätzliche Dokumentdateien**  
 Weitere Verzeichnisse, in denen das Projektsystem XDC-Dateien gesucht werden soll. XDCMake wird immer vom Projekt generierten XDC-Dateien gesucht. Es können mehrere Verzeichnisse angegeben werden.  
  
 **Dokument-Ausgabedatei**  
 Der Name und für den Verzeichniszugriff der Speicherort der XML-Ausgabedatei. Finden Sie unter [allgemeine Makros für Buildbefehle und-Eigenschaften](../ide/common-macros-for-build-commands-and-properties.md) Informationen zur Verwendung von Makros Verzeichnisspeicherorte angeben.  
  
 **Bibliothekabhängigkeiten Dokument**  
 Wenn Ihr Projekt eine LIB-Projekt in der Projektmappe eine abhängig ist, können Sie XDC-Dateien aus dem LIB-Projekt in der XML-Dateien für das aktuelle Projekt verarbeiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)   
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)