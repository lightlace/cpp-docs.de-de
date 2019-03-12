---
title: Melden eines Problems mit dem Visual C++-Toolset
ms.date: 06/21/2018
ms.technology: cpp-ide
author: corob-msft
ms.author: corob
ms.openlocfilehash: 4b64f79ea5a9566d2ad28216fbc5e736b622fe00
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740244"
---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset-or-documentation"></a>Melden eines Problems mit dem Visual C++-Toolset oder der -Dokumentation

Wenn Sie Probleme mit dem Microsoft Visual C++-Compiler, -Linker oder anderen Tools und Bibliotheken haben, informieren Sie uns darüber. Wenn in unserer Dokumentation ein Fehler vorliegt, möchten wir das natürlich auch wissen.

## <a name="how-to-report-a-c-toolset-issue"></a>Melden eines Problems mit einem C++-Toolset

Die beste Möglichkeit, uns über ein Problem zu informieren, ist das Senden eines Berichts. Dieser sollte die Beschreibung des aufgetretenen Problems enthalten sowie Details dazu, wie Sie Ihr Programm entwickeln, und eine *Reproduktion*, die wir als vollständigen Testfall zum Reproduzieren des Problems auf unseren Computern verwenden können. Anhand dieser Informationen können wir schnell überprüfen, ob das Problem in Ihrem Code besteht oder lokal in Ihrer Umgebung vorliegt. Außerdem können wir bestimmen, ob es sich auf andere Versionen des Compilers auswirkt, und wir können die Ursache ermitteln.

In den folgenden Abschnitten erfahren Sie, was einen guten Bericht ausmacht, wie Sie das von Ihnen erkannte Problem reproduzieren, und wie Sie Ihren Bericht an das Produktteam senden können. Ihre Berichte sind wichtig für uns und andere Entwickler wie Sie. Vielen Dank für Ihren Beitrag zur Verbesserung von Visual C++!

## <a name="how-to-prepare-your-report"></a>Vorbereiten des Berichts

Das Erstellen eines verwertbaren Berichts ist wichtig, da es sehr schwierig ist, das bei Ihnen aufgetretene Problem auf unseren Computern zu reproduzieren, wenn die Informationen nicht vollständig sind. Je besser Ihr Bericht, desto effektiver können wir das Problem reproduzieren und untersuchen.

Ihr Bericht sollte mindestens die folgenden Elemente enthalten:

- Die vollständigen Informationen zur Version des Toolsets, das Sie verwenden.

- Die vollständige „cl.exe“-Befehlszeile, die zum Erstellen Ihres Code verwendet wurde.

- Eine ausführliche Beschreibung des aufgetretenen Problems.

- Bei einer Reproduktion handelt es sich um ein vollständiges, vereinfachtes und unabhängiges Quellcodebeispiel, das das Problem veranschaulicht.

Lesen Sie weiter, um mehr über das Erstellen einer guten Reproduktion und die spezifischen Informationen zu erfahren, die wir benötigen, und wo Sie diese finden können.

### <a name="the-toolset-version"></a>Die Version des Toolsets

Wir benötigen die vollständigen Versionsinformationen und die Zielarchitektur des Toolsets, das das Problem verursacht, um Ihre Reproduktion mit dem gleichen Toolset auf unseren Computern zu testen. Wenn wir das Problem reproduzieren können, verfügen wir über einen Ausgangspunkt, um zu untersuchen, welche anderen Versionen des Toolsets dasselbe Problem aufweisen.

#### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>So melden Sie die vollständige Version des von Ihnen verwendeten Compilers

1. Öffnen Sie die **Developer-Eingabeaufforderung**, die der Version von Visual Studio entspricht, und die Konfigurationsarchitektur, die zum Erstellen Ihres Projekts verwendet wurde. Wenn Sie beispielsweise Anwendungen für x64-Ziele mithilfe von Visual Studio 2017 für x64 erstellen, wählen Sie **x64 Native Tools-Eingabeaufforderung für Visual Studio 2017** aus. Weitere Informationen finden Sie unter [Developer command prompt shortcuts (Tastenkombinationen für die Developer-Eingabeaufforderung)](build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

1. Geben Sie im Fenster „Developer-Eingabeaufforderung“ den Befehl **cl /Bv** ein.

Die Ausgabe sollte etwa so aussehen:

```Output
C:\Users\username\Source>cl /Bv
Microsoft (R) C/C++ Optimizing Compiler Version 19.14.26428.1 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

Compiler Passes:
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\cl.exe:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1xx.dll:      Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c2.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\link.exe:      Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\mspdb140.dll:  Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\1033\clui.dll: Version 19.14.26428.1

cl : Command line error D8003 : missing source filename
```

Kopieren Sie die gesamte Ausgabe in den Bericht.

### <a name="the-command-line"></a>Die Befehlszeile

Wir benötigen die genaue Befehlszeile („cl.exe“ mit allen Argumenten), die verwendet wurde, um den Code zu erstellen, damit wir diesen auf die gleiche Weise auf unseren Computer nachbilden können. Dies ist wichtig, da das aufgetretene Problem eventuell nur existiert, wenn der Build mit einem bestimmten Argument oder einer Kombination von Argumenten erstellt wird.

Diese Informationen finden Sie am besten unmittelbar nach Auftreten des Problems im Buildprotokoll. Dadurch wird sichergestellt, dass die Befehlszeile genau die gleichen Argumente enthält, die ggf. zum Problem beitragen.

#### <a name="to-report-the-contents-of-the-command-line"></a>So melden Sie den Inhalt der Befehlszeile

1. Wechseln Sie zur Daten **CL.command.1.tlog**, und öffnen Sie sie. Standardmäßig befindet sich diese Datei im Ordner „Dokumente“ unter \\Visual Studio*Version*\\Projects\\*Projektmappenname*\\*Projektname*\\*Configuration*\\*Projektname*.tlog\\CL.command.1.tlog oder im Ordner „Benutzer“ unter \\Source\\Repos\\*Projektmappenname*\\*Projektname*\\*Configuration*\\*Projektname*.tlog\\CL.command.1.tlog. Wenn Sie ein anderes Buildsystem verwenden oder den Standardspeicherort für Ihr Projekt geändert haben, kann dieses sich an einem anderen Speicherort befinden.

   In dieser Datei finden Sie die Namen von Quellcodedateien, gefolgt von den Befehlszeilenargumenten zu deren Kompilierung, jeweils in separaten Zeilen.

1. Suchen Sie die Zeile mit dem Namen der Quellcodedatei, in der das Problem auftritt. Die Zeile darunter enthält die entsprechenden Argumente des cl.exe-Befehls.

Kopieren Sie die gesamte Befehlszeile in den Bericht.

### <a name="a-description-of-the-problem"></a>Eine Beschreibung des Problems

Wir benötigen eine ausführliche Beschreibung des aufgetretenen Problems, damit wir überprüfen können, ob es die gleiche Auswirkung auf unseren Computern hat. Außerdem ist es mitunter nützlich, von Ihnen zu erfahren, was Sie erreichen möchten und was Sie erwartet hatten.

Geben Sie die **genauen Fehlermeldungen** an, die das Toolset ausgibt, bzw. das genaue Laufzeitverhalten. Wir benötigen diese Informationen, um zu überprüfen, ob das Problem richtig reproduziert wurde. Geben Sie bitte nicht nur die letzte Fehlermeldung, sondern die **gesamte** Ausgabe des Compilers an. Wir müssen alle Gegebenheiten überblicken können, die vor dem Ihnen ausgestellten Bericht vorhanden waren. Wenn Sie das Problem mithilfe des Befehlszeilencompilers duplizieren können, bevorzugen wir diese Compilerausgabe. Die IDE und andere Buildsysteme filtern die Fehlermeldung möglicherweise heraus, die Ihnen angezeigt wird, oder erfassen nur die erste Zeile einer Fehlermeldung.

Wenn der Fehler darin besteht, dass der Compiler ungültigen Code akzeptiert und keine Diagnose generiert, erwähnen Sie dies in Ihrem Bericht.

Fügen Sie zum Melden eines Problems mit dem Laufzeitverhalten eine **genaue Kopie** der Ausgabe des Programms oder die erwartete Ausgabe hinzu. Diese wird idealerweise in der Ausgabeanweisung eingebettet, z.B. `printf("This should be 5: %d\n", actual_result);`. Erwähnen Sie ebenfalls, falls das Programm abstürzt oder nicht reagiert.

Fügen Sie weitere Details hinzu, die beim Diagnostizieren Ihres Problems hilfreich sein können, z.B. Problemumgehungen, die Sie möglicherweise entdeckt haben. Vermeiden Sie die Wiederholung von Informationen, die an anderer Stelle in Ihrem Bericht vorhanden ist.

### <a name="the-repro"></a>Die Reproduktion

Bei einer Reproduktion handelt es sich um ein vollständiges, eigenständiges Quellcodebeispiel, das Ihr Problem reproduzierbar veranschaulicht. Wir benötigen eine Reproduktion, um den Fehler auf unseren Computern zu reproduzieren. Der Code sollte dafür ausreichen, eine einfache ausführbare Datei zu erstellen, die kompiliert und ausgeführt werden kann bzw. die kompiliert und ausgeführt werden könnte, wenn kein Problem vorliegen würde. Bei einer Reproduktion handelt es sich nicht um einen Codeausschnitt. Es sollten alle Funktionen und Klassen sowie alle erforderlichen #include-Anweisungen (auch für die Standardheader) enthalten sein.

#### <a name="what-makes-a-good-repro"></a>Was zeichnet eine gute Reproduktion aus?

Eine gute Reproduktion weist folgende Merkmale auf:

- **Minimal.** Die Reproduktionen sollte so klein wie möglich sein und dennoch das aufgetretene Problem exakt veranschaulichen. Reproduktionen müssen nicht komplex oder realistisch sein, sondern nur den Code anzeigen, der dem Standard oder der dokumentierten Compilerimplementierung entspricht. Im Fall einer fehlenden Diagnose muss der Code angezeigt werden, der nicht konform ist. Einfache Reproduktionen, die nur den Code enthalten, der für das Veranschaulichen des Problems relevant ist, sind am besten. Wenn Sie Code entfernen oder den Code vereinfachen können, ohne Konformität einzubüßen oder das Problem zu verändern, ist dies erwünscht. Sie müssen keine Beispiele für funktionierenden Code einfügen.

- **Unabhängig.** In Reproduktionen sollten unnötige Abhängigkeiten vermieden werden. Wenn Sie das Problem ohne Drittanbieterbibliotheken reproduzieren können, machen Sie dies. Wenn Sie das Problem abgesehen von einfachen Ausgabeanweisungen (`puts("this shouldn't compile");`, `std::cout << value;` und `printf("%d\n", value);` sind beispielsweise zulässig) ohne Bibliothekscode reproduzieren können, ist dies erwünscht. Idealerweise kann das Beispiel in eine einzige Quellcodedatei ohne Verweise auf Benutzerheader komprimiert werden. Für uns ist es enorm hilfreich, wenn Sie die Menge des Codes verringern, den wir als mögliche Ursache des Problems untersuchen müssen.

- **Neueste Compilerversion.** Für Reproduktionen sollte nach Möglichkeit das neueste Update der aktuellen Version des Toolsets oder das aktuelle Vorabrelease des nächsten Updates oder des nächsten Hauptreleases verwendet werden. Probleme, die in älteren Versionen des Toolsets auftreten, wurden in neueren Versionen häufig behoben. Fehlerbehebungen werden nur in Ausnahmefälle für ältere Versionen bereitgestellt.

- Ein **Vergleich mit anderen Compilern** wurde durchgeführt (falls relevant). Bei Reproduktionen, die portablen C++-Code enthalten, muss das Verhalten mit anderen Compilern, falls möglich, verglichen werden. Der Standard bestimmt letztendlich die Richtigkeit des Programms und kein Compiler ist perfekt. Wenn Clang und GCC Ihren Code jedoch ohne Diagnose akzeptieren, MSVC jedoch nicht, liegt wahrscheinlich ein Fehler im Compiler vor. (Weitere Möglichkeiten bestehen in den unterschiedlichen Verhaltensweisen von Unix und Windows, in verschiedenen Implementierungsebenen der C++-Standards usw.) Wenn Ihr Code andererseits von allen Compilern abgelehnt ist, ist Ihr Code wahrscheinlich fehlerhaft. Die verschiedenen angezeigten Fehlermeldungen können Sie dabei unterstützen, das Problem selbst zu diagnostizieren.

   Eine Liste der Onlinecompiler, mit denen Sie Ihren Code testen können, finden Sie unter [Online C++ compilers (C++-Onlinecompiler)](https://isocpp.org/blog/2013/01/online-c-compilers) auf der ISO C++-Website, oder Sie verwenden diese zusammengestellte [List of Online C++ Compilers (Liste der C++-Onlinecompiler)](https://arnemertz.github.io/online-compilers/) auf GitHub. Zu den Beispielen zählen [Wandbox](https://wandbox.org/), [Compiler Explorer](https://godbolt.org/) und [Coliru](http://coliru.stacked-crooked.com/).

   > [!NOTE]
   > Die Websites für Onlinecompiler stehen nicht in Verbindung mit Microsoft. Viele Websites für Onlinecompiler werden als persönliche Projekte geführt. Einige dieser Seiten sind möglicherweise nicht mehr verfügbar, über eine Suche sollten Sie jedoch andere Seiten finden, die Sie verwenden können.

Probleme mit dem Compiler, dem Linker und den Bibliotheken weisen üblicherweise bestimmte Merkmale auf. Die Art des aufgetretenen Problems bestimmt, welche Art von Reproduktion in den Bericht aufgenommen werden soll. Ohne geeignete Reproduktion gibt es nichts, was wir untersuchen könnten. Im Folgenden finden Sie einige Probleme, die bei Ihnen auftreten können, sowie Anweisungen für das Generieren der Reproduktionen, die Sie für das Melden des jeweiligen Problems verwenden sollten.

#### <a name="frontend-parser-crash"></a>Front-End-Absturz (in der Analysephase)

Front-End-Abstürze erfolgen in der Analysephase des Compilers. Der Compiler gibt in der Regel [Schwerwiegender Fehler C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) aus und verweist auf die Quellcodedatei und Zeilennummer, in der der Fehler aufgetreten ist. Häufig wird eine Datei des Typs „msc1.cpp“ erwähnt, die Sie jedoch ignorieren können.

Fügen Sie bei dieser Art des Absturzes eine [vorverarbeitete Reproduktion](#preprocessed-repros) hinzu.

Hier ist ein Beispiel der Ausgabe des Compilers bei dieser Art von Absturz:

```Output
SandBoxHost.cpp
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        fatal error C1001: An internal error has occurred in the compiler.
(compiler file 'msc1.cpp', line 1369)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        note: This diagnostic occurred in the compiler generated function
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted
        to send an error report to Microsoft later.
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

#### <a name="backend-code-generation-crash"></a>Back-End-Absturz (Codegenerierung)

Back-End-Abstürze erfolgen in der Codegenerierungsphase des Compilers. Der Compiler gibt in der Regel [Schwerwiegender Fehler C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) aus und verweist ggf. nicht auf die Quellcodedatei und Zeilennummer, in der das Problem aufgetreten ist. Häufig wird die Datei „compiler\\utc\\src\\p2\\main.c“ erwähnt, dies können Sie jedoch ignorieren.

Stellen Sie für diese Art von Absturz eine [Linkreproduktion](#link-repros) bereit, wenn Sie die Link-Zeitcodegenerierung (Link-Time Code Generation, LTCG) verwenden, die vom Befehlszeilenargument **/GL** für „cl.exe“ aktiviert wurde. Wenn dies nicht der Fall ist, stellen Sie stattdessen eine [vorverarbeitete Reproduktion](#preprocessed-repros) bereit.

Hier finden Sie ein Beispiel der Ausgabe des Compilers bei einem Back-End-Absturz, wenn LTCG nicht verwendet wird. Wenn Ihre Compilerausgabe wie folgt aussieht, sollten Sie eine [vorverarbeitete Reproduktion](#preprocessed-repros) bereitstellen.

```Output
repro.cpp
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:
        An internal error has occurred in the compiler.
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
INTERNAL COMPILER ERROR in
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

Wenn in der Zeile, die mit **Interner Compilerfehler** beginnt, „link.exe“ anstatt „cl.exe“ angegeben ist, war LTCG aktiviert, weshalb Sie eine [Linkreproduktion](#link-repros) bereitstellen sollten. Wenn anhand der Fehlermeldung des Compilers nicht klar ist, ob LTCG aktiviert war, müssen Sie möglicherweise die Befehlszeilenargumente untersuchen, die Sie in einem vorherigen Schritt aus dem Buildprotokoll für das Befehlszeilenargument **/GL** kopiert haben.

#### <a name="linker-crash"></a>Linkerabstürze

Linkerabstürze treten in der Verknüpfungsphase nach Ausführung des Compilers auf. In der Regel gibt der Linker [Linkertoolfehler LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md) aus.

> [!NOTE]
> Wenn die Ausgabe C1001 oder LTCG enthält, finden Sie unter [Back-End-Absturz (Codegenerierung)](#backend-code-generation-crash) weitere Informationen.

Fügen Sie bei dieser Art von Absturz eine [Linkreproduktion](#link-repros) hinzu.

Hier ist ein Beispiel der Ausgabe des Compilers bei dieser Art von Absturz.

```Output
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2

  Version 14.00.22816.0

  ExceptionCode            = C0000005
  ExceptionFlags           = 00000000
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)
        "z:\tools\bin\x64\link.exe"
  NumberParameters         = 00000002
  ExceptionInformation[ 0] = 0000000000000000
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF

CONTEXT:

  Rax    = 0000000000000400  R8     = 0000000000000000
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690
  Rdx    = 000000655F97E270  R11    = 0000000000000400
  Rsp    = 000000655F97E248  R12    = 0000000000000000
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000
  Rsi    = 000000655DF82580  R14    = 000000655F97F390
  Rdi    = 0000000000000000  R15    = 0000000000000000
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206
  SegCs  = 0000000000000033  SegDs  = 000000000000002B
  SegSs  = 000000000000002B  SegEs  = 000000000000002B
  SegFs  = 0000000000000053  SegGs  = 000000000000002B
  Dr0    = 0000000000000000  Dr3    = 0000000000000000
  Dr1    = 0000000000000000  Dr6    = 0000000000000000
  Dr2    = 0000000000000000  Dr7    = 0000000000000000
```

Wenn inkrementelles Verknüpfen aktiviert ist und der Absturz nach dem erfolgreichen anfänglichen Verknüpfen stattgefunden hat (d.h. erst nach der ersten vollständigen Verknüpfung, auf der nachfolgende inkrementelle Verknüpfungen basieren), fügen Sie eine Kopie der Objekt- und Bibliotheksdateien (OBJ und LIB) hinzu, die den Quelldateien entsprechen, die nach Abschluss der anfänglichen Verknüpfung geändert wurden.

#### <a name="bad-code-generation"></a>Generierung von fehlerhaftem Code

Die Generierung von fehlerhaftem Code ist selten, erfolgt jedoch, wenn der Compiler versehentlich falschen Code erzeugt, der den Absturz Ihrer Anwendung zur Laufzeit bewirkt, anstatt dieses Problem zur Kompilierungszeit zu erkennen. Wenn Sie meinen, dass das aufgetretene Problem zur Generierung von fehlerhaftem Code führt, erstellen Sie Ihren Bericht analog zu [ Back-End-Absturz (Codegenerierung)](#backend-code-generation-crash).

Stellen Sie für diese Art von Absturz eine [Linkreproduktion](#link-repros) bereit, wenn Sie die Link-Zeitcodegenerierung (Link-Time Code Generation, LTCG) verwenden, die vom Befehlszeilenargument **/GL** für „cl.exe“ aktiviert wurde. Wenn dies nicht der Fall ist, stellen Sie eine [vorverarbeitete Reproduktion](#preprocessed-repros) bereit.

## <a name="how-to-generate-a-repro"></a>Generieren einer Reproduktion

Eine [gute Reproduktion](#what-makes-a-good-repro) ist entscheidend, damit wir die Quelle des Problems ermitteln können. Bevor Sie einen der im Folgenden beschriebenen Schritte für bestimmte Arten von Reproduktionen ausführen, versuchen Sie, den Code, der das Problem veranschaulicht, so weit wie möglich zu reduzieren. Versuchen Sie, Abhängigkeiten, erforderliche Header und Bibliotheken zu entfernen oder zu minimieren, und begrenzen Sie nach Möglichkeit die verwendeten Compileroptionen und Präprozessordefinitionen.

Es folgenden Anweisungen zum Generieren der verschiedenen Arten von Reproduktionen, mit deren Hilfe Sie verschiedene Arten von Problemen melden.

### <a name="preprocessed-repros"></a>Vorverarbeitete Reproduktionen

Bei einer *vorverarbeiteten Reproduktion* handelt es sich um eine einzelne Quelldatei, die ein Problem veranschaulicht und aus der Ausgabe des C-Präprozessors generiert wurde, indem die Compileroption **/P** in der ursprünglichen Quelldatei der Reproduktion verwendet wurde. Dabei wird für eingeschlossene Header eine inline-Ersetzung vorgenommen, um Abhängigkeiten von zusätzlichen Quell- und Headerdateien sowie Makros, #ifdef-Direktiven und andere Präprozessorbefehle zu entfernen, die von Ihrer lokalen Umgebung abhängig sein können.

> [!NOTE]
> Vorverarbeitete Reproduktionen sind für Probleme nicht besonders nützlich, die das Ergebnis von Fehlern der Implementierung unserer Standardbibliothek sein können, da die neueste in Bearbeitung befindliche Implementierung häufig ausgetauscht wird, um zu prüfen, ob das Problem bereits behoben wurde. Führen Sie in diesem Fall keine Vorverarbeitung der Reproduktion aus. Wenn Sie das Problem nicht zu einer einzelne Quelldatei reduzieren können, packen Sie Ihren Code in eine ZIP-Datei o.ä., oder erwägen Sie eine IDE-Projektreproduktion. Weitere Informationen finden Sie unter [Andere Reproduktionen](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>So erfolgt die Vorverarbeitung einer Quellcodedatei

1. Erfassen Sie die Befehlszeilenargumente, die zum Erstellen Ihrer Reproduktion verwendet wurden. Dieser Vorgang wird unter [So melden Sie den Inhalt der Befehlszeile](#to-report-the-contents-of-the-command-line) beschrieben.

1. Öffnen Sie die **Developer-Eingabeaufforderung**, die der Version von Visual Studio entspricht, und die Konfigurationsarchitektur, die zum Erstellen Ihres Projekts verwendet wurde.

1. Wechseln Sie zu dem Verzeichnis, das die Reproduktion Ihres Projekts enthält.

1. Geben Sie im Konsolenfenster der Developer-Eingabeaufforderung den Befehl **cl /P** *Argumente* *Dateiname.cpp* ein. Hierbei stellt *Argumente* die Liste der oben erfassten Argumente und *Dateiname.cpp* den Namen der Quelldatei Ihrer Reproduktion dar. Dieser Befehl repliziert die Befehlszeile, die für die Reproduktion verwendet wurde, beendet jedoch die Kompilierung nach dem Durchlauf des Präprozessors und gibt den vorverarbeiteten Quellcode in der Datei „*Dateiname*.i“ aus.

Wenn Sie eine C++- oder CX-Quellcodedatei vorverarbeiten oder das Feature „C++-Module“ verwenden, sind einige zusätzliche Schritte erforderlich. Weitere Informationen finden Sie in den folgenden Abschnitten.

Nachdem Sie die vorverarbeitete Datei generiert haben, sollten Sie sicherstellen, dass das Problem mithilfe der vorverarbeiteten Datei reproduziert werden kann.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>So bestätigen Sie, dass der Fehler mit der vorverarbeiteten Datei weiter reproduziert wird

1. Geben Sie im Konsolenfenster der Developer-Eingabeaufforderung den Befehl „**cl** *Argumente* **/TP** *Dateiname*.i“ ein, damit „cl.exe“ die vorverarbeitete Datei als C++-Quelldatei kompiliert. Hierbei stellt *Argumente* die Liste der oben erfassten Argumente dar, bei der jedoch alle **/D**- und **/I**-Argumente entfernt wurden (da diese bereits in der vorverarbeiteten Datei enthalten sind), und *Dateiname.i* stellt den Namen der vorverarbeiteten Datei dar.

1. Vergewissern Sie sich, dass das Problem reproduziert wird.

Fügen Sie Ihrem Bericht schließlich die vorverarbeitete Reproduktion (*Dateiname*.i) an.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>Vorverarbeitete C++/CX WinRT/UWP-Codereproduktionen

Wenn Sie C++ oder CX verwenden, um Ihre ausführbare Datei zu erstellen, sind einige zusätzliche Schritte erforderlich, um eine vorverarbeitete Reproduktion zu erstellen und zu überprüfen.

#### <a name="to-preprocess-ccx-source-code"></a>Vorverarbeiten von C++/CX-Quellcode

1. Erstellen Sie wie unter [To preprocess a source code file (Vorverarbeiten einer Quellcodedatei)](#to-preprocess-a-source-code-file) beschrieben eine vorverarbeitete Quelldatei.

1. Durchsuchen Sie die Datei _Dateiname_.i nach **#using-Direktiven**.

1. Erstellen Sie eine Liste aller Dateien, auf die verwiesen wird. Lassen Sie alle Windows\*.winmd- und platform.winmd-Dateien sowie „mscorlib.dll“ aus.

Wenn Sie überprüfen möchten, ob die vorverarbeitete Datei das Problem immer noch reproduziert,

1. erstellen Sie ein neues Verzeichnis für die vorverarbeitete Datei, und kopieren Sie sie in das neue Verzeichnis.

1. Kopieren Sie die WINMD-Dateien aus Ihrer **#using-Liste** in das neue Verzeichnis.

1. Erstellen Sie eine leere vccorlib.h-Datei im neuen Verzeichnis.

1. Bearbeiten Sie die vorverarbeitete Datei, um alle **#using-Direktiven** für „mscorlib.dll“ zu entfernen.

1. Bearbeiten Sie die vorverarbeitete Datei, um alle absoluten Pfade in die reinen Dateinamen der kopierten WINMD-Dateien zu ändern.

Überprüfen Sie wie zuvor, dass die vorverarbeitete Datei das Problem immer noch reproduziert.

### <a name="preprocessed-c-modules-repros"></a>Reproduktionen vorverarbeiteter C++-Module

Wenn Sie das Modulfeature des C++-Compilers verwenden, sind verschiedene Schritte erforderlich, um eine vorverarbeitete Reproduktion zu erstellen und zu überprüfen.

#### <a name="to-preprocess-a-source-code-file-that-uses-a-module"></a>Vorverarbeiten einer Quellcodedatei, die ein Modul verwendet

1. Erfassen Sie die Befehlszeilenargumente, die zum Erstellen Ihrer Reproduktion verwendet wurden. Dieser Vorgang wird unter [So melden Sie den Inhalt der Befehlszeile](#to-report-the-contents-of-the-command-line) beschrieben.

1. Öffnen Sie die **Developer-Eingabeaufforderung**, die der Version von Visual Studio entspricht, und die Konfigurationsarchitektur, die zum Erstellen Ihres Projekts verwendet wurde.

1. Wechseln Sie zu dem Verzeichnis, das die Reproduktion Ihres Projekts enthält.

1. Geben Sie im Konsolenfenster der Developer-Eingabeaufforderung den Befehl **cl /P** *Argumente* *Dateiname.cpp* ein. Hierbei stellt *Argumente* die Liste der oben erfassten Argumente und *Dateiname.cpp* den Namen der Quelldatei, die das Modul verwendet, dar.

1. Ändern Sie das Verzeichnis, das das Reproduktionsprojekt enthält, das die Modulschnittstelle (die IFC-Ausgabe) erstellt hat.

1. Erfassen Sie die Befehlszeilenargumente, die zum Erstellen der Modulschnittstelle verwendet wurden.

1. Geben Sie im Konsolenfenster der Developer-Eingabeaufforderung den Befehl **cl /P** *Argumente* *Modulname.ixx* ein. Hierbei stellt *Argumente* die Liste der oben erfassten Argumente und *Modulname.ixx* den Namen der Datei, die die Modulschnittstelle erstellt, dar.

Nachdem Sie die vorverarbeitete Datei generiert haben, sollten Sie sicherstellen, dass das Problem mithilfe der vorverarbeiteten Datei reproduziert werden kann.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>So bestätigen Sie, dass der Fehler mit der vorverarbeiteten Datei weiter reproduziert wird

1. Wechseln Sie im Fenster der Entwicklerkonsole zu dem Verzeichnis, das die Reproduktion Ihres Projekts enthält.

1. Geben Sie wie zuvor den Befehl **cl** *Argumente* **/TP** *Dateiname*.i ein, um die vorverarbeitete Datei so zu kompilieren, als wäre sie eine C++-Quelldatei.

1. Überprüfen Sie wie zuvor, dass die vorverarbeitete Datei das Problem immer noch reproduziert.

Fügen Sie die vorverarbeiteten Reproduktionsdateien (*Dateiname*.i und *Modulname*.i) schließlich zusammen mit der IFC-Ausgabe Ihrem Bericht hinzu.

### <a name="link-repros"></a>Linkreproduktionen

Bei einer *Linkreproduktion* handelt es sich um die vom Linker generierten Inhalte eines Verzeichnisses, das von der Umgebungsvariable **link\_repro** angegeben wird. In dieser sind die Buildartefakte enthalten, die ein Problem veranschaulichen, das zur Linkzeit auftritt, z.B. ein Back-End-Absturz in Zusammenhang mit der Link-Zeitcodegenerierung (LTCG) oder ein Absturz des Linkers. Diese Buildartefakte sind als Linkereingabe erforderlich, damit das Problem reproduziert werden kann. Eine Linkreproduktion kann einfach erstellt werden, indem Sie diese Umgebungsvariable verwenden, um die integrierte Funktion des Linkers zum Generieren einer Reproduktion zu aktivieren.

#### <a name="to-generate-a-link-repro"></a>So generieren Sie eine Linkreproduktion

1. Erfassen Sie die Befehlszeilenargumente, die zum Erstellen Ihrer Reproduktion verwendet wurden. Dieser Vorgang wird unter [So melden Sie den Inhalt der Befehlszeile](#to-report-the-contents-of-the-command-line) beschrieben.

1. Öffnen Sie die **Developer-Eingabeaufforderung**, die der Version von Visual Studio entspricht, und die Konfigurationsarchitektur, die zum Erstellen Ihres Projekts verwendet wurde.

1. Wechseln Sie im Konsolenfenster der Developer-Eingabeaufforderung zu dem Verzeichnis, das die Reproduktion Ihres Projekts enthält.

1. Geben Sie **mkdir linkrepro** ein, um ein Verzeichnis für die Linkreproduktion zu erstellen.

1. Geben Sie den Befehl **set link\_repro=linkrepro** ein, um die Umgebungsvariable **link\_repro** auf das Verzeichnis festzulegen, das Sie gerade erstellt haben. Wenn Ihr Build von einem anderen Verzeichnis aus ausgeführt wird, was bei komplexeren Projekten häufig der Fall ist, legen Sie für **link\_repro** stattdessen den vollständigen Pfad zu Ihrem linkrepro-Verzeichnis fest.

1. Geben Sie im Konsolenfenster der Developer-Eingabeaufforderung den Befehl **devenv** ein, um das reproduzierte Projekt in Visual Studio zu erstellen. Dadurch wird sichergestellt, dass der Wert der Umgebungsvariablen **link\_repro** für Visual Studio sichtbar ist. Verwenden Sie zum Erstellen des Projekts über die Befehlszeile die oben erfassten Befehlszeilenargumente, um den reproduzierten Build zu duplizieren.

1. Erstellen Sie das reproduzierte Projekt, und vergewissern Sie sich, dass das erwartete Problem aufgetreten ist.

1. Wenn Sie Visual Studio für den Build verwendet haben, schließen Sie das Programm.

1. Geben Sie im Konsolenfenster der Developer-Eingabeaufforderung den Befehl **set link\_repro=** ein, um die Umgebungsvariable **link\_repro** zu löschen.

Packen Sie abschließend die Reproduktion, indem Sie das gesamte Verzeichnis der Linkreproduktion in einer ZIP-Datei o.ä. komprimieren, und fügen Sie diese an Ihren Bericht an.

### <a name="other-repros"></a>Andere Reproduktionen

Wenn Sie das Problem nicht auf eine einzelne Quelldatei oder vorverarbeitete Reproduktion reduzieren können und das Problem keine Linkreproduktion verlangt, können wir ein IDE-Projekt untersuchen. Die Anleitung für das Erstellen einer guten Reproduktion gilt hierfür ebenfalls: Der Code sollte minimal und eigenständig sein, das Problem sollte in den neuesten Tools auftreten und das Problem sollte nicht in anderen Compilern angezeigt werden (falls relevant).

Erstellen Sie Ihre Reproduktion als minimales IDE-Projekt, und erstellen Sie dann ein Paket, indem Sie die gesamte Verzeichnisstruktur in einer ZIP-Datei o.ä. komprimieren und diese an Ihren Bericht anfügen.

## <a name="ways-to-send-your-report"></a>Möglichkeiten zum Senden Ihres Berichts

Es gibt mehrere gute Möglichkeiten, uns Ihren Bericht zu übermitteln. Die können das in Visual Studio integrierte [Tool „Problem melden“](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) oder die Seiten der [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) verwenden. Sie gelangen direkt zu den Seiten der Developer Community, wenn Sie auf **Produktfeedback** unten auf der Seite klicken. Die Wahl hängt davon ab, ob Sie die integrierten Tools der IDE zum Erstellen von Screenshots und zum Organisieren Ihres Berichts verwenden möchten, um diesen auf den Seiten der Entwicklercommunity zu veröffentlichen, oder ob Sie lieber direkt die Website verwenden möchten.

> [!NOTE]
> Unabhängig davon, wie Sie den Bericht senden, respektiert Microsoft Ihre Privatsphäre. Microsoft verpflichtet sich der Einhaltung aller Datenschutzgesetze- und regeln. Informationen dazu, wie wir Daten behandeln, die Sie uns senden, finden Sie in der [Datenschutzerklärung von Microsoft](https://privacy.microsoft.com/privacystatement).

### <a name="use-the-report-a-problem-tool"></a>Nutzen des Tools „Problem melden“

Das Tool **Problem melden** in Visual Studio bietet Benutzern von Visual Studio die Möglichkeit, eine Vielzahl von Problemen über ein paar Mausklicks zu melden. Es bietet ein einfaches Formular, in dem Sie detaillierte Informationen zum aufgetretenen Problem angeben und Ihren Bericht anschließend übermitteln können, ohne die IDE verlassen zu müssen.

Es ist einfach und praktisch, von der IDE aus ein Problem über das Tool **Problem melden** zu melden. Sie können über die Titelleiste auf das Tool zugreifen, indem Sie auf das Symbol **Feedback senden** neben dem Suchfeld **Schnellstart** klicken. Alternativ finden Sie es auf der Menüleiste unter **Hilfe** > **Feedback senden** > **Problem melden**.

Wenn Sie ein Problem melden möchten, suchen Sie zunächst in der Developer Community nach ähnlichen Problemen. Wenn das Problem bereits zuvor gemeldet wurde, stimmen Sie für das Thema ab, und fügen Sie Kommentare mit zusätzlichen Einzelheiten hinzu. Wenn Sie kein Problem dieser Art finden, klicken Sie auf die Schaltfläche **Neues Problem melden** am Ende des Feedbackdialogfelds von Visual Studio, und befolgen Sie die Schritte, um Ihr Problem einzureichen.

### <a name="use-the-visual-studio-developer-community-pages"></a>Verwenden Sie die Seiten der Visual Studio Developer Community

Die Seiten der Visual Studio Developer Community bietet eine weitere einfache Möglichkeit zum Melden von Problemen und zum Finden von Lösungen für Visual Studio und den C++-Compiler, für Tools und für Bibliotheken. Es gibt spezifische Developer Community-Seiten für [Visual Studio](https://developercommunity.visualstudio.com/spaces/8/index.html), [Visual Studio für Mac](https://developercommunity.visualstudio.com/spaces/41/index.html), [.NET](https://developercommunity.visualstudio.com/spaces/61/index.html), [C++](https://developercommunity.visualstudio.com/spaces/62/index.html), [ Azure DevOps](https://developercommunity.visualstudio.com/spaces/21/index.html) und [TFS](https://developercommunity.visualstudio.com/spaces/22/index.html). Unter diesen Registerkarte finden Sie oben auf jeder Seite ein Suchfeld, über das Sie Beiträge oder Themen finden können, die Ihrem Problem ähneln. Möglicherweise sind eine Lösung oder andere nützliche Informationen bezüglich Ihres Problem bereits vorhanden. Wenn jemand zuvor das gleiche Problem gemeldet hat, stimmen Sie für dieses Thema ab, kommentieren Sie es, und erstellen Sie keinen neuen Problembericht. Sie werden möglicherweise dazu aufgefordert, sich bei Ihrem Visual Studio-Konto anzumelden und der Developer Community-App Zugriff auf Ihr Profil zu gewähren, wenn Sie kommentieren, abstimmen oder ein neues Problem melden möchten.

Verwenden Sie bei Problemen mit dem C++-Compiler, dem Linker und anderen Tools und Bibliotheken die [C++](https://developercommunity.visualstudio.com/spaces/62/index.html)-Seite. Wenn Sie nach Ihrem Problem suchen und es noch nicht gemeldet wurde, wählen Sie die Schaltfläche **Problem melden** neben dem Suchfeld oben auf der Seite aus. Sie können Ihren Reproduktionscode und die Befehlszeile sowie Screenshots, Links zu ähnlichen Diskussionen oder andere Informationen hinzufügen, die relevant und nützlich für dieses Thema sind.

> [!TIP]
> Für andere Arten von Problemen, die möglicherweise in Visual Studio auftreten, die jedoch nicht mit dem C++-Toolset zusammenhängen (z.B. Benutzeroberflächenprobleme, defekte IDE-Funktionalität oder allgemeine Abstürze), verwenden Sie das Tool **Problem melden** in der IDE. Dies ist die beste Wahl, da es über Screenshotfunktionen verfügt und Benutzeroberflächenaktionen aufzeichnen kann, die zu dem aufgetretenen Problem geführt haben. Diese Art von Problemen kann auch auf der [Developer Community](https://developercommunity.visualstudio.com/)-Website nachgeschlagen werden. Weitere Informationen finden Sie unter [Melden eines Problems mit Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017).

### <a name="reports-and-privacy"></a>Berichte und Datenschutz

Standardmäßig sind **alle Informationen in Berichten sowie alle Kommentare und Antworten öffentlich sichtbar**. Dies ist in der Regel ein Vorteil, da die gesamte Community Einblicke in die Probleme, Lösungen und Problemumgehungen anderer Benutzer hat. Wenn Sie Ihre Daten oder Ihre Identität jedoch aus Gründen des Datenschutzes oder des geistigen Eigentums nicht veröffentlichen möchten, gibt es Optionen, die Sie nutzen können.

Wenn Sie Ihre Identität nicht offenlegen möchten, [erstellen Sie ein neues Microsoft-Konto](https://signup.live.com/), das keine personenbezogenen Informationen enthält. Verwenden Sie dieses Konto, um Ihren Bericht zu erstellen.

**Fügen Sie keine Informationen, die privat bleiben sollen, in den Titel oder den Inhalt des ursprünglichen Berichts ein, denn dieser ist öffentlich.** Stattdessen sollten Sie Details privat in einem separaten Kommentar versenden. Wenn Sie sicherstellen möchten, dass für Ihren Bericht die richtige Zielgruppe festgelegt ist, sollten Sie **cppcompiler** in die Themenliste des Problemberichts einfügen. Sobald der Problembericht erstellt ist, können Sie festlegen, wer Ihre Antworten und Anlagen anzeigen kann.

#### <a name="to-create-a-problem-report-for-private-information"></a>Erstellen eines Problemberichts für private Informationen

1. Klicken Sie im erstellten Bericht auf **Kommentar hinzufügen**, um eine private Beschreibung des Problems zu erstellen.

1. Verwenden Sie im Antwort-Editor das Dropdown-Steuerelement unter den Schaltflächen **Senden** und **Abbrechen**, um die Zielgruppe für Ihre Antwort festzulegen. Nur die angegebenen Personen können die privaten Antworten sowie enthaltene Bilder, Links und Code anzeigen. Wählen Sie **Viewable by moderators and the original poster** (Sichtbar für Moderatoren und den Verfasser) aus, um die Sichtbarkeit auf Microsoft-Mitarbeiter und sich selbst zu beschränken.

1. Fügen Sie die Beschreibung und weitere erforderliche Informationen, Bilder und Dateianlagen für die Reproduktion hinzu. Klicken Sie auf die Schaltfläche **Senden**, um diese Informationen privat zu senden.

   Beachten Sie, dass Sie maximal 10 Dateien und maximal 2 GB anfügen können. Fordern Sie bei größeren Uploads eine Upload-URL in einem privaten Kommentar an.

Alle Antworten unter diesem Kommentar haben die Sichtbarkeit, die Sie angegeben haben. Dies gilt auch, wenn das Dropdown-Steuerelement den Status der eingeschränkten Sichtbarkeit nicht korrekt anzeigt.

Wenn Sie Ihre Privatsphäre schützen und Ihre vertraulichen Daten nicht veröffentlichen möchten, sollte die gesamte Interaktion mit Microsoft unter diesen eingeschränkten Kommentaren stattfinden. Antworten auf andere Kommentare können dazu führen, dass Sie versehentlich vertrauliche Informationen offenlegen.

## <a name="how-to-report-a-c-documentation-issue"></a>So melden Sie einen Fehler in der C++-Dokumentation

Wir verwenden GitHub-Tickets, um Fehler in unserer Dokumentation zu erfassen. Sie können GitHub-Tickets jetzt direkt von einer Inhaltsseite aus erstellen. So können Sie besser mit Autoren und Produktteams kommunizieren. Wenn Ihnen ein Fehler (ein falsches Codebeispiel, eine verwirrende Erklärung, eine schwerwiegende Auslassung oder auch nur ein Tippfehler) in einer Dokumentation auffällt, können Sie uns ganz leicht darüber informieren. Scrollen Sie auf der Seite ganz nach unten, und klicken Sie auf **Sign in to give documentation feedback** (Anmelden und Feedback zur Dokumentation geben). Sie müssen ein GitHub-Konto erstellen, wenn Sie nicht bereits über ein Konto verfügen. Sobald Sie über ein Konto verfügen, können Sie sich alle Tickets zur Dokumentation und deren Status ansehen und Benachrichtigungen erhalten, wenn ein von Ihnen gemeldetes Problem bearbeitet wurde. Weitere Informationen erhalten Sie unter [A New Feedback System Is Coming to docs.microsoft.com](/teamblog/a-new-feedback-system-is-coming-to-docs) (Neues Feedbacksystem auf docs.microsoft.com).

Wenn Sie ein GitHub-Ticket zur Dokumentation über die Feedbackschaltfläche in der Dokumentation erstellen, wird das Ticket automatisch mit Informationen zur Seite aufgefüllt, für die Sie das Ticket erstellen möchten, damit wir wissen, wo das Problem besteht. Bearbeiten Sie diese Informationen nicht. Fügen Sie nur Angaben zu dem Problem hinzu. Wenn Sie möchten, können Sie auch einen Änderungsvorschlag machen. [Unsere Dokumentation ist Open Source](https://github.com/MicrosoftDocs/cpp-docs/). Wenn Sie also einen Fehler beheben und eine Änderung vorschlagen möchten, können Sie dies selbst tun. Weitere Informationen zum Beitragen zur Dokumentation finden Sie im [Leitfaden für Mitwirkende](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) auf GitHub.
