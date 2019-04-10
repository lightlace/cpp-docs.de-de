---
title: /MP (Erstellen mit mehreren Prozessen)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.MultiProcessorCompilation
helpviewer_keywords:
- -MP compiler option (C++)
- /MP compiler option (C++)
- MP compiler option (C++)
- cl.exe compiler, multi-process build
ms.openlocfilehash: e005b0314e87270e81dbb155dfdaa67be067cd3f
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424143"
---
# <a name="mp-build-with-multiple-processes"></a>/MP (Erstellen mit mehreren Prozessen)

Die Option **/MP** kann die Gesamtzeit für die Kompilierung der Quelldateien in der Befehlszeile reduzieren. Die Option **/MP** bewirkt, dass der Compiler eine oder mehrere Kopien von sich selbst erstellt, jeweils in einem separaten Prozess. Diese Kopien kompilieren dann gleichzeitig die Quelldateien. Daher kann die Gesamtzeit für die Erstellung der Quelldateien erheblich reduziert werden.

## <a name="syntax"></a>Syntax

> **/MP**[*processMax*]

## <a name="arguments"></a>Argumente

*processMax*<br/>
(Optional) Die maximale Anzahl von Prozessen, die der Compiler erstellen kann.

Die *ProcessMax* Argument muss zwischen 1 und 65536 liegen. Andernfalls gibt der Compiler die Warnmeldung **D9014**, ignoriert der *ProcessMax* -Argument, und nimmt an, dass die maximale Anzahl von Prozessen 1.

Wenn Sie weglassen der *ProcessMax* -Argument, das der Compiler Ruft die Anzahl der [effektiven Prozessoren](#effective_processors) aus dem Betriebssystem auf Ihrem Computer und erstellt einen Prozess für jeden Prozessor.

## <a name="remarks"></a>Hinweise

Die Compileroption **/MP** kann beim Kompilieren vieler Dateien die Buildzeit beträchtlich reduzieren. Zur Verbesserung der Buildzeit erstellt der Compiler bis zu *ProcessMax* Kopien von sich selbst und verwendet dann diese Kopien, um Ihre Quelldateien zur gleichen Zeit zu kompilieren. Die Option **/MP** gilt für Kompilierungen, jedoch nicht für das Linken oder die Link-Zeitcodegenerierung. Standardmäßig ist die Option **/MP** Option deaktiviert.

Die Verbesserung der Buildzeit hängt von der Anzahl der Prozessoren auf einem Computer ab, der Anzahl der zu kompilierenden Dateien und der Verfügbarkeit von Systemressourcen, z.B. der E/A-Kapazität. Experimentieren Sie mit der Option **/MP** , um die beste Einstellung zum Erstellen eines bestimmten Projekts zu bestimmen. Ratschläge, die Sie bei dieser Entscheidung unterstützen, finden Sie unter [Richtlinien](#guidelines).

## <a name="incompatible-options-and-language-features"></a>Inkompatible Optionen und Sprachfunktionen

Die Option **/MP** ist mit einigen Compileroptionen und Sprachfunktionen nicht kompatibel. Wenn Sie eine nicht kompatible Compileroption mit verwenden die **/MP** auswählen, gibt der Compiler die Warnung **D9030** und ignoriert die **/MP** Option. Wenn Sie eine nicht kompatible Sprachfunktion verwenden, gibt der Compiler Fehler [C2813](../../error-messages/compiler-errors-2/compiler-error-c2813.md) und beendet oder fortgesetzt werden, abhängig von der aktuellen compilerwarnstufe.

> [!NOTE]
> Die meisten Optionen sind nicht kompatibel, denn wenn sie zulässig wären, würden die gleichzeitig ausgeführten Compiler ihre Ausgabe zur gleichen Zeit auf die Konsole oder in eine bestimmte Datei schreiben. Daher wäre die Ausgabe vermischt und verstümmelt. In einigen Fällen würde die Kombination von Optionen die Leistung verschlechtern.

Die folgende Tabelle enthält die Compileroptionen und Sprachfunktionen, die nicht mit der Option **/MP** kompatibel sind:

|Option oder Sprachfunktion|Beschreibung|
|--------------------------------|-----------------|
|[#import](../../preprocessor/hash-import-directive-cpp.md) Präprozessordirektive|Konvertiert die Typen in einer Typbibliothek in C++-Klassen und schreibt diese Klassen dann in eine Headerdatei.|
|[/E](e-preprocess-to-stdout.md), [/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Kopiert die Präprozessorausgabe in die Standardausgabe (**stdout**).|
|[/Gm](gm-enable-minimal-rebuild.md)|Veraltet. Ermöglicht eine inkrementelle erneute Erstellung.|
|[/showIncludes](showincludes-list-include-files.md)|Schreibt eine Liste von Includedateien in den Standardfehler (**stderr**).|
|[/Yc](yc-create-precompiled-header-file.md)|Schreibt eine vorkompilierte Headerdatei.|

## <a name="diagnostic-messages"></a>Diagnosemeldungen

Wenn Sie eine Option oder Sprachfunktion angeben, die nicht mit der Option **/MP** kompatibel ist, erhalten Sie eine Diagnosemeldung. Die folgende Tabelle enthält die Meldungen und das Verhalten des Compilers:

|Diagnosemeldung|Beschreibung|Compilerverhalten|
|------------------------|-----------------|-----------------------|
|**C2813**|Die **#import** Direktive ist nicht kompatibel mit der Option **/MP** Option.|Die Kompilierung endet, sofern keine Option für [Compilerwarnstufen](compiler-option-warning-level.md) etwas anderes angibt.|
|**D9014**|Ein ungültiger Wert angegeben ist, für die *ProcessMax* Argument.|Der Compiler ignoriert den ungültigen Wert und nimmt den Wert 1 an.|
|**D9030**|Die angegebene Option ist nicht kompatibel mit **/MP**.|Der Compiler ignoriert die Option **/MP** .|

## <a name="guidelines"></a> Richtlinien

### <a name="measure-performance"></a>Messen der Leistung

Verwenden Sie die gesamte Buildzeit zum Messen der Leistung. Sie können die Buildzeit mit einer physischen Uhr messen, oder Sie können Software verwenden, die den Unterschied zwischen Start und Ende des Build berechnet. Wenn Ihr Computer über mehrere Prozessoren verfügt, kann eine physische Uhr genauere Ergebnisse als eine Software-Zeitmessung ergeben.

### <a name="effective_processors"></a> Effective Processors

Ein Computer kann eine oder mehrere virtuelle Prozessoren, die auch als bekannt sind haben *effektiven Prozessoren*, für jeden seiner physischen Prozessoren. Jeder physischer Prozessor kann einen oder mehrere Kerne haben, und wenn das Betriebssystem für einen Kern Hyperthreading ermöglicht, erscheint jeder Kern als zwei virtuelle Prozessoren.

Beispiel: Ein Computer verfügt über einen effektiven Prozessor, wenn er einen physischen Prozessor mit einem Kern besitzt und Hyperthreading deaktiviert ist. Im Gegensatz dazu besitzt ein Computer acht effektive Prozessoren, wenn er zwei physische Prozessoren mit jeweils zwei Kernen hat und alle Kerne Hyperthreading aktiviert haben. D. h. (8 effektive Prozessoren) = (2 physische Prozessoren) x (2 Kerne pro physischem Prozessor) x (2 effektive Prozessoren pro Kern wegen Hyperthreading).

Wenn Sie weglassen der *ProcessMax* -Argument in der **/MP** -Option der Compiler Ruft die Anzahl der effektiven Prozessoren vom Betriebssystem ab und erstellt dann einen Prozess pro effektivem Prozessor. Jedoch kann der Compiler nicht garantieren, welcher Prozess auf einem bestimmten Prozessor ausgeführt wird; das Betriebssystem trifft diese Entscheidung.

### <a name="number-of-processes"></a>Anzahl der Prozesse

Der Compiler berechnet die Anzahl der Prozesse, die dazu verwendet werden, die Quelldateien zu kompilieren. Dieser Wert ist kleiner als die Anzahl der Quelldateien, die Sie in der Befehlszeile angeben und die Anzahl der Prozesse, die Sie explizit oder implizit mit der Option **/MP** angeben. Sie können die maximale Anzahl von Prozessen explizit festlegen, wenn Sie angeben, die *ProcessMax* Argument der **/MP** Option. Oder Sie können die Standardeinstellung, die gleich der Anzahl der effektiven Prozessoren in einem Computer, wenn Sie weglassen, wird die *ProcessMax* Argument.

Beispielsweise können Sie die folgende Befehlszeile angeben:

`cl /MP7 a.cpp b.cpp c.cpp d.cpp e.cpp`

In diesem Fall verwendet der Compiler fünf Prozesse, da dies weniger als fünf Quelldateien und maximal sieben Prozesse sind. Beispiel: Ihr Computer hat zwei effektive Prozessoren und Sie geben die folgende Befehlszeile an:

`cl /MP a.cpp b.cpp c.cpp`

In diesem Fall meldet das Betriebssystem zwei Prozessoren. Daher verwendet der Compiler zwei Prozesse in seiner Berechnung. Daher wird der Compiler den Build mit zwei Prozessen ausführen, da dies der kleinere Wert von zwei Prozessen und drei Quelldateien ist.

### <a name="source-files-and-build-order"></a>Quelldateien und Buildreihenfolge

Die Quelldateien werden möglicherweise nicht in der gleichen Reihenfolge kompiliert, in denen sie in der Befehlszeile angezeigt werden. Obwohl der Compiler eine Reihe von Prozessen erstellt, die Kopien des Compilers enthalten, plant das Betriebssystem, wann jeder Prozess ausgeführt wird. Daher können Sie nicht garantieren, dass die Quelldateien in einer bestimmten Reihenfolge kompiliert werden.

Eine Quelldatei wird kompiliert, wenn ein Prozess für ihre Kompilierung verfügbar ist. Wenn mehr Dateien als Prozesse vorhanden sind, wird der erste Satz von Dateien von den verfügbaren Prozessen kompiliert. Die restlichen Dateien werden verarbeitet, wenn ein Prozess die Behandlung einer vorherigen Datei beendet und für die Verarbeitung einer der verbleibenden Dateien bereitsteht.

Geben Sie die gleiche Quelldatei nicht mehrmals in einer Befehlszeile an. Dies kann zum Beispiel passieren, wenn ein Tool automatisch eine [Makefile](contents-of-a-makefile.md) erstellt, die auf Abhängigkeitsinformationen in einem Projekt basiert. Wenn Sie die Option **/MP** nicht angeben, verarbeitet der Compiler die Liste der Dateien sequenziell und kompiliert jedes Vorkommen der Datei neu. Wenn Sie jedoch die Option **/MP** angeben, wird die gleiche Datei möglicherweise von verschiedenen Compilern zur gleichen Zeit kompiliert. Aus diesem Grund versuchen die verschiedenen Compiler zur gleichen Zeit in die gleiche Ausgabedatei zu schreiben. Ein Compiler wird exklusiven Schreibzugriff auf die Ausgabedatei erhalten und die anderen Compiler werden einen Dateizugriffsfehler melden.

### <a name="using-type-libraries-import"></a>Verwenden von Typbibliotheken (#import)

Der Compiler unterstützt nicht die Verwendung der [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive zusammen mit dem **/MP** -Schalter. Führen Sie wenn möglich die folgenden Schritte aus, um dieses Problem zu umgehen:

- Verschieben Sie alle `#import` -Direktiven in den verschiedenen Quelldateien in eine oder mehrere Dateien, und kompilieren Sie dann diese Dateien ohne die Option **/MP** . Das Ergebnis ist ein Satz generierter Headerdateien.

- In den restlichen Quelldateien fügen Sie die [#include](../../preprocessor/hash-include-directive-c-cpp.md) -Direktiven ein, die die generierten Header angeben, und kompilieren Sie dann die restlichen Quelldateien mit der Option **/MP** .

### <a name="visual-studio-project-settings"></a>Visual Studio Projekteinstellungen

#### <a name="the-msbuildexe-tool"></a>Das Tool „MSBUILD.exe“

Visual Studio verwendet die [MSBuild.exe](/visualstudio/msbuild/msbuild-reference) Tool, um Projektmappen und Projekte zu erstellen. Die **maxcpucount:**_Anzahl_ (oder **/m:**_Anzahl_) Befehlszeilenoption des MSBuild.exe-Tools kann mehrere Projekte erstellen, die gleichzeitig. Die Compileroption **/MP** kann mehrere Kompilierungseinheiten gleichzeitig erstellen. Wenn es für die Anwendung geeignet ist, verbessern Sie die Buildzeit Ihrer Projektmappe, indem Sie **/MP** oder/und **/maxcpucount**verwenden.

Die Buildzeit der Projektmappe hängt teilweise von der Anzahl der Prozesse ab, die den Build ausführen. Die *Anzahl* Argument der [maxcpucount](/visualstudio/msbuild/msbuild-command-line-reference) MSBuild-Option gibt die maximale Anzahl der Projekte gleichzeitig erstellen. Auf ähnliche Weise die *ProcessMax* Argument der **/MP** Compiler-Option gibt die maximale Anzahl von Kompilierungseinheiten gleichzeitig erstellen. Wenn die **maxcpucount** Option gibt an, *P* Projekte und die **/MP** Option gibt an, *C* verarbeitet wird, maximal *P*  x *C* Prozesse zur gleichen Zeit ausführen.

Die Richtlinie für die Entscheidung, ob zum Verwenden von MSBuild oder **/MP** Technologie lautet wie folgt:

- Wenn viele Projekte mit wenigen Dateien in jedem Projekt vorhanden sind, verwenden Sie das MSBuild-Tool.

- Wenn wenige Projekte mit vielen Dateien in jedem Projekt vorhanden sind, verwenden Sie die Option **/MP** .

- Wenn die Anzahl von Projekten und Dateien pro Projekt ausgeglichen ist, verwenden Sie beide MSBuild und **/MP**. Legen Sie anfangs die Option **/maxcpucount** auf die Anzahl der zu erstellenden Projekte und die Option **/MP** auf die Anzahl der Prozessoren im Computer fest. Messen Sie die Leistung und passen Sie dann die Einstellungen so an, dass sie zu optimalen Ergebnissen führen. Wiederholen Sie diesen Zyklus, bis Sie mit der Gesamt-Buildzeit zufrieden sind.

## <a name="see-also"></a>Siehe auch

[#import-Anweisung](../../preprocessor/hash-import-directive-cpp.md)<br/>
[Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference)<br/>
[/ ZF (schnellere PDB-Generierung)](zf.md)<br/>
