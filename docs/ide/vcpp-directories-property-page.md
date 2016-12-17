---
title: "Eigenschaftenseite &quot;VC++-Verzeichnisse&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCDirectories.IncludePath"
  - "VC.Project.VCDirectories.ReferencePath"
  - "VC.Project.VCDirectories.SourcePath"
  - "VC.Project.VCDirectories.LibraryWPath"
  - "VC.Project.VCDirectories.ExecutablePath"
  - "VC.Project.VCDirectories.LibraryPath"
  - "VS.ToolsOptionsPages.Projects.VCDirectories"
  - "VC.Project.VCDirectories.ExcludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Eigenschaftenseite "VC++-Verzeichnisse""
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: 25
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenseite &quot;VC++-Verzeichnisse&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Verzeichnisse an, die Visual Studio zum Erstellen eines Projekts verwenden soll.  Öffnen Sie für den Zugriff auf die Eigenschaftenseite im **Projektmappen\-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**. Erweitern Sie dann im linken Bereich des Dialogfelds **EigenschaftenseitenKonfigurationseigenschaften**, und wählen Sie **VC\+\+\-Verzeichnisse**.  
  
 Wenn Sie mit Visual Studio ein Projekt erstellen, erbt dieses bestimmte Verzeichnisse.  Viele davon sind Makros.  Zur Untersuchung des aktuellen Werts eines Makros im rechten Bereich der Seite **VC\+\+\-Verzeichnisse** wählen Sie eine Zeile, beispielsweise **Includeverzeichnisse**, wählen die Schaltfläche mit dem Pfeil nach unten und wählen dann **Bearbeiten**. Anschließend wählen Sie im angezeigten Dialogfeld die Schaltfläche **Makros**.  Weitere Informationen finden Sie in den Blogbeiträgen zu den Themen [VC\+\+\-Verzeichnisse](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx) und [Geerbte Eigenschaften und Eigenschaftenblätter](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx) sowie im [Visual Studio 2010 C\+\+\-Projektupgradehandbuch](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).  
  
## Verzeichnistypen  
 Sie können auch andere Verzeichnisse wie folgt angeben.  
  
 **Ausführbare Verzeichnisse**  
 Verzeichnisse, in denen nach ausführbaren Dateien gesucht wird.  Entspricht der Umgebungsvariablen **PATH**.  
  
 **Includeverzeichnisse**  
 Verzeichnisse, in denen nach Includedateien gesucht wird, auf die im Quellcode verwiesen wird.  Entspricht der Umgebungsvariablen **INCLUDE**.  
  
 **Verweisverzeichnisse**  
 Verzeichnisse, in denen nach Assembly\- und Moduldateien \(Metadaten\) gesucht wird, auf die im Quellcode über die [\#using](../preprocessor/hash-using-directive-cpp.md)\-Direktive verwiesen wird.  Entspricht der Umgebungsvariablen **LIBPATH**.  
  
 **Bibliotheksverzeichnisse**  
 Verzeichnisse, in denen nach Bibliotheksdateien \(.LIB\-Dateien\) gesucht wird. Dies schließt auch die Laufzeitbibliotheken ein.  Entspricht der Umgebungsvariablen **LIB**.  Diese Einstellung gilt nicht für OBJ\-Dateien. Für eine Verknüpfung mit einer OBJ\-Datei wählen Sie auf der [Linker](../ide/linker-property-pages.md)\-Eigenschaftenseite unter **Allgemein** die Option **Zusätzliche Bibliotheksverzeichnisse** aus und geben den relativen Pfad der Datei an.  
  
 **Quellverzeichnisse**  
 Verzeichnisse, in denen nach Quelldateien gesucht wird, die für IntelliSense verwendet werden sollen.  
  
 **Verzeichnisse ausschließen**  
 Verzeichnisse, die beim Überprüfen von Buildabhängigkeiten nicht berücksichtigt werden.  
  
#### So geben Sie Verzeichniseinstellungen an oder ändern diese  
  
1.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das zu ändernde Projekt, und wählen Sie **Eigenschaften**.  
  
2.  Erweitern Sie im linken Bereich des Dialogfelds **EigenschaftenseitenKonfigurationseigenschaften**, und wählen Sie **VC\+\+\-Verzeichnisse**.  
  
3.  Zum Ändern einer Verzeichnisliste wählen Sie diese aus, wählen dann die Schaltfläche mit dem Pfeil nach unten und wählen abschließend **Bearbeiten**.  
  
     Im Feld des angezeigten Dialogfelds können Sie Werte hinzufügen und entfernen sowie die Reihenfolge ändern, in der sie erscheinen.  Durch das Aktiveren oder Deaktivieren von **Vom übergeordneten Projekt erben oder Projektstandard** können Sie zudem festlegen, ob das Projekt Einstellungen erbt.  
  
## Freigeben der Einstellungen  
 Sie können Projekteigenschaften für andere Benutzer oder Computer freigeben.  Weitere Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
## Siehe auch  
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)