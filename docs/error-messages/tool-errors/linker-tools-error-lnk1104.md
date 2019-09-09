---
title: Linkertoolfehler LNK1104
ms.date: 09/06/2019
f1_keywords:
- LNK1104
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
ms.openlocfilehash: f3effd9054954a90f69c5b18d8f099e6d705d9a3
ms.sourcegitcommit: 7babce70714242cf498ca811eec3695fad3abd03
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2019
ms.locfileid: "70808840"
---
# <a name="linker-tools-error-lnk1104"></a>Linkertoolfehler LNK1104

> Datei "*Dateiname*" kann nicht geöffnet werden

Der Linker konnte die angegebene Datei nicht öffnen. Die häufigsten Gründe für dieses Problem sind, dass die Datei in Gebrauch ist oder von einem anderen Prozess gesperrt ist. Es ist auch möglich, dass die Datei nicht vorhanden ist oder nicht in einem der Verzeichnisse gefunden werden kann, die der Linker durchsucht. Oder Sie verfügen möglicherweise nicht über ausreichende Berechtigungen, um auf die Datei zuzugreifen. Weniger häufig ist möglicherweise nicht genügend Speicherplatz vorhanden, die Datei ist möglicherweise zu groß, oder der Pfad zur Datei ist zu lang.

## <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen

Dieser Fehler kann auftreten, wenn der Linker versucht, eine Datei zum Lesen oder zum Schreiben zu öffnen. Um die möglichen Ursachen einzugrenzen, prüfen Sie zunächst, welche Art von Datei es ist. Verwenden Sie dann die folgenden Abschnitte, um das jeweilige Problem zu identifizieren und zu beheben.

### <a name="cant-open-your-app-or-its-pdb-file"></a>Ihre APP oder die zugehörige PDB-Datei kann nicht geöffnet werden.

Wenn der Dateiname die ausführbare Datei ist, die Ihr Projekt erstellt, oder eine zugehörige PDB-Datei, ist die häufigste Ursache, dass Ihre Anwendung bereits ausgeführt wird, wenn Sie versuchen, Sie neu zu erstellen, oder Sie wird in einem Debugger geladen. Um dieses Problem zu beheben, müssen Sie das Programm vor dem erneuten Aufbau aus dem Debugger entfernen. Wenn die app in einem anderen Programm, z. b. einem Ressourcen-Editor, geöffnet ist, schließen Sie Sie. In Extremfällen müssen Sie möglicherweise den Task-Manager verwenden, um den Prozess zu beenden oder Visual Studio zu beenden und neu zu starten.

Antivirenprogramme blockieren häufig vorübergehend den Zugriff auf neu erstellte Dateien, insbesondere auf ausführbare EXE-und dll-Dateien. Um dieses Problem zu beheben, versuchen Sie, die projektbuildverzeichnisse aus dem Antivirenscanner auszuschließen.

### <a name="cant-open-a-microsoft-library-file"></a>Eine Microsoft-Bibliotheksdatei kann nicht geöffnet werden.

Wenn die Datei, die nicht geöffnet werden kann, eine der Standard Bibliotheksdateien ist, die von Microsoft bereitgestellt werden, z. b. Kernel32. lib, liegt möglicherweise ein Projekt Konfigurationsfehler oder ein Installationsfehler vor. Vergewissern Sie sich, dass die Windows SDK installiert wurde, und wenn Ihr Projekt andere Microsoft-Bibliotheken wie MFC erfordert, stellen Sie sicher, dass die MFC-Komponenten auch vom Visual Studio-Installer installiert wurden. Sie können das Installationsprogramm erneut ausführen, um jederzeit optionale Komponenten hinzuzufügen. Weitere Informationen finden Sie unter [Ändern von Visual Studio](/visualstudio/install/modify-visual-studio). Verwenden Sie die Registerkarte einzelne Komponenten im Installationsprogramm, um bestimmte Bibliotheken und sdert auszuwählen.

Für universelle Windows-Apps (UWP)-Apps oder-Komponenten gibt es keine von Spectre abgeminderten Bibliotheken. Wenn im Fehlerbericht die Datei " *vccorlib. lib* " erwähnt wird, haben Sie möglicherweise [/Qspectre](../../build/reference/qspectre.md) in einem UWP-Projekt aktiviert. Deaktivieren Sie die **/Qspectre** -Compileroption, um dieses Problem zu beheben. Ändern Sie in Visual Studio die **Eigenschaft Spectre-Entschärfung** , die auf der Seite **C/C++Code-**  > Generierung des Dialog Felds **Eigenschaften Seiten** des Projekts enthalten ist.

Wenn Sie ein Projekt erstellen, das mit einer älteren Version von Visual Studio erstellt wurde, sind das Platt Form Toolset und die Bibliotheken für diese Version möglicherweise nicht installiert. Wenn die Fehlermeldung für einen Bibliotheksnamen mit Versions Angabe (z. b. "msvcr100. lib) auftritt, ist dies wahrscheinlich die Ursache. Um dieses Problem zu beheben, haben Sie zwei Möglichkeiten: Sie können das Projekt aktualisieren, um das aktuelle Platt Form Toolset zu verwenden, oder Sie können das ältere Toolset installieren und das Projekt unverändert erstellen. Weitere Informationen finden Sie unter [Aktualisieren von Projekten aus früheren Versionen von C++ Visual](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) Studio, und [verwenden Sie die native Ziel Versionen in Visual Studio, um alte Projekte zu erstellen](../../porting/use-native-multi-targeting.md).

Wenn dieser Fehler angezeigt wird, wenn Sie für eine neue Zielplattform oder-Konfiguration erstellen, sind die Bibliotheken für diese Projekt Konfiguration oder dieses Platt Form Toolset möglicherweise nicht installiert. Stellen Sie sicher, dass das **Platt Form Toolset** und die **Windows SDK Version** , die auf der [Eigenschaften Seite Allgemein](../../build/reference/general-property-page-project.md) für Ihr Projekt angegeben sind, installiert sind, und überprüfen Sie, **ob die erforderlichen Bibliotheken in den in** die [Eigenschaften Seite für VC + +-Verzeichnisse](../../build/reference/vcpp-directories-property-page.md) für Ihre Konfigurationseinstellungen. Es gibt separate Einstellungen für Debug-und Einzelhandels Konfigurationen sowie 32-Bit-und 64-Bit-Konfigurationen. Wenn also ein Build funktioniert, aber ein anderer einen Fehler verursacht, stellen Sie sicher, dass die Einstellungen richtig sind und dass die erforderlichen Tools und Bibliotheken für alle installiert werden. Konfiguration, die Sie erstellen.

Wenn Sie die Visual Studio-IDE verwenden, um ein Projekt zu erstellen, das von einem anderen Computer kopiert wurde, können sich die Installations Pfade für Bibliotheken unterscheiden. Überprüfen Sie die Eigenschaft **Bibliotheks Verzeichnisse** auf der [Eigenschaften Seite für VC + +-Verzeichnisse](../../build/reference/vcpp-directories-property-page.md) für das Projekt, und aktualisieren Sie Sie bei Bedarf. Um die in der IDE festgelegten aktuellen Bibliothekspfade anzuzeigen und zu bearbeiten, wählen Sie das Dropdown-Steuerelement für die Eigenschaft **Bibliotheks Verzeichnisse** aus, und wählen Sie **Bearbeiten**aus. Im Abschnitt **ausgewerteter Wert** des Dialog Felds **Bibliotheks Verzeichnisse** werden die aktuellen Pfade aufgelistet, die nach Bibliotheksdateien durchsucht werden.

Dieser Fehler kann auch auftreten, wenn der Pfad zum Windows SDK veraltet ist. Wenn Sie eine Version der Windows SDK installiert haben, die neuer als die Version von Visual Studio ist, stellen Sie sicher, dass die auf der [Eigenschaften Seite "VC + +-Verzeichnisse](../../build/reference/vcpp-directories-property-page.md) " angegebenen Pfade entsprechend dem neuen SDK aktualisiert werden. Wenn Sie die Developer-Eingabeaufforderung verwenden, stellen Sie sicher, dass die Batchdatei, mit der die Umgebungsvariablen initialisiert werden, für die neuen SDK-Pfade aktualisiert wird. Dieses Problem kann vermieden werden, indem Sie mithilfe des Visual Studio-Installers aktualisierte sdche installieren.

### <a name="cannot-open-a-third-party-library-file"></a>Die Bibliotheksdatei eines Drittanbieters kann nicht geöffnet werden.

Es gibt verschiedene Häufige Gründe für dieses Problem:

- Möglicherweise ist der Pfad zu ihrer Bibliotheksdatei falsch, oder Sie haben ihn möglicherweise nicht für den Linker angegeben.

- Möglicherweise haben Sie eine 32-Bit-Version der Bibliothek installiert, aber Sie bauen für 64 Bits oder umgekehrt.

- Die Bibliothek kann Abhängigkeiten von anderen Bibliotheken aufweisen, die nicht installiert sind.

Vergewissern Sie sich, dass die lib-Umgebungsvariable festgelegt ist und alle Verzeichnisse für die von Ihnen verwendeten Bibliotheken für jede Konfiguration enthält, die Sie erstellen, um ein Pfad Problem zu beheben. In der IDE wird die LIB-Variable von der Eigenschaft **Bibliotheks Verzeichnisse** auf der [Eigenschaften Seite für VC + +-Verzeichnisse](../../build/reference/vcpp-directories-property-page.md)festgelegt. Stellen Sie sicher, dass alle Verzeichnisse, die die benötigten Bibliotheken enthalten, für jede Konfiguration, die Sie erstellen, hier aufgeführt sind.

Wenn Sie ein Bibliotheksverzeichnis angeben müssen, das ein Standard Bibliotheksverzeichnis überschreibt, können Sie die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) -Option in der Befehlszeile oder in der IDE verwenden, um die Eigenschaft **zusätzliche Bibliotheks Verzeichnisse** in den Konfigurations Eigenschaften zu verwenden.  **> Linker >** Eigenschaften Seite Allgemein für Ihr Projekt.

Stellen Sie sicher, dass Sie jede Version der Bibliothek installiert haben, die Sie für die von Ihnen Erstellungs Konfigurationen benötigen. Verwenden Sie ggf. das [vcpkg](../../vcpkg.md) -Paket Verwaltungs Hilfsprogramm, um die Installation und Einrichtung für viele gängige Bibliotheken zu automatisieren. Wenn dies möglich ist, sollten Sie Ihre eigenen Kopien von Bibliotheken von Drittanbietern erstellen, damit Sie sicher sind, dass Sie über alle lokalen Abhängigkeiten verfügen, die für die Bibliotheken erforderlich sind, und für dieselben Konfigurationen wie Ihr Projekt erstellt werden.

### <a name="cannot-open-a-file-built-by-your-project"></a>Eine vom Projekt erstellter Datei kann nicht geöffnet werden.

Dieser Fehler wird möglicherweise angezeigt, wenn der Datei *Dateiname* von der Projekt Mappe erstellt wird, aber noch nicht vorhanden ist, wenn der Linker versucht, darauf zuzugreifen. Dies kann vorkommen, wenn ein Projekt von einem anderen Projekt abhängig ist, die Projekte jedoch nicht in der richtigen Reihenfolge erstellt werden. Um dieses Problem zu beheben, stellen Sie sicher, dass die Projekt Verweise im Projekt festgelegt sind, das die Datei verwendet, damit die fehlende Datei erstellt wird, bevor Sie erforderlich ist. Weitere Informationen finden Sie unter [Hinzufügen von Verweisen in C++ Visual Studio-Projekten](../../build/adding-references-in-visual-cpp-projects.md) und [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).

### <a name="cannot-open-file-cprogramobj"></a>Die Datei "C:\\Program. obj" kann nicht geöffnet werden.

Wenn dieser Fehler oder ein ähnlicher Fehler wie eine unerwartete obj-Datei im Stammverzeichnis des Laufwerks angezeigt wird, ist das Problem fast sicherlich ein Bibliotheks Pfad, der nicht in doppelte Anführungszeichen eingeschlossen ist.

Um dieses Problem bei Befehlszeilenbuilds zu beheben, überprüfen Sie die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) -Optionsparameter, die in der LIB-Umgebungsvariablen angegebenen Pfade und die in der Befehlszeile angegebenen Pfade, und stellen Sie sicher, dass Sie doppelte Anführungszeichen für alle Pfade verwenden, die Leerzeichen enthalten.

Um dieses Problem in der IDE zu beheben, überprüfen Sie die Eigenschaft **Bibliotheks Verzeichnisse** auf der Eigenschaften Seite " [Konfigurations Eigenschaften > VC + +-Verzeichnisse](../../build/reference/vcpp-directories-property-page.md) ", die Eigenschaft " **zusätzliche Bibliotheks Verzeichnisse** " im **Konfigurations Eigenschaften > Linker >** Eigenschaften Seite Allgemein und der Eigenschaft **Zusätzliche Abhängigkeiten** auf der **Eigenschaften Seite Konfigurations Eigenschaften > Linker > Eingabe** für Ihr Projekt. Stellen Sie sicher, dass alle Verzeichnispfade, die die benötigten Bibliotheken enthalten, bei Bedarf in doppelte Anführungszeichen eingeschlossen werden.

### <a name="other-common-issues"></a>Weitere häufige Probleme

Dieser Fehler kann auftreten, wenn der Dateiname oder der Pfad der Bibliothek, der für den Linker in der Befehlszeile oder in einer #pragma Kommentar-Direktive [(lib, "library_name")](../../preprocessor/comment-c-cpp.md) angegeben ist, nicht korrekt ist oder der Pfad eine ungültige Laufwerk Spezifikation aufweist. Überprüfen Sie die Rechtschreibung und die Dateierweiterung, und vergewissern Sie sich, dass die Datei am angegebenen Speicherort vorhanden ist

Möglicherweise ist die Datei in einem anderen Programm geöffnet, und der Linker kann nicht in sie schreiben. Antivirenprogramme blockieren den Zugriff auf neu erstellte Dateien häufig vorübergehend. Um dieses Problem zu beheben, versuchen Sie, die projektbuildverzeichnisse aus dem Antivirenscanner auszuschließen.

Wenn Sie eine parallele Buildoption verwenden, ist es möglich, dass Visual Studio die Datei auf einem anderen Thread gesperrt hat. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie nicht das gleiche Code Objekt oder die gleiche Bibliothek in mehreren Projekten erstellen und dass Sie Buildabhängigkeiten oder Projekt Verweise verwenden, um die erstellten Binärdateien in Ihrem Projekt zu übernehmen.

Wenn Sie einzelne Bibliotheken direkt in der Eigenschaft **Zusätzliche Abhängigkeiten** angeben, verwenden Sie Leerzeichen, um die Bibliotheksnamen zu trennen, nicht Kommas oder Semikolons. Wenn Sie das Menü Element **Bearbeiten** verwenden, um das Dialogfeld **Zusätzliche Abhängigkeiten** zu öffnen, verwenden Sie Zeilenumbrüche, um die Namen, nicht Kommas, Semikolons oder Leerzeichen zu trennen. Verwenden Sie auch Zeilenumbrüche, wenn Sie Bibliothekspfade in den Dialogfeldern **Bibliotheks Verzeichnisse** und **zusätzliche Bibliotheks Verzeichnisse** angeben.

Dieser Fehler wird möglicherweise angezeigt, wenn der Pfad für *Dateiname* auf mehr als 260 Zeichen erweitert wird. Ändern Sie die Namen, oder ordnen Sie die Verzeichnisstruktur bei Bedarf neu an, um die Pfade zu den erforderlichen Dateien zu verkürzen.

Dieser Fehler kann auftreten, wenn die Datei zu groß ist. Bibliotheken oder Objektdateien mit einer Größe von mehr als Gigabyte können für den 32-Bit-Linker Probleme verursachen. Eine mögliche Lösung für dieses Problem besteht darin, das 64-Bit-Toolset zu verwenden. Weitere Informationen zur Vorgehensweise in der Befehlszeile finden [Sie unter Gewusst wie: Aktivieren Sie ein visuelles C++ 64-Bit-Toolset in der](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)Befehlszeile. Informationen dazu, wie Sie dies in der IDE tun, finden Sie unter [Verwenden von MSBuild mit dem 64-Bit-Compiler und-Tools](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) und diesem Stack Overflow Beitrag: Gewusst [wie: Verwenden von Visual Studio, um die systemeigene amd64-Toolkette zu verwenden](https://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055)

Dieser Fehler kann auftreten, wenn Sie nicht über ausreichende Dateiberechtigungen für den Zugriff auf *filename*verfügen. Dies kann vorkommen, wenn Sie ein normales Benutzerkonto verwenden und versuchen, auf Bibliotheksdateien in geschützten Systemverzeichnissen zuzugreifen, oder Dateien verwenden, die von anderen Benutzern kopiert wurden, deren ursprüngliche Berechtigungen festgelegt wurden. Um dieses Problem zu beheben, verschieben Sie die Datei in ein beschreibbares Projektverzeichnis. Wenn sich die Datei in einem beschreibbaren Verzeichnis befindet, aber nicht über die erforderlichen Berechtigungen verfügt, können Sie eine Administrator Eingabeaufforderung verwenden und den Befehl "takeown. exe" ausführen, um den Besitz der Datei zu übernehmen.

Der Fehler kann auftreten, wenn nicht genügend Speicherplatz vorhanden ist. Der Linker verwendet im verschiedenen Fällen temporäre Dateien. Auch wenn Sie über genügend Speicherplatz verfügen, kann ein sehr großer Link den verfügbaren Speicherplatz erschöpft oder fragmentieren. Verwenden Sie die Option [/OPT (Optimierungen)](../../build/reference/opt-optimizations.md) . durch die transitiv Comdat-Eliminierung werden alle Objektdateien mehrmals gelesen.

Wenn der *Dateiname* lnk*nnn*heißt, d. h. ein vom Linker für eine temporäre Datei generierter Dateiname, ist das in der TMP-Umgebungsvariable angegebene Verzeichnis möglicherweise nicht vorhanden, oder es sind mehrere Verzeichnisse für die TMP-Umgebungsvariable angegeben. Es muss nur ein Verzeichnispfad für die TMP-Umgebungsvariable angegeben werden.
