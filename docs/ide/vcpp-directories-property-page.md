---
title: VC++-Verzeichnisse Eigenschaftenseite | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs:
- C++
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3acaccff2e2764f4fd7f6f4815f5721f0ba845a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="vc-directories-property-page-windows"></a>VC++-Verzeichnisse Eigenschaftenseite (Windows)

Verwenden Sie diese Eigenschaftenseite Visual Studio mitteilen, welche Verzeichnisse beim Erstellen des Projekts aktuell ausgewählt ist. Verwenden Sie ein benutzerdefiniertes Eigenschaftenfenster zum Festlegen von Verzeichnissen für mehrere Projekte in einer Projektmappe, wie in beschrieben [Erstellen von wiederverwendbaren Eigenschaftenkonfigurationen](working-with-project-properties.md#bkmkPropertySheets).

Die Linux-Version auf dieser Seite finden Sie unter [VC++-Verzeichnisse (Linux C++)](../linux/prop-pages/directories-linux.md).   

Für den Zugriff auf die **VC++-Verzeichnisse** Eigenschaftenseite:

1. Wenn die **Projektmappen-Explorer** nicht sichtbar ist, wählen Sie dann im Hauptmenü **Ansicht** > **Projektmappen-Explorer**.
1. Mit der rechten Maustaste auf einen Projektknoten (nicht der obersten Ebene Projektmappe), und wählen Sie **Eigenschaften**.
1. Im linken Bereich des der **Eigenschaftenseiten** wählen Sie im Dialogfeld **Konfigurationseigenschaften** > **VC++-Verzeichnisse**.  

VC++-Verzeichnisse Eigenschaften gelten für ein Projekt, nicht den Projektmappenknoten auf oberster Ebene. Wenn Sie nicht sehen **VC++-Verzeichnisse** unter **Konfigurationseigenschaften**, wählen Sie den Knoten eines C++-Projekts in der **Projektmappen-Explorer** Fenster: 

![Wählen Sie den Projektknoten](media/vcppdir.png "wählen Sie den Projektknoten, um die Eigenschaften der VC++-Verzeichnisse finden Sie unter")

Beachten Sie, dass die **VC++-Verzeichnisse** Eigenschaftenseite für plattformübergreifende Projekte sieht anders. Informationen zu Linux-C++-Projekten finden Sie unter [VC++-Verzeichnisse (Linux C++)](../linux/prop-pages/directories-linux.md). 
 
Wenn Sie mit nicht vertraut sind *Projekteigenschaften* in Visual Studio Sie finden es vielleicht hilfreich sein, der erste Lesevorgang [arbeiten mit Projekteigenschaften](working-with-project-properties.md). 
 
Die Standardeinstellungen für **VC++-Verzeichnisse** Eigenschaften auf Grundlage des Projekttyps abhängig sind. Für Desktopprojekte enthalten sie die C++-Tools-Speicherorte für eine bestimmte Plattformtoolset und den Speicherort des Windows SDK. Sie können ändern, die **Plattformtoolset** und **Version des Windows SDK** auf die **Konfigurationseigenschaften** > **allgemeine** Seite ". 

So zeigen Sie die Werte für keines der Verzeichnisse an:

1. Wählen Sie eine der Eigenschaften in der **VC++-Verzeichnisse** Seite. Wählen Sie z. B. **Bibliotheksverzeichnisse**.
1. Wählen Sie die nach-unten Schaltfläche am Ende der dem Feld für Eigenschaftswerte aus.
1. Wählen Sie in der Dropdown-Menü **bearbeiten**.

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
  
**Ausführbare Verzeichnisse**<br/>
Verzeichnisse, in denen nach ausführbaren Dateien gesucht wird. Entspricht der **Pfad** -Umgebungsvariablen angegeben.

**Includeverzeichnisse**<br/>
Verzeichnisse, in denen nach Includedateien gesucht wird, auf die im Quellcode verwiesen wird. Entspricht der **INCLUDE** -Umgebungsvariablen angegeben.

**Verweisverzeichnisse**<br/>
 Verzeichnisse, in denen für die Suche nach Assembly- und Moduldateien (Metadaten), die in den Quellcode von referenziert werden die [#using](../preprocessor/hash-using-directive-cpp.md) Richtlinie. Entspricht der **LIBPATH** -Umgebungsvariablen angegeben.

**Bibliotheksverzeichnisse**<br/>
Verzeichnisse, in denen nach Bibliotheksdateien (.LIB-Dateien) gesucht wird. Dies schließt auch die Laufzeitbibliotheken ein. Entspricht der **LIB** -Umgebungsvariablen angegeben. Diese Einstellung gilt nicht für OBJ-Dateien; für eine Verknüpfung mit einer OBJ-Datei, auf die **Konfigurationseigenschaften** > **Linker** > **allgemeine** Eigenschaftenseite  **Zusätzliche Bibliotheksverzeichnisse** , und geben Sie den relativen Pfad der Datei. Weitere Informationen finden Sie unter [Linker-Eigenschaftenseiten](../ide/linker-property-pages.md).

**WinRT Bibliotheksverzeichnisse**<br/>
Verzeichnisse für WinRT-Bibliotheksdateien für die Suche in apps der universellen Windows-Plattform (UWP) verwenden. 

**Quellverzeichnisse**<br/>
Verzeichnisse, in denen nach Quelldateien gesucht wird, die für IntelliSense verwendet werden sollen.

**Ausschließen von Verzeichnissen**<br/>
Vor jeder Kompilierung fragt Visual Studio den Zeitstempel für alle Dateien, um festzustellen, ob alle seit der letzten Kompilierung geändert worden sein. Wenn das Projekt große stabile Bibliotheken hat, können Sie potenziell Buildzeiten beschleunigen durch Ausschließen dieser Verzeichnisse gegenüber der Timestamp-Überprüfung.

## <a name="sharing-the-settings"></a>Freigeben der Einstellungen

Sie können Projekteigenschaften für andere Benutzer oder Computer freigeben. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).
