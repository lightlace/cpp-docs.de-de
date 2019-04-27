---
title: Linkertoolfehler LNK1104
ms.date: 05/17/2017
f1_keywords:
- LNK1104
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
ms.openlocfilehash: eadeeb7ac19e3975a37a1364502b33400018cb05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255512"
---
# <a name="linker-tools-error-lnk1104"></a>Linkertoolfehler LNK1104

> Datei kann nicht geöffnet werden kann '*Filename*"

Der Linker konnte die angegebene Datei nicht geöffnet werden. Die häufigsten Ursachen dieses Problems sind, dass die Datei verwendet wird oder von einem anderen Prozess gesperrt, nicht vorhanden ist, wurde nicht gefunden in eines der Verzeichnisse, die der Linker sucht, oder Sie können keine ausreichenden Berechtigungen zum Zugriff auf die Datei. Weniger üblich, Sie möglicherweise nicht genügend Speicherplatz ausgeführt haben, die Datei ist möglicherweise zu groß oder der Pfad zu der Datei ist möglicherweise zu lang.

## <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen

Dieser Fehler kann auftreten, wenn der Linker, zum Öffnen einer Datei oder zum Lesen als auch zum Schreiben versucht. Die möglichen Ursachen einzugrenzen, zuerst überprüfen Sie welche Art von Datei dies stammt, und verwenden Sie in den folgenden Abschnitten, um zu erkennen und beheben Sie das spezifische Problem.

### <a name="cannot-open-your-app-or-its-pdb-file"></a>Ihre app oder die PDB-Datei kann nicht geöffnet werden.

Wenn der Dateiname der ausführbaren Datei ist das Projekt erstellt wurde, oder eine zugehörige PDB-Datei, die häufigste Ursache ist, dass Ihre Anwendung bereits ausgeführt wird, wenn Sie versuchen, ihn neu zu erstellen, oder es in einem Debugger geladen wird. Um dieses Problem zu beheben, das Programm aus, und Entladen der Debugger vor dem Erstellen es noch mal. Wenn die app in einem anderen Programm geöffnet ist z. B. ein Ressourcen-Editor, schließen Sie sie. In Extremfällen müssen Sie die Task-Manager verwenden, um den Prozess zu beenden oder zu beenden und starten Sie Visual Studio.

Antivirenprogrammen häufig vorübergehend Block für neu erstellte Dateien, insbesondere .exe und .dll ausführbare auf Dateien zugreifen. Um dieses Problem zu beheben, versuchen Sie es mit Ausnahme Ihrer Projekt-Build-Verzeichnisse aus der Virenscanner.

### <a name="cannot-open-a-microsoft-library-file"></a>Eine Microsoft-Library-Datei kann nicht geöffnet werden.

Wenn die Datei, die nicht geöffnet werden kann, die eine der Dateien von Microsoft bereitgestellt werden, z. B. kernel32.lib, standard-Bibliothek ist möglicherweise Sie ein Projekt-Konfigurationsfehler oder ein Installationsfehler. Stellen Sie sicher, dass das Windows SDK installiert wurde, und wenn Ihr Projekt mit anderen Microsoft-Bibliotheken wie MFC erforderlich sind, stellen Sie sicher, dass die MFC-Komponenten auch von Visual Studio-Installer installiert wurden. Sie können das Installationsprogramm erneut aus, um optionale Komponenten zu einem beliebigen Zeitpunkt hinzufügen, ausführen. Weitere Informationen finden Sie unter [Ändern von Visual Studio](/visualstudio/install/modify-visual-studio). Verwenden Sie die Registerkarte "einzelne Komponenten" im Installer, um bestimmte Bibliotheken und SDKs auszuwählen.

Wenn Sie ein Projekt erstellen, die mit einer älteren Version von Visual Studio erstellt wurde, können das Plattformtoolset und -Bibliotheken für diese Version nicht installiert. Wenn die Fehlermeldung für den Namen einer mit versionsverwaltung durch das Bibliothek an, wie z. B. msvcr100.lib, tritt auf, ist dies wahrscheinlich die Ursache. Um dieses Problem zu beheben, haben Sie zwei Möglichkeiten: Sie können das Projekt, um dem aktuellen Plattformtoolset verwenden, müssen installiert sein, aktualisieren oder Sie älteren Toolsets installieren können, und erstellen Sie das Projekt, das unverändert. Weitere Informationen finden Sie unter [Aktualisieren von Projekten von früheren Versionen von Visual C++](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) und [verwenden native Festlegung von Zielversionen in Visual Studio, um alte Projekte zu erstellen](../../porting/use-native-multi-targeting.md).

Wenn Sie dieser Fehler angezeigt, wenn Sie für eine neue Zielplattform oder die Konfiguration erstellen, können die Bibliotheken für dieses Projekt Benutzerkonfigurations- oder Plattformprobleme-Toolset nicht installiert. Überprüfen Sie, ob die **Plattformtoolset** und **Windows SDK-Version** Angabe in der [Eigenschaftenseite "Allgemein"](../../build/reference/general-property-page-project.md) für Ihr Projekt installiert sind, und überprüfen Sie, ob die erforderlichen Bibliotheken stehen in der **Bibliotheksverzeichnisse** Angabe in der [VC++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md) für Ihre Konfigurationseinstellungen. Es gibt separate Einstellungen für Debuggen und Retail-Konfigurationen als auch 32-Bit- und 64-Bit-Konfigurationen, also wenn eine funktioniert jedoch eine andere einen Fehler verursacht, stellen sicher, dass die Einstellungen richtig sind und die erforderlichen Tools und Bibliotheken werden installiert, für jede die Konfiguration, die Sie erstellen.

Wenn Sie den Visual Studio-IDE verwenden, um ein Projekt zu erstellen, die von einem anderen Computer kopiert wurde, können die Installationspfade für Bibliotheken abweichen. Überprüfen Sie die **Bibliotheksverzeichnisse** Eigenschaft für die [VC++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md) für das Projekt und bei Bedarf aktualisieren. Um anzuzeigen, und bearbeiten die aktuellen Library-Pfade, die in der IDE festzulegen, wählen Sie das Dropdown-Steuerelement für die **Bibliotheksverzeichnisse** Eigenschaft, und wählen Sie **bearbeiten**. Die **Wert ausgewertet** Teil der **Bibliotheksverzeichnisse** Dialogfeld listet die aktuellen Pfade, die nach Bibliotheksdateien gesucht.

Dieser Fehler kann auch auftreten, wenn der Pfad zum Windows SDK nicht mehr aktuell ist. Wenn Sie eine Version des Windows SDK, die neuer ist als Ihre Version von Visual Studio installiert haben, stellen Sie sicher, dass die Pfade in angegeben die [VC++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md) werden aktualisiert, um das neue SDK entsprechen. Wenn Sie die Developer-Eingabeaufforderung verwenden, stellen Sie sicher, dass die Batchdatei, die die Umgebungsvariablen initialisiert für die neue SDK-Pfade aktualisiert wird. Dieses Problem kann vermieden werden, mithilfe von Visual Studio-Installer zum Installieren der aktualisierten SDKs.

### <a name="cannot-open-a-third-party-library-file"></a>Eine Drittanbieter-Bibliothek-Datei kann nicht geöffnet werden.

Es gibt einige häufige Ursachen für dieses Problem:

- Der Pfad zu Ihrer Bibliotheksdatei ist möglicherweise falsch, oder Sie möglicherweise nicht haben es dem Linker angegeben.

- Sie haben eine 32-Bit-Version der Bibliothek installiert, aber erstellen Sie für 64-Bit oder umgekehrt.

- Die Bibliothek möglicherweise Abhängigkeiten von anderen Bibliotheken, die nicht installiert werden.

Um ein Problem mit dem Pfad zu beheben, stellen Sie sicher, dass die LIB-Umgebungsvariable festgelegt ist, und enthält alle Verzeichnisse für die Bibliotheken, die Sie für jede Konfiguration verwenden, die Sie erstellen. In der IDE die LIB-Variable festgelegt ist, indem die **Bibliotheksverzeichnisse** Eigenschaft für die [VC++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md). Stellen Sie sicher, dass alle Verzeichnisse, die die Bibliotheken enthalten, die Sie benötigen für jede Konfiguration, die Sie erstellen, hier aufgeführt werden.

Wenn Sie ein Bibliotheksverzeichnis angeben müssen, überschreibt es sich um ein Verzeichnis für die standard-Bibliothek, können Sie verwenden die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) Option in der Befehlszeile oder in der IDE, können Sie die **Zusätzliche Bibliotheksverzeichnisse** Eigenschaft in der **Konfigurationseigenschaften > Linker > Allgemein** Eigenschaftenseite für das Projekt.

Stellen Sie sicher, dass Sie jede Version der Bibliothek installiert haben, müssen Sie die Konfigurationen, die Sie erstellen. Erwägen Sie die Verwendung der [Vcpkg](../../vcpkg.md) -Hilfsprogramm zum Automatisieren der Installation und Setup für viele allgemeine Bibliotheken. Sofern möglich, empfiehlt es sich um Ihre eigenen Kopien von Drittanbieter-Bibliotheken, zu erstellen, damit Sie alle lokalen Abhängigkeiten verfügen, in denen die Bibliotheken, und diese werden für die gleichen Konfigurationen wie Ihr Projekt erstellt werden.

### <a name="cannot-open-a-file-built-by-your-project"></a>Eine vom Projekt erstellte Datei kann nicht geöffnet werden.

Dieser Fehler möglicherweise angezeigt, wenn die Datei *Filename* wird Ihrer Projektmappe erstellt, aber noch nicht vorhanden, wenn der Linker versucht, darauf zuzugreifen. Dies kann passieren, wenn ein Projekt, die von einem anderen Projekt abhängig ist, aber die Projekte werden nicht in der richtigen Reihenfolge erstellt. Um dieses Problem zu beheben, stellen Sie sicher, dass Ihre Projektverweise auf im Projekt festgelegt werden, die die Datei verwendet werden, damit die fehlende Datei erstellt wird, bevor es erforderlich ist. Weitere Informationen finden Sie unter [Hinzufügen von Verweisen in Visual C++-Projekten](../../build/adding-references-in-visual-cpp-projects.md) und [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).

### <a name="cannot-open-file-cprogramobj"></a>Datei kann nicht geöffnet werden kann ' "c:"\\Program.obj "

Wenn dieser Fehler oder eine ähnliche Fehlermeldung, die im Zusammenhang mit einer unerwarteten OBJ-Datei im Stammverzeichnis des Laufwerks angezeigt wird, ist das Problem mit großer Wahrscheinlichkeit einen Bibliothekspfad aus, der nicht in doppelte Anführungszeichen umschlossen wird.

Um dieses Problem für Befehlszeilenbuilds zu beheben, überprüfen Sie die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) option Parameter, in der LIB-Umgebungsvariablen angegebenen Pfade und Pfade in der Befehlszeile angegeben, und stellen Sie sicher, dass doppelte Anführungszeichen um Pfade zu verwenden die Leerzeichen enthalten.

Um dieses Problem in der IDE zu beheben, überprüfen Sie die **Bibliotheksverzeichnisse** Eigenschaft für die [Konfigurationseigenschaften > VC++-Verzeichnisse](../../build/reference/vcpp-directories-property-page.md) auf der Seite die **Zusätzliche Bibliotheksverzeichnisse** -Eigenschaft in der **Konfigurationseigenschaften > Linker > Allgemein** auf der Seite und die **zusätzliche Abhängigkeiten** -Eigenschaft in der **Konfiguration Eigenschaften > Linker > Eingabe** Eigenschaftenseite für das Projekt. Stellen Sie sicher, dass alle die Verzeichnispfade, die die Bibliotheken enthalten, die Sie benötigen in doppelte Anführungszeichen umschlossen werden bei Bedarf.

### <a name="other-common-issues"></a>Andere allgemeine Probleme

Dieser Fehler kann auftreten, wenn für den Linker an, in der Befehlszeile oder in der Bibliotheksdateiname oder Pfad angegeben ein [#pragma Comment ("Lib", "Library_name" ")](../../preprocessor/comment-c-cpp.md) Richtlinie ist falsch, oder der Pfad weist eine ungültige Laufwerksangabe. Überprüfen Sie die Rechtschreibung und die Dateierweiterung ein, und stellen Sie sicher, dass die Datei am angegebenen Speicherort vorhanden ist.

Möglicherweise ist die Datei in einem anderen Programm geöffnet, und der Linker kann nicht in sie schreiben. Oft blockiert Antivirusprogramme vorübergehend Zugriff auf die neu erstellte Dateien. Um dieses Problem zu beheben, versuchen Sie es mit Ausnahme Ihrer Projekt-Build-Verzeichnisse aus der Virenscanner.

Wenn Sie eine parallele projekterstellung-Option verwenden, ist es möglich, dass Visual Studio die Datei auf einem anderen Thread gesperrt hat. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie nicht der gleiche Codeobjekt oder die Bibliothek in mehreren Projekten erstellen und Sie Buildabhängigkeiten oder Projektverweise verwenden, um die erstellten Binärdateien in Ihrem Projekt zu übernehmen.

Beim Angeben von einzelnen Bibliotheken in der **zusätzliche Abhängigkeiten** Eigenschaft direkt Leerzeichen verwenden, um die Namen von Typbibliotheken, nicht Kommas oder Semikolons trennen. Bei Verwendung der **bearbeiten** Menüelement zum Öffnen der **zusätzliche Abhängigkeiten** Dialogfeld Zeilenumbrüche verwenden, um den Namen, nicht durch Kommas, Semikolons oder Leerzeichen zu trennen. Zeilenumbrüche auch verwenden, bei der Angabe von Library-Pfade in der **Bibliotheksverzeichnisse** und **Zusätzliche Bibliotheksverzeichnisse** Dialogfelder.

Dieser Fehler wird möglicherweise angezeigt bei den Pfad für *Filename* erweitert, dass es mehr als 260 Zeichen lang sein. Ändern Sie die Namen oder ordnen Sie die Verzeichnisstruktur neu an, falls erforderlich, um die Pfade zu den erforderlichen Dateien zu kürzen.

Dieser Fehler kann auftreten, da die Datei zu groß ist. Bibliotheken oder die Objekt-Dateien mehr als ein Gigabyte groß für den 32-Bit-Linker möglicherweise Probleme verursacht. Eine mögliche Lösung für dieses Problem ist die Verwendung der 64-Bit-Toolsets. Weitere Informationen dazu, wie Sie hierzu in der Befehlszeile finden Sie unter [Vorgehensweise: Aktivieren eines 64-Bit-Visual C++-Toolsets in der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). Informationen dazu, wie dies in der IDE ausführen, finden Sie unter [Verwenden von MSBuild mit 64-Bit-Compiler und Tools](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) und Stack Overflow-Beitrag: [Wie Sie Visual Studio verwendet die systemeigenen amd64-toolkette](http://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).

Dieser Fehler kann auftreten, wenn Sie nicht genügend Berechtigungen zum Zugriff auf haben *Filename*. Dies kann auftreten, wenn Sie einem normalen Benutzerkonto und ein Versuch Bibliotheksdateien in geschützte Verzeichnisse zugreifen, oder verwenden die Dateien kopiert, die von anderen Benutzern, die die ursprünglichen Berechtigungen festlegen. Um dieses Problem zu beheben, verschieben Sie die Datei zu einem beschreibbaren Projektverzeichnis. Wenn diese Datei befindet sich in einem Verzeichnis geschrieben, aber berechtigt ist, können Sie verwenden eine Administrator-Eingabeaufforderung und führen den takeown.exe-Befehl aus, um den Besitzer der Datei werden.

Der Fehler kann auftreten, wenn Sie nicht über genügend Speicherplatz verfügen. Der Linker verwendet im verschiedenen Fällen temporäre Dateien. Auch wenn Sie über ausreichend Speicherplatz verfügen, kann eine sehr umfangreiche Verknüpfung erschöpft sind oder einem fragment den verfügbare Speicherplatz. Erwägen Sie die Verwendung der [/OPT (Optimierungen)](../../build/reference/opt-optimizations.md) Option, die Ausführung transitive COMDAT-Eliminierung von Duplikaten liest alle Objektdateien mehrfach.

Wenn die *Filename* heißt LNK*Nnn*, dies ist ein Dateiname die vom Linker für eine temporäre Datei, in der TMP-Umgebungsvariablen angegebene Verzeichnis möglicherweise nicht vorhanden oder kann mehr als ein Verzeichnis sein. für die TMP-Umgebungsvariable angegeben. Nur ein Verzeichnispfad sollte für die TMP-Umgebungsvariable angegeben werden.
