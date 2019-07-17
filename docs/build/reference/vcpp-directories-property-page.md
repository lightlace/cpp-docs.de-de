---
title: Eigenschaftenseite "VC++-Verzeichnisse"
ms.date: 07/17/2019
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
ms.openlocfilehash: 9b005a89156db48615ec6ea8dfc4f07a7414fc3b
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299790"
---
# <a name="vc-directories-property-page-windows"></a>Eigenschaftenseite „VC++-Verzeichnisse“ (Windows)

Verwenden Sie diese Eigenschaftenseite, um Visual Studio mitzuteilen, welche Verzeichnisse verwendet werden sollen, wenn das derzeit ausgewählte Projekt erstellt wird. Wenn Sie Verzeichnisse für mehrere Projekte in einer Projekt Mappe festlegen möchten, verwenden Sie ein benutzerdefiniertes Eigenschaften Blatt wie unter [freigeben oder wieder verwenden von Visual Studio C++ -Projekteinstellungen](../create-reusable-property-configurations.md)beschrieben.

Die Linux-Version dieser Seite finden Sie unter [VC++-Verzeichnisse (Linux C++)](../../linux/prop-pages/directories-linux.md).

So greifen Sie auf die Eigenschaftenseite **VC++-Verzeichnisse** zu:

1. Wenn das Fenster **Projektmappen-Explorer** nicht angezeigt wird, klicken Sie im Hauptmenü auf **Ansicht** > **Projektmappen-Explorer**.
1. Klicken Sie mit der rechten Maustaste auf einen Projektknoten (nicht auf die Projektmappe auf oberster Ebene), und wählen Sie **Eigenschaften** aus.
1. Klicken Sie im linken Bereich des Dialogfelds **Eigenschaftenseiten** auf **Konfigurationseigenschaften** > **VC++-Verzeichnisse**.

Die Eigenschaften für VC++-Verzeichnisse gelten für ein Projekt, nicht für den Projektmappenknoten auf oberster Ebene. Wenn **VC++-Verzeichnisse** nicht unter **Konfigurationseigenschaften** angezeigt wird, wählen Sie einen C++-Projektknoten im Fenster **Projektmappen-Explorer** aus:

![Auswählen des Projektknotens](../media/vcppdir.png "Auswählen des Projektknotens zum Anzeigen der Eigenschaften von VC++-Verzeichnissen")

Beachten Sie, dass die Eigenschaftenseite **VC++-Verzeichnisse** für plattformübergreifende Projekte anders aussieht. Weitere Informationen zu C++-Projekten unter Linux finden Sie unter [VC++-Verzeichnisse (Linux C++)](../../linux/prop-pages/directories-linux.md).

Wenn Sie mit den *Projekteigenschaften* in Visual Studio nicht vertraut sind, ist es möglicherweise hilfreich, zuerst [Set C++ Compiler und Buildeigenschaften in Visual Studio](../working-with-project-properties.md)zu lesen.

Die Standardeinstellungen für die Eigenschaften der **VC++-Verzeichnisse** hängen vom Projekttyp ab. Bei Desktopprojekten enthalten diese die Speicherorte der C++-Tools für ein bestimmtes Plattformtoolset sowie den Speicherort des Windows SDK. Sie können das **Plattformtoolset** und die Version des **Windows SDK** auf der Seite **Konfigurationseigenschaften** > **Allgemein** ändern.

So zeigen Sie die Werte für Verzeichnisse an:

1. Wählen Sie eine der Eigenschaften auf der Seite **VC++-Verzeichnisse** aus, z.B. **Bibliotheksverzeichnisse**.
1. Klicken Sie am Ende des Felds für Eigenschaftswerte auf die Schaltfläche mit dem Pfeil nach unten.
1. Wählen Sie im Dropdownmenü **Bearbeiten** aus.

![Bearbeiten von Bibliotheksverzeichnissen](../media/vcppdir_libdir_edit.png "Dialogfenster für das Bearbeiten von Bibliothekspfaden")

Folgendes Dialogfeld wird angezeigt:

![Anzeigen von Bibliotheksverzeichnissen](../media/vcppdir_libdir.png "Dialogfeld für das Hinzufügen oder Entfernen von Bibliothekspfaden")

Verwenden Sie dieses Dialogfeld, um die aktuellen Verzeichnisse anzuzeigen. Wenn Sie ein Verzeichnis jedoch ändern oder eines hinzufügen möchten, sollten Sie den **Eigenschaften-Manager** verwenden, um ein Eigenschaftenblatt zu erstellen oder das Eigenschaftenblatt für den Standardbenutzer ändern. Weitere Informationen finden Sie unter [freigeben oder wieder verwenden von C++ Visual Studio-Projekteinstellungen](../create-reusable-property-configurations.md).

Wie Sie oben sehen, werden viele der abgeleiteten Pfade als Makros angegeben.  Klicken Sie auf die Schaltfläche **Makros** in der unteren rechten Ecke des Dialogfelds, um den aktuellen Wert eines Makros zu überprüfen. Beachten Sie, dass viele Makros vom Konfigurationstyp abhängen. Ein Makro in einem Debugbuild kann einen anderen Pfad als das gleiche Makro in einem Releasebuild ergeben.

Sie können im Bearbeitungsfeld nach teilweisen oder vollständigen Übereinstimmungen suchen. Die folgende Abbildung zeigt alle Makros, die die Zeichenfolge „WindowsSDK“ enthalten, sowie den aktuellen Pfad, den das Makro ergibt:

![Anzeigen von Makrowerten](../media/vcppdir_libdir_macros.png "Dialogfeld für das Bearbeiten von Makros")

Hinweis: Die Liste wird bei der Typisierungs Auflistung aufgefüllt. Drücken Sie nicht auf die **EINGABETASTE**.

Weitere Informationen zu Makros und deren Verwendung anstelle von hart codierten Pfaden, wenn möglich, finden Sie unter [festlegen C++ von Compiler-und Buildeigenschaften in Visual Studio](../working-with-project-properties.md).

Eine Liste der häufig verwendeten Makros finden Sie unter [Allgemeine Makros für Buildbefehle und-Eigenschaften](common-macros-for-build-commands-and-properties.md).

Sie können eigene Makros auf zwei Arten definieren:

- Legen Sie Umgebungsvariablen in einer Developer-Eingabeaufforderung fest. Alle Umgebungsvariablen werden als MSBuild-Eigenschaften oder -Makros behandelt.

- Definieren Sie Benutzermakros in einer PROPS-Datei. Weitere Informationen finden Sie unter [Property page macros (Makros für Eigenschaftenseiten)](../working-with-project-properties.md).

Weitere Informationen finden Sie in den folgenden Blogbeiträgen: [VC + +-Verzeichnisse](https://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [geerbte Eigenschaften und Eigenschaften Blätter](https://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx)und [Visual Studio C++ 2010 Project Upgrade Guide](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/).

## <a name="directory-types"></a>Verzeichnistypen

Sie können auch andere Verzeichnisse wie folgt angeben.

**Ausführbare Verzeichnisse**<br/>
Verzeichnisse, in denen nach ausführbaren Dateien gesucht wird. Entspricht der Umgebungsvariablen **PATH**.

**Includeverzeichnisse**<br/>
Verzeichnisse, in denen nach Includedateien gesucht wird, auf die im Quellcode verwiesen wird. Entspricht der Umgebungsvariablen **INCLUDE**.

**Verweisverzeichnisse**<br/>
Verzeichnisse, in denen nach Assembly- und Moduldateien (Metadaten) gesucht wird, auf die im Quellcode über die [#using](../../preprocessor/hash-using-directive-cpp.md)-Direktiven verwiesen wird. Entspricht der Umgebungsvariablen **LIBPATH**.

**Bibliotheksverzeichnisse**<br/>
Verzeichnisse, in denen nach Bibliotheksdateien (.LIB-Dateien) gesucht wird. Dies schließt auch die Laufzeitbibliotheken ein. Entspricht der Umgebungsvariablen **LIB**. Diese Einstellung gilt nicht für OBJ-Dateien. Für eine Verknüpfung mit einer OBJ-Datei klicken Sie auf der Eigenschaftenseite **Konfigurationseigenschaften** > **Linker** > **Allgemein** auf **Zusätzliche Bibliotheksverweise**, und geben Sie dann den relativen Pfad der Datei an. Weitere Informationen finden Sie unter [Linker property pages (Eigenschaftenseiten für Linker)](linker-property-pages.md).

**WinRT-Bibliotheksverzeichnisse**<br/>
Verzeichnisse für das Suchen nach WinRT-Bibliotheksdateien für die Verwendung in UWP-Apps (Universelle Windows-Plattform).

**Quellverzeichnisse**<br/>
Verzeichnisse, in denen nach Quelldateien gesucht wird, die für IntelliSense verwendet werden sollen.

**Ausschließbare Verzeichnisse**<br/>
Vor jeder Kompilierung fragt Visual Studio den Zeitstempel aller Dateien ab, um zu bestimmen, ob seit der letzten Kompilierung Änderungen an diesen vorgenommen wurden. Wenn Ihr Projekt eine große, stabile Bibliothek besitzt, können Sie die Buildzeiten eventuell beschleunigen, indem Sie diese Verzeichnisse aus der Überprüfung der Zeitstempel ausschließen.

## <a name="sharing-the-settings"></a>Freigeben der Einstellungen

Sie können Projekteigenschaften für andere Benutzer oder Computer freigeben. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).
