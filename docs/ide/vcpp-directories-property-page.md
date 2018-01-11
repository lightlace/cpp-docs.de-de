---
title: VC++-Verzeichnisse Eigenschaftenseite | Microsoft Docs
ms.custom: 
ms.date: 11/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs: C++
helpviewer_keywords: VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c92a97ccd28a1bc7d1fae518cf499b45d339dae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vc-directories-property-page-windows"></a>VC++-Verzeichnisse Eigenschaftenseite (Windows)

Verwenden Sie diese Eigenschaftenseite Visual Studio mitteilen, welche Verzeichnisse beim Erstellen des Projekts aktuell ausgewählt ist. Verwenden Sie ein benutzerdefiniertes Eigenschaftenfenster zum Festlegen von Verzeichnissen für mehrere Projekte in einer Projektmappe, wie in beschrieben [Erstellen von wiederverwendbaren Eigenschaftenkonfigurationen](working-with-project-properties.md#bkmkPropertySheets).

Die Linux-Version auf dieser Seite finden Sie unter [VC++-Verzeichnisse (Linux C++)](../linux/prop-pages/directories-linux.md).   

Für den Zugriff auf die **VC++-Verzeichnisse** Eigenschaftenseite:

1. Wählen Sie im Hauptmenü **Ansicht | Projektmappen-Explorer**
1. mit der rechten Maustaste auf den Projektknoten (nicht der obersten Ebene Projektmappe), und wählen Sie **Eigenschaften**
1. im linken Bereich des der **Eigenschaftenseiten** Dialogfeld erweitern Sie **Konfigurationseigenschaften** , und wählen Sie **VC++-Verzeichnisse**.  

VC++-Verzeichnisse Eigenschaften gelten für ein Projekt, nicht den Projektmappenknoten auf oberster Ebene:

![Wählen Sie den Projektknoten](media/vcppdir.png "wählen Sie den Projektknoten, um die Eigenschaften der VC++-Verzeichnisse finden Sie unter")

Wenn Sie die Eigenschaftenseite nicht angezeigt wird, stellen sicher, dass Sie den Projektknoten im ausgewählten **Projektmappen-Explorer**. Beachten Sie, dass eine **VC++-Verzeichnisse** Eigenschaftenseite für plattformübergreifende Projekte sieht anders. Nicht-Windows-Projekte finden Sie unter [VC++-Verzeichnisse (Linux C++)](../linux/prop-pages/directories-linux.md) oder. 
 
Wenn Sie mit nicht vertraut sind *Projekteigenschaften* in Visual Studio Sie finden es vielleicht hilfreich sein, der erste Lesevorgang [arbeiten mit Projekteigenschaften](working-with-project-properties.md). 
 
Die Standardeinstellungen für VC++-Verzeichnisse hängen vom Projekttyp ab. Für Desktopprojekte enthalten sie die Speicherorte VC++-Tools für eine bestimmte Plattformtoolset und den Speicherort des Windows SDK. Sie können ändern, die **Plattformtoolset** und **Version des Windows SDK** auf die **Konfigurationseigenschaften – Allgemein** Seite. So zeigen Sie die Werte für keines der Verzeichnisse an:

1. im Bereich rechts von der **VC++-Verzeichnisse** Seite, wählen Sie eine Zeile. Beispielsweise **Bibliotheksverzeichnisse**
1. Wählen Sie die nach-unten Schaltfläche auf der rechten Seite
1. Wählen Sie **bearbeiten**.

![Bearbeiten von Bibliotheksverzeichnisse](media/vcppdir_libdir_edit.png "Dialogfeld Bibliothekspfade bearbeiten")

Sie sehen nun ein Dialogfeld folgendermaßen: 

![Anzeigen von Bibliotheksverzeichnisse](media/vcppdir_libdir.png "Dialogfeld zum Hinzufügen oder Entfernen von Bibliothekspfade")

Verwenden Sie dieses Dialogfeld, um die aktuellen Verzeichnisse anzuzeigen. Wenn Sie ändern oder ein Verzeichnis hinzufügen möchten, ist es jedoch eher die Verwendung **Eigenschaften-Manager** erstellen ein Eigenschaftenblatt oder ändern das Eigenschaftenblatt für Standard-Benutzer. Weitere Informationen finden Sie unter [Erstellen von wiederverwendbaren Eigenschaftenkonfigurationen](working-with-project-properties.md#bkmkPropertySheets).

Wie oben gezeigt, werden viele der geerbten Pfade als Makros angegeben.  Um den aktuellen Wert eines Makros zu untersuchen, wählen Sie die **Makros** Schaltfläche in der unteren rechten Ecke des Dialogfelds. Beachten Sie, dass der Konfigurationstyp viele Makros abhängen. Ein Makro in einem Debugbuild möglicherweise zu einem anderen Pfad als das gleiche Makro in einem Releasebuild ausgewertet werden. 

Sie können für teilweise oder vollständig Übereinstimmungen in das Bearbeitungsfeld suchen. Die folgende Abbildung zeigt alle Makros, die die Zeichenfolge "WindowsSDK" enthalten, und es zeigt auch den aktuellen Pfad, dem das Makro ergibt:

![Finden Sie unter Makrowerte](media/vcppdir_libdir_macros.png "Dialogfeld zum Bearbeiten von Makros")

Hinweis: Die Liste wird aufgefüllt, während der Eingabe. Drücken Sie nicht **EINGABETASTE**.

Weitere Informationen zu Makros und warum Sie diese anstatt hartcodierte Pfade möglichst verwenden sollten, finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md#bkmkPropertiesVersusMacros). 

Eine Liste der häufig verwendeten Makros, finden Sie unter [allgemeine Makros für Buildbefehle und-Eigenschaften](https://docs.microsoft.com/en-us/cpp/ide/common-macros-for-build-commands-and-properties).

Sie können Ihre eigenen Makros auf zwei Arten definieren:
-   Festlegen von Umgebungsvariablen in einem Developer-Eingabeaufforderung. Alle Umgebungsvariablen werden als MSBuild-Eigenschaften/Makros behandelt.
-   Definieren Sie Benutzermakros in eine PROPS-Datei. Weitere Informationen finden Sie unter [Eigenschaft Seite Makros](working-with-project-properties.md#bkmkPropertiesVersusMacros). 

Weitere Informationen finden Sie in folgenden Blogbeiträgen: [VC++-Verzeichnisse](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [geerbte Eigenschaften und Eigenschaftenblätter](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), und [Visual Studio 2010 C++-Projekt Upgradehandbuch](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).  
  
## <a name="directory-types"></a>Verzeichnistypen

Sie können auch andere Verzeichnisse wie folgt angeben.  
  
**Ausführbare Verzeichnisse**  
Verzeichnisse, in denen nach ausführbaren Dateien gesucht wird. Entspricht der **Pfad** -Umgebungsvariablen angegeben.

**Includeverzeichnisse**  
Verzeichnisse, in denen nach Includedateien gesucht wird, auf die im Quellcode verwiesen wird. Entspricht der **INCLUDE** -Umgebungsvariablen angegeben.

**Verweisverzeichnisse**  
 Verzeichnisse, in denen für die Suche nach Assembly- und Moduldateien (Metadaten), die in den Quellcode von referenziert werden die [#using](../preprocessor/hash-using-directive-cpp.md) Richtlinie. Entspricht der **LIBPATH** -Umgebungsvariablen angegeben.

**Bibliotheksverzeichnisse**  
Verzeichnisse, in denen nach Bibliotheksdateien (.LIB-Dateien) gesucht wird. Dies schließt auch die Laufzeitbibliotheken ein. Entspricht der **LIB** -Umgebungsvariablen angegeben. Diese Einstellung gilt nicht für OBJ-Dateien; für eine Verknüpfung mit einer OBJ-Datei, auf die [Linker](../ide/linker-property-pages.md)**allgemeine** Eigenschaftenseite select **Zusätzliche Bibliotheksverzeichnisse** , und geben Sie den relativen Pfad der Datei.

**Quellverzeichnisse**  
Verzeichnisse, in denen nach Quelldateien gesucht wird, die für IntelliSense verwendet werden sollen.

**Ausschließen von Verzeichnissen**  
Verzeichnisse, die beim Überprüfen von Buildabhängigkeiten nicht berücksichtigt werden.

## <a name="sharing-the-settings"></a>Freigeben der Einstellungen

Sie können Projekteigenschaften für andere Benutzer oder Computer freigeben. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).
