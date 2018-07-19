---
title: Linkertoolfehler Lnk1104 | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2b832d4bceab88fbf3fbe8325a414669d11073c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302811"
---
# <a name="linker-tools-error-lnk1104"></a>Linkertoolfehler LNK1104

> Öffnen der Datei "*Filename*"

Der Linker konnte die angegebene Datei nicht geöffnet werden. Die häufigsten Ursachen für dieses Problem sind, dass die Datei verwendet wird oder von einem anderen Prozess gesperrt wurde, nicht vorhanden ist, kann nicht in einem der Linker sucht Verzeichnisse gefunden werden, oder Sie möglicherweise nicht über ausreichende Berechtigungen zum Zugriff auf die Datei. Weniger üblich, Sie möglicherweise nicht genügend Speicherplatz, die Datei ist möglicherweise zu groß, oder der Pfad zur Datei ist möglicherweise zu lang.

## <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen

Dieser Fehler kann auftreten, wenn der Linker versucht, eine Datei zum Lesen oder zum Schreiben zu öffnen. Die möglichen Ursachen einzugrenzen, zuerst überprüfen Sie welcher Art Datei ist, und verwenden Sie die folgenden Abschnitten zum Identifizieren und beheben Sie das spezifische Problem.

### <a name="cannot-open-your-app-or-its-pdb-file"></a>Die app oder die PDB-Datei kann nicht geöffnet werden.

Wenn der Dateiname der ausführbaren Datei ist das Projekt erstellt wurde, oder eine zugehörige PDB-Datei, die häufigste Ursache ist, dass die Anwendung bereits ausgeführt wird, wenn Sie versuchen, ihn neu erstellen oder in einem Debugger geladen wird. Um dieses Problem zu beheben, beenden Sie das Programm, und über den Debugger entladen Sie werden, bevor Sie es erneut erstellen. Wenn die app in einem anderen Programm geöffnet ist, z. B. eine Ressourcen-Editor, schließen Sie diese. In extremen Fällen müssen Sie die Task-Manager verwenden, um den Prozess zu beenden oder beenden und starten Sie Visual Studio neu.

Antivirusprogramme greifen oft vorübergehend blockieren, auf die neu erstellte Dateien, vor allem .exe und DLL ausführbare Dateien. Um dieses Problem zu beheben, versuchen Sie es Ausschließen von Ihrem Build Projektverzeichnisse von der Antivirenscanner.

### <a name="cannot-open-a-microsoft-library-file"></a>Eine Microsoft-Library-Datei kann nicht geöffnet werden.

Wenn die Datei, die nicht geöffnet werden kann eine der Standardbibliothek-Dateien, die von Microsoft bereitgestellt werden, z. B. kernel32.lib, ist möglicherweise Sie ein Projekt-Konfigurationsfehler oder ein Installationsfehler. Stellen Sie sicher, dass das Windows SDK installiert wurde, und wenn Ihr Projekt andere Microsoft-Bibliotheken wie MFC erforderlich sind, stellen Sie sicher, dass die MFC-Komponenten auch von der Visual Studio-Installer installiert wurden. Sie können das Installationsprogramm erneut aus, um optionale Komponenten zu einem beliebigen Zeitpunkt hinzufügen ausführen. Weitere Informationen finden Sie unter [Visual Studio ändern](/visualstudio/install/modify-visual-studio). Verwenden Sie die einzelnen Komponenten (Registerkarte) in das Installationsprogramm, um bestimmte Bibliotheken und SDKs auszuwählen.

Wenn Sie ein Projekt erstellen, die mit einer älteren Version von Visual Studio erstellt wurde, können die Plattformtoolset und Bibliotheken für diese Version nicht installiert. Wenn die Fehlermeldung für einen mit Versionsangabe Bibliotheksnamen, z. B. msvcr100.lib, ist dies wahrscheinlich die Ursache. Um dieses Problem zu beheben, haben Sie zwei Optionen: upgrade des Projekts, um die aktuellen-Plattformtoolset verwenden Sie installiert haben, oder installieren Sie das ältere Toolset und erstellen Sie das Projekt nicht geändert. Weitere Informationen finden Sie unter [Aktualisierung von Projekten aus früheren Versionen von Visual C++](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) und [verwenden systemeigene Festlegung von Zielversionen in Visual Studio zum Erstellen von Projekten alten](../../porting/use-native-multi-targeting.md).

Wenn dieser Fehler angezeigt wird, wenn Sie für eine neue Zielplattform oder Konfiguration erstellen, wird die Bibliotheken für dieses Projekt oder Plattformeigenschaften Toolset möglicherweise nicht installiert. Überprüfen Sie, ob die **Plattformtoolset** und **Windows SDK-Version** angegebenen, in der [Eigenschaftenseite Allgemein](../../ide/general-property-page-project.md) für das Projekt installiert sind, und überprüfen Sie, ob die erforderlichen Bibliotheken werden in der **Bibliotheksverzeichnisse** angegebenen, in der [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md) für Ihre Konfigurationseinstellungen. Es gibt separate Einstellungen für die Debug- und Retail-Konfigurationen als auch 32-Bit und 64-Bit-Konfigurationen, wenn Erstellung funktioniert, aber einen anderen einen Fehler verursacht, achten Sie also die Einstellungen richtig sind und die erforderlichen Tools und Bibliotheken für installiert sind alle Konfiguration, die Sie erstellen.

Wenn Sie Visual Studio-IDE verwenden, um ein Projekt zu erstellen, die von einem anderen Computer kopiert wurde, können die Installationspfade für Bibliotheken abweichen. Überprüfen der **Bibliotheksverzeichnisse** Eigenschaft auf die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md) für das Projekt und bei Bedarf zu aktualisieren. Um anzuzeigen, und bearbeiten die aktuellen Library-Pfade, die in der IDE festgelegt, wählen Sie das Dropdown-Steuerelement für die **Bibliotheksverzeichnisse** Eigenschaft, und wählen Sie **bearbeiten**. Die **Wert ausgewertet** Teil der **Bibliotheksverzeichnisse** Dialogfeld listet die aktuellen Pfade Bibliotheksdateien gesucht.

Dieser Fehler kann auch auftreten, wenn der Pfad zum Windows SDK veraltet ist. Wenn Sie eine Version des Windows SDK, die neuer ist als Ihre Version von Visual Studio installiert haben, stellen Sie sicher, dass die Pfade in angegeben die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md) werden aktualisiert, um das neue SDK übereinstimmen. Wenn Sie die Developer-Eingabeaufforderung verwenden, stellen Sie sicher, dass die Batchdatei, die die Umgebungsvariablen initialisiert für die neue SDK-Pfade aktualisiert wird. Dieses Problem kann vermieden werden, mithilfe der Visual Studio-Installer zum Installieren des aktualisierten SDKs.

### <a name="cannot-open-a-third-party-library-file"></a>Eine Drittanbieter-Bibliotheksdatei kann nicht geöffnet werden.

Es gibt einige häufige Ursachen für dieses Problem:

- Der Pfad zu Ihrer Bibliotheksdatei ist möglicherweise falsch, oder Sie möglicherweise nicht verfügen angegeben es an den Linker.

- Sie haben eine 32-Bit-Version der Bibliothek installiert, aber Sie erstellen für 64-Bit oder umgekehrt.

- Die Bibliothek möglicherweise Abhängigkeiten von anderen Bibliotheken, die nicht installiert werden.

Um ein Problem mit dem Pfad zu beheben, stellen Sie sicher, dass die LIB-Umgebungsvariable festgelegt ist, und alle Verzeichnisse für die Bibliotheken wie enthält, für jede Konfiguration, die Sie erstellen. In der IDE die LIB-Variable festgelegt ist, indem Sie die **Bibliotheksverzeichnisse** Eigenschaft auf die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md). Stellen Sie sicher, dass alle Verzeichnisse, die Bibliotheken enthalten, die Sie müssen, für jede Konfiguration, die Sie erstellen, hier aufgelistet sind.

Wenn Sie ein Bibliotheksverzeichnis angeben müssen, überschreibt eine standard-Bibliotheksverzeichnis, können Sie mithilfe der [/LIBPATH](../../build/reference/libpath-additional-libpath.md) Option in der Befehlszeile oder in der IDE, können Sie die **Zusätzliche Bibliotheksverzeichnisse** die Eigenschaft in der **Konfigurationseigenschaften > Linker > Allgemein** Eigenschaftenseite für das Projekt.

Stellen Sie sicher, dass Sie jede Version der Bibliothek installiert haben, müssen Sie für die Konfigurationen, die Sie erstellen. Erwägen Sie die [Vcpkg](../../vcpkg.md) Verwaltungsdienstprogramms zum Automatisieren der Installation und Setup für viele allgemeine Bibliotheken verpacken. Sofern möglich, empfiehlt es sich um eigene Kopien eines Drittanbieters-Bibliotheken zu erstellen, damit sind Sie sicher, dass alle lokalen Abhängigkeiten ist, die die Bibliotheken erfordern, und sie für die gleichen Konfigurationen wie das Projekt erstellt werden.

### <a name="cannot-open-a-file-built-by-your-project"></a>Eine vom Projekt erstellte Datei kann nicht geöffnet werden.

Dieser Fehler vermutlich angezeigt werden, wenn die Datei *Filename* , die von der Projektmappe erstellt wird, aber noch nicht vorhanden, wenn der Linker versucht, darauf zuzugreifen. Dies kann geschehen, wenn ein Projekt von einem anderen Projekt abhängig ist, aber die Projekte werden nicht in der richtigen Reihenfolge erstellt. Um dieses Problem zu beheben, stellen Sie sicher, dass Ihre Projektverweise auf im Projekt festgelegt werden, die die Datei verwendet, sodass die fehlende Datei erstellt wird, bevor er erforderlich ist. Weitere Informationen finden Sie unter [Hinzufügen von Verweisen in Visual C++-Projekten](../../ide/adding-references-in-visual-cpp-projects.md) und [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).

### <a name="cannot-open-file-cprogramobj"></a>Öffnen der Datei "" c: "\\Program.obj"

Wenn Sie diesen Fehler oder eine ähnliche Fehlermeldung im Zusammenhang mit einer unerwarteten OBJ-Datei im Stammverzeichnis des Laufwerks angezeigt wird, ist das Problem Befehlsbeispiel einen Bibliothekspfad aus, der nicht in doppelte Anführungszeichen umgeben ist.

Um dieses Problem für Befehlszeilenbuilds zu beheben, überprüfen Sie die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) Parameter, in der LIB-Umgebungsvariablen angegebenen Pfade und Pfade in der Befehlszeile angegebene option aus, und achten Sie darauf, verwenden Sie doppelte Anführungszeichen um alle Pfade die Leerzeichen enthalten.

Überprüfen Sie zur Behebung dieses Problems in der IDE die **Bibliotheksverzeichnisse** Eigenschaft auf die [Konfigurationseigenschaften > VC++-Verzeichnisse](../../ide/vcpp-directories-property-page.md) auf der Seite der **Zusätzliche Bibliotheksverzeichnisse** Eigenschaft in der **Konfigurationseigenschaften > Linker > Allgemein** auf der Seite und die **zusätzliche Abhängigkeiten** Eigenschaft in der **Konfiguration Eigenschaften > Linker > Eingabe** Eigenschaftenseite für das Projekt. Stellen Sie sicher, dass alle Verzeichnispfade, die Bibliotheken enthalten, die Sie benötigen, in doppelte Anführungszeichen umschlossen ist, bei Bedarf.

### <a name="other-common-issues"></a>Andere häufig auftretende Probleme

Dieser Fehler kann auftreten, wenn der Bibliotheksdateiname oder Pfad, an den Linker an, in der Befehlszeile oder in angegeben einem [#pragma-Kommentar (Lib, "Library_name")](../../preprocessor/comment-c-cpp.md) Richtlinie ist falsch, oder der Pfad weist eine ungültige Laufwerksangabe. Überprüfen Sie die Rechtschreibung und der Dateierweiterung ein, und stellen Sie sicher, dass die Datei am angegebenen Speicherort vorhanden ist.

Möglicherweise ist die Datei in einem anderen Programm geöffnet, und der Linker kann nicht in sie schreiben. Oft blockiert Antivirusprogramme vorübergehend den Zugriff auf die neu erstellte Dateien. Um dieses Problem zu beheben, versuchen Sie es Ausschließen von Ihrem Build Projektverzeichnisse von der Antivirenscanner.

Wenn Sie eine parallele Buildoption verwendet werden, ist es möglich, dass Visual Studio die Datei in einem anderen Thread gesperrt hat. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie nicht die gleichen Codeobjekt oder eine Bibliothek in mehreren Projekten erstellen und Sie Buildabhängigkeiten oder Projektverweise verwenden, um in Ihrem Projekt erstellten Binärdateien zu übernehmen.

Beim Angeben von einzelnen Bibliotheken in der **zusätzliche Abhängigkeiten** Eigenschaft direkt Leerzeichen verwenden, um den Bibliotheksnamen, keine Kommas oder Semikolons trennen. Bei Verwendung der **bearbeiten** Menüelement zum Öffnen der **zusätzliche Abhängigkeiten** (Dialogfeld), Zeilenumbrüche verwenden, um den Namen, nicht durch Kommas, Semikolons oder Leerzeichen zu trennen. Bucheintrag auch verwenden, bei der Angabe von Library-Pfade in der **Bibliotheksverzeichnisse** und **Zusätzliche Bibliotheksverzeichnisse** Dialogfelder.

Dieser Fehler vermutlich angezeigt Wenn der Pfad für *Filename* wird auf mehr als 260 Zeichen erweitert. Ändern Sie die Namen oder ordnen Sie die Verzeichnisstruktur neu an, bei Bedarf, um die Pfade zu den erforderlichen Dateien zu kürzen.

Dieser Fehler kann auftreten, weil die Datei zu groß ist. Objekt oder Bibliotheken Dateien mehr als ein Gigabyte groß für den 32-Bit-Linker möglicherweise Probleme verursacht. Eine mögliche Lösung für dieses Problem ist die 64-Bit-Toolset verwendet. Weitere Informationen dazu in der Befehlszeile finden Sie unter [Vorgehensweise: Aktivieren Sie eine 64-Bit-Visual C++-Toolsets in der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). Informationen dazu in der IDE finden Sie unter [mithilfe von MSBuild mit 64-Bit-Compiler und Tools](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) und diesen Beitrag Stack Overflow: [wie Sie Visual Studio verwenden, die amd64 native-toolkette](http://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).

Dieser Fehler kann auftreten, haben Zugriff auf Unzureichende Dateiberechtigungen *Filename*. Dies kann geschehen, wenn Sie einem normalen Benutzerkonto und der Versuch Bibliotheksdateien in Verzeichnissen des geschützten Systems Zugriff auf, verwenden oder von anderen Benutzern, die ihre ursprüngliche berechtigt kopierte Dateien festgelegt. Um dieses Problem zu beheben, verschieben Sie die Datei in einem beschreibbaren Projektverzeichnis. Wenn die Datei in einem beschreibbaren Verzeichnis jedoch berechtigt ist nicht zugegriffen werden kann, können Sie verwenden eine Eingabeaufforderung mit Administratorrechten aus und führen Sie den Befehl takeown.exe des Besitzes der Datei.

Der Fehler kann auftreten, wenn Sie nicht über genügend Speicherplatz verfügen. Der Linker verwendet im verschiedenen Fällen temporäre Dateien. Auch wenn Sie über ausreichend Speicherplatz verfügen, kann eine sehr umfangreiche Verknüpfung ausschöpfen oder fragmentieren den verfügbare Speicherplatz. Erwägen Sie die [/OPT (Optimierungen)](../../build/reference/opt-optimizations.md) Option; auf diese Weise transitive COMDAT-Eliminierung liest alle Objektdateien mehrfach.

Wenn die *Filename* heißt LNK *"nnn"*, also einen vom Linker für eine temporäre Datei generierten Dateinamen, in der TMP-Umgebungsvariablen angegebene Verzeichnis ist möglicherweise nicht vorhanden oder ist möglicherweise mehr als ein Verzeichnis an. für die TMP-Umgebungsvariable angegeben. Nur ein Verzeichnispfad sollte für die TMP-Umgebungsvariable angegeben werden.
