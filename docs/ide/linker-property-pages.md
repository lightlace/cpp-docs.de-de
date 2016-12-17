---
title: "Eigenschaftenseiten &quot;Linker&quot;"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RegisterOutput"
  - "VC.Project.VCLinkerTool.IgnoreImportLibrary"
  - "VC.Project.VCLinkerTool.UseLibraryDependencyInputs"
  - "VC.Project.VCLinkerTool.LinkLibraryDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Umleitung pro Benutzer"
  - "Linker-Eigenschaftenseiten"
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenseiten &quot;Linker&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden die folgenden Eigenschaften erörtert, die sich auf der Eigenschaftenseite **Allgemein** des Linkers befinden:  
  
 **Importbibliothek ignorieren**  
 Durch diese Option wird der Linker angewiesen, keine während des aktuellen Builds erstellte LIB\-Ausgabe mit einem abhängigen Projekt zu verknüpfen.  Auf diese Weise kann das Projektsystem DLL\-Dateien verarbeiten, durch die während der Erstellung keine LIB\-Datei generiert wird.  Wenn ein Projekt von einem anderen Projekt abhängt, das eine DLL generiert, verknüpft das Projektsystem automatisch die LIB\-Datei, die von diesem untergeordneten Projekt erstellt wurde.  Diese Verknüpfung ist für Projekte, die COM\-DLLs oder reine Ressourcen\-DLLs erstellen, u. U. nicht erforderlich. Diese DLLs exportieren keine wichtigen Daten.  Wenn eine DLL über keine Exportdaten verfügt, wird vom Linker auch keine LIB\-Datei erstellt.  Wenn auf dem Datenträger keine LIB\-Exportdatei vorhanden ist und der Linker vom Projektsystem angewiesen wird, eine Verknüpfung mit dieser \(fehlenden\) DLL zu erstellen, schlägt die Verknüpfung fehl.  
  
 Verwenden Sie **Importbibliothek ignorieren**, um dieses Problem zu beheben.  Wenn Sie `Yes` auswählen, ignoriert das Projektsystem das Vorhandensein bzw. das Fehlen der LIB\-Datei, und jedes von diesem Projekt abhängige Projekt wird daran gehindert, eine Verknüpfung mit der nicht vorhandenen LIB\-Datei zu erstellen.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary*>.  
  
 **Ausgabe registrieren**  
 Führen Sie "regsvr32.exe \/s $\(TargetPath\)" aus, die nur für DLL\-Projekte zulässig ist.  Bei EXE\-Projekten wird diese Eigenschaft ignoriert.  Wenn Sie eine EXE\-Ausgabedatei registrieren möchten, legen Sie für die Konfiguration ein Postbuildereignis fest, um die benutzerdefinierte Registrierung auszuführen, die für registrierte EXE\-Dateien stets erforderlich ist.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput*>.  
  
 **Umleitung pro Benutzer**  
 Die Registrierung in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] erfolgte herkömmlicherweise in HKEY\_CLASSES\_ROOT \(HKCR\).  Bei [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] müssen Sie [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] im erhöhten Modus ausführen, um auf HKCR zuzugreifen.  Entwickler möchten die Software nicht immer im erhöhten Modus ausführen, müssen aber trotzdem mit der Registrierung arbeiten.  Die Umleitung pro Benutzer ermöglicht Ihnen die Registrierung, ohne die Software in diesem Modus ausführen zu müssen.  
  
 Mit der Umleitung pro Benutzer wird die Umleitung aller für HKCR geschriebenen Daten in HKEY\_CURRENT\_USER \(HKCU\) erzwungen.  Wenn die Umleitung pro Benutzer deaktiviert ist, kann dies zu [Projektbuildfehler PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) führen, wenn das Programm versucht, in HKCR zu schreiben.  
  
 **Bibliothekabhängigkeiten verknüpfen**  
 Diese Option bietet die Möglichkeit, innerhalb den von abhängigen Projekten generierten LIB\-Dateien Verknüpfungen zu erstellen.  Normalerweise werden Verknüpfungen in der LIB\-Datei erstellt.  
  
 Sie können auch eine OBJ\-Datei angeben, indem Sie den Dateinamen und den relativen Pfad, beispielsweise **..\\..\\MyLibProject\\MyObjFile.obj**, angeben.  Wenn der Quellcode für die OBJ\-Datei einen vorkompilierten Header, beispielsweise pch.h, enthält, befindet sich die pch.obj\-Datei im gleichen Ordner wie **MyObjFile.obj**. Dann müssen Sie auch **pch.obj** als zusätzliche Abhängigkeit hinzufügen.  
  
 **Bibliothekabhängigkeitseingaben verwenden**  
 Wenn durch ein abhängiges Projekt in einem umfangreichen Projekt eine LIB\-Datei generiert wird, werden inkrementelle Verknüpfungen deaktiviert.  Wenn es viele abhängige Projekte gibt, durch die LIB\-Dateien generiert werden, kann die Anwendungserstellung längere Zeit in Anspruch nehmen.  Wenn diese Eigenschaft auf `Yes` festgelegt ist, erstellt das Projektsystem in den OBJ\-Dateien Verknüpfungen für LIB\-Dateien, die von abhängigen Projekten generiert wurden, sodass inkrementelle Verknüpfungen möglich sind.  
  
 Informationen dazu, wie Sie auf die Linker\-Eigenschaftenseite **Allgemein** zugreifen, finden Sie unter [Gewusst wie: Festlegen von Projekteigenschaften mit Eigenschaftenseiten](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
## Siehe auch  
 [VC\+\+ Directories, Projects and Solutions, Options Dialog Box](assetId:///e027448b-c811-4c3d-8531-4325ad3f6e02)   
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)