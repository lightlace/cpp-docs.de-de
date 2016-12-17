---
title: "Resource Files (Visual Studio)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio]"
  - ".rc files"
  - "resource files"
  - "resource script files"
  - "resource script files, Win-32 based applications"
  - "resource script files, files updated when editing resources"
  - "resources [Visual Studio], types of resource files"
  - "rct files"
  - "resources [C++]"
  - "rc files"
  - "resource files, types of"
  - ".rct files"
  - "resource script files, unsupported types"
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
caps.latest.revision: 18
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Resource Files (Visual Studio)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Diese Materialien beziehen sich auf Windows\-Desktopanwendungen. Informationen über Ressourcen in [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps finden Sie unter [Definieren von App\-Ressourcen](assetId:///476ea844-632c-4467-9ce3-966be1350dd4).  
>   
>  Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Da Projekte in .NET\-Programmiersprachen keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im **Projektmappen\-Explorer** öffnen. Mit der [Bildbearbeitung](../mfc/image-editor-for-icons.md) und dem [Binär\-Editor](../mfc/binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Die Ressourcen\-Editoren von Visual Studio unterstützen die Bearbeitung von eingebetteten Ressourcen nicht. Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Der Begriff „Ressourcendatei“ kann sich auf verschiedene Dateitypen beziehen, einschließlich dieser:  
  
-   Die Ressourcenskriptdatei \(RC\) eines Programms.  
  
-   Eine Ressourcenvorlagendatei \(RCT\).  
  
-   Eine einzelne Ressource, die als eigenständige Datei vorliegt, wie etwa eine Bitmap\-, eine Symbol\- oder eine Cursordatei, auf die von einer RC\-Datei verwiesen wird.  
  
-   Eine von der Entwicklungsumgebung generierte Headerdatei, beispielsweise „Resource.h“, auf die von einer RC\-Datei verwiesen wird.  
  
 Ressourcen können auch in [anderen Dateitypen](../windows/editable-file-types-for-resources.md) vorkommen, wie z. B. EXE, DLL und RES\-Dateien. Sie können mit Ressourcen und Ressourcendateien aus Ihrem Projekt arbeiten, aber auch mit solchen, die nicht Teil Ihres aktuellen Projekts sind. Sie können auch mit Ressourcendateien arbeiten, die nicht in der Entwicklungsumgebung von Visual Studio erstellt wurden. Sie haben unter anderem folgende Möglichkeiten:  
  
-   Arbeiten mit geschachtelten und bedingt eingeschlossenen Ressourcendateien.  
  
-   Aktualisieren vorhandener Ressourcen oder Konvertierung vorhandener Ressourcen in das Visual C\+\+\-Format.  
  
-   Importieren oder Exportieren grafischer Ressourcendateien in die oder aus der aktuelle\(n\) Ressourcendatei.  
  
-   Einschließen gemeinsam verwendeter oder schreibgeschützter Bezeichner \(Symbole\), die von der Entwicklungsumgebung nicht geändert werden können.  
  
-   Einschließen von Ressourcen in eine ausführbare Datei \(EXE\), die im Rahmen des aktuellen Projekts keine Bearbeitung erfordern \(oder deren Bearbeitung Sie nicht wünschen\), wie etwa bei Ressourcen, die von mehreren Projekten gemeinsam verwendet werden.  
  
-   Einschließen von Ressourcentypen, die von der Entwicklungsumgebung nicht unterstützt werden.  
  
 In diesem Abschnitt:  
  
-   [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md)  
  
-   [Erstellen einer neuen Ressource](../windows/how-to-create-a-resource.md)  
  
-   [Anzeigen von Ressourcen in einer Ressourcenskriptdatei](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
  
-   [Öffnen einer Ressourcenskriptdatei im Textformat](../windows/how-to-open-a-resource-script-file-in-text-format.md)  
  
-   [Einschließen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md)  
  
-   [Kopieren von Ressourcen](../windows/how-to-copy-resources.md)  
  
-   [Verwenden von Ressourcenvorlagen \(RCT\)](../windows/how-to-use-resource-templates.md)  
  
-   [Importieren und Exportieren von Ressourcen](../windows/how-to-import-and-export-resources.md)  
  
-   [Editierbare Dateitypen für Ressourcen](../windows/editable-file-types-for-resources.md)  
  
-   [Von der Ressourcenbearbeitung betroffene Dateien](../windows/files-affected-by-resource-editing.md)  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)   
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Menüs und weitere Ressourcen](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)