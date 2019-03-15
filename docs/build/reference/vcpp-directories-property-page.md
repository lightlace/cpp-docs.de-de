---
title: Eigenschaftenseite "VC++-Verzeichnisse"
ms.date: 10/09/2018
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
ms.openlocfilehash: 3822a3c751ac06154e4b13a12f449e7f0ff2cc07
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825541"
---
# <a name="vc-directories-property-page-windows"></a>Eigenschaftenseite „VC++-Verzeichnisse“ (Windows)

Verwenden Sie diese Eigenschaftenseite, um Visual Studio mitzuteilen, welche Verzeichnisse verwendet werden sollen, wenn das derzeit ausgewählte Projekt erstellt wird. Verwenden Sie zum Festlegen der Verzeichnisse für mehrere Projekte in einer Projektmappe ein benutzerdefiniertes Eigenschaftenfenster Siehe [Freigabe oder beabsichtigen Visual Studio C++-projekteinstellungen](../create-reusable-property-configurations.md).

Die Linux-Version dieser Seite finden Sie unter [VC++-Verzeichnisse (Linux C++)](../../linux/prop-pages/directories-linux.md).

So greifen Sie auf die Eigenschaftenseite **VC++-Verzeichnisse** zu:

1. Wenn das Fenster **Projektmappen-Explorer** nicht angezeigt wird, klicken Sie im Hauptmenü auf **Ansicht** > **Projektmappen-Explorer**.
1. Klicken Sie mit der rechten Maustaste auf einen Projektknoten (nicht auf die Projektmappe auf oberster Ebene), und wählen Sie **Eigenschaften** aus.
1. Klicken Sie im linken Bereich des Dialogfelds **Eigenschaftenseiten** auf **Konfigurationseigenschaften** > **VC++-Verzeichnisse**.

Die Eigenschaften für VC++-Verzeichnisse gelten für ein Projekt, nicht für den Projektmappenknoten auf oberster Ebene. Wenn **VC++-Verzeichnisse** nicht unter **Konfigurationseigenschaften** angezeigt wird, wählen Sie einen C++-Projektknoten im Fenster **Projektmappen-Explorer** aus:

![Auswählen des Projektknotens](../media/vcppdir.png "Auswählen des Projektknotens zum Anzeigen der Eigenschaften von VC++-Verzeichnissen")

Beachten Sie, dass die Eigenschaftenseite **VC++-Verzeichnisse** für plattformübergreifende Projekte anders aussieht. Weitere Informationen zu C++-Projekten unter Linux finden Sie unter [VC++-Verzeichnisse (Linux C++)](../../linux/prop-pages/directories-linux.md).

Wenn Sie mit nicht vertraut sind *Projekteigenschaften* in Visual Studio unter Umständen hilfreich sein, der erste Lesevorgang [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

Die Standardeinstellungen für die Eigenschaften der **VC++-Verzeichnisse** hängen vom Projekttyp ab. Bei Desktopprojekten enthalten diese die Speicherorte der C++-Tools für ein bestimmtes Plattformtoolset sowie den Speicherort des Windows SDK. Sie können das **Plattformtoolset** und die Version des **Windows SDK** auf der Seite **Konfigurationseigenschaften** > **Allgemein** ändern.

So zeigen Sie die Werte für Verzeichnisse an:

1. Wählen Sie eine der Eigenschaften auf der Seite **VC++-Verzeichnisse** aus, z.B. **Bibliotheksverzeichnisse**.
1. Klicken Sie am Ende des Felds für Eigenschaftswerte auf die Schaltfläche mit dem Pfeil nach unten.
1. Wählen Sie im Dropdownmenü **Bearbeiten** aus.

![Bearbeiten von Bibliotheksverzeichnissen](../media/vcppdir_libdir_edit.png "Dialogfenster für das Bearbeiten von Bibliothekspfaden")

Folgendes Dialogfeld wird angezeigt:

![Anzeigen von Bibliotheksverzeichnissen](../media/vcppdir_libdir.png "Dialogfeld für das Hinzufügen oder Entfernen von Bibliothekspfaden")

Verwenden Sie dieses Dialogfeld, um die aktuellen Verzeichnisse anzuzeigen. Wenn Sie ein Verzeichnis jedoch ändern oder eines hinzufügen möchten, sollten Sie den **Eigenschaften-Manager** verwenden, um ein Eigenschaftenblatt zu erstellen oder das Eigenschaftenblatt für den Standardbenutzer ändern. Weitere Informationen finden Sie unter [Freigabe oder beabsichtigen Visual Studio C++-projekteinstellungen](../create-reusable-property-configurations.md).

Wie Sie oben sehen, werden viele der abgeleiteten Pfade als Makros angegeben.  Klicken Sie auf die Schaltfläche **Makros** in der unteren rechten Ecke des Dialogfelds, um den aktuellen Wert eines Makros zu überprüfen. Beachten Sie, dass viele Makros vom Konfigurationstyp abhängen. Ein Makro in einem Debugbuild kann einen anderen Pfad als das gleiche Makro in einem Releasebuild ergeben.

Sie können im Bearbeitungsfeld nach teilweisen oder vollständigen Übereinstimmungen suchen. Die folgende Abbildung zeigt alle Makros, die die Zeichenfolge „WindowsSDK“ enthalten, sowie den aktuellen Pfad, den das Makro ergibt:

![Anzeigen von Makrowerten](../media/vcppdir_libdir_macros.png "Dialogfeld für das Bearbeiten von Makros")

Hinweis: Die Liste wird aufgefüllt, während der Eingabe. Drücken Sie nicht auf die **EINGABETASTE**.

Weitere Informationen über Makros und warum Sie diese anstatt hartcodierte Pfade möglichst verwenden sollten, finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

Eine Liste der häufig verwendeten Makros finden Sie unter [gängige Makros für Buildbefehle und-Eigenschaften](common-macros-for-build-commands-and-properties.md).

Sie können eigene Makros auf zwei Arten definieren:

- Legen Sie Umgebungsvariablen in einer Developer-Eingabeaufforderung fest. Alle Umgebungsvariablen werden als MSBuild-Eigenschaften oder -Makros behandelt.

- Definieren Sie Benutzermakros in einer PROPS-Datei. Weitere Informationen finden Sie unter [Property page macros (Makros für Eigenschaftenseiten)](../working-with-project-properties.md).

Weitere Informationen finden Sie in folgenden Blogbeiträgen: [VC++-Verzeichnisse](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [geerbte Eigenschaften und Eigenschaftenblätter](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), und [Visual Studio 2010 C++-Projekt-Aktualisierungshandbuch](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).

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

Sie können Projekteigenschaften für andere Benutzer oder Computer freigeben. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).
