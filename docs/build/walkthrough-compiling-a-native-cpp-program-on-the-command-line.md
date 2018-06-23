---
title: 'Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C++-Programms in der Befehlszeile | Microsoft Docs'
ms.custom: conceptual
ms.date: 06/21/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb0d7aab8000febdf07288370da058f437767387
ms.sourcegitcommit: e013acba70aa29fed60ae7945162adee23e19c3b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36322432"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C++-Programms in der Befehlszeile

Visual C++ enthält einen C++-Befehlszeilencompiler, den Sie verwenden können, um alles von grundlegenden konsolenanwendungen für universelle Windows-Plattform-apps, Desktop-apps, Gerätetreiber und .NET-Komponenten zu erstellen.

In dieser exemplarischen Vorgehensweise erstellen Sie ein grundlegender, "Hello, World"-Stil C++-Programm mit einem Text-Editor und kompilieren es dann in der Befehlszeile angegeben. Wenn Sie möchten, um zu versuchen das Visual Studio-IDE statt über die Befehlszeile finden Sie unter [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) oder [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

In dieser exemplarischen Vorgehensweise können Sie Ihr eigenes Visual C++-Programm verwenden, statt das gezeigte einzugeben, oder Sie können ein Visual C++-Codebeispiel aus einem anderen Hilfeartikel verwenden.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise müssen installiert Visual Studio und dem optionalen **Desktopentwicklung mit C++** arbeitsauslastung oder der Befehlszeile Build-Tools für Visual Studio.

Visual Studio ist eine leistungsstarke integrierte Entwicklungsumgebung (IDE), die einem voll ausgestatteten-Editor, Ressourcen-Manager, Debugger und Compilern für viele Sprachen und Plattformen unterstützt. Informationen zum Herunterladen und installieren Visual Studio, einschließlich der kostenlosen Visual Studio Community Edition und Unterstützung für C/C++-Entwicklung finden Sie unter [Installieren von C++-Unterstützung in Visual Studio](../build/vscpp-step-0-installation.md).

Der Build-Tools für Visual Studio installiert nur die Befehlszeilencompiler, Tools und Bibliotheken, die zum Erstellen von C und C++-Programmen erforderlich. Ist es perfekt für Build Labs oder Schulungsraum ausführt und relativ schnell installiert. Um nur die Befehlszeilentools zu installieren, laden Sie [Build-Tools für Visual Studio-2017](https://go.microsoft.com/fwlink/p/?linkid=875721).

Bevor Sie eine C- oder C++-Programm in der Befehlszeile erstellen können, müssen Sie sicherstellen, dass die Verwaltungstools installiert sind und Sie sie über die Befehlszeile zugreifen können. Visual C++ stellt komplexe Anforderungen an die befehlszeilenumgebung zum Suchen von Tools, Header und Bibliotheken, die verwendet. **Sie können Visual C++ in einem einfachen Eingabeaufforderungsfenster verwenden** ohne vorbereiten. Visual C++ installiert Glücklicherweise Tastenkombinationen für Sie eine Developer-Eingabeaufforderung zu starten, die die Umgebung, die für Befehlszeilenbuilds eingerichtet hat. Leider sind die Namen der Verknüpfungen mit der Developer-Eingabeaufforderung und wo sich diese befinden sich in fast jeder Version von Visual C++ und in verschiedenen Versionen von Windows. Die erste Aufgabe für die exemplarische Vorgehensweise findet das richtige zu verwenden.

> [!NOTE]
> Eine Developer-eingabeaufforderungsverknüpfung legt automatisch die richtigen Pfade für den Compiler und Tools, und für alle erforderlichen Header und Bibliotheken. Sie müssen diese Umgebungswerte selbst festlegen bei Verwendung von regulären Eingabeaufforderungsfensters. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Es wird empfohlen, dass Sie eine Developer-eingabeaufforderungsverknüpfung verwenden, anstatt eine eigene erstellen.

### <a name="open-a-developer-command-prompt"></a>Öffnen Sie eine Developer-Eingabeaufforderung

1. Wenn Sie Visual Studio 2017 unter Windows 10 installiert haben, öffnen Sie im Menü Start, und wählen Sie **alle apps**. Führen Sie einen Bildlauf nach unten, und Öffnen der **Visual Studio 2017** Ordner (nicht die Visual Studio-2017-app). Wählen Sie **Developer-Eingabeaufforderung für VS 2017** im Eingabeaufforderungsfenster zu öffnen.

   Wenn Sie Microsoft Visual C++ erstellen Tools 2015 für Windows 10 installiert haben, öffnen Sie die **starten** Menü, und wählen Sie **alle apps**. Führen Sie einen Bildlauf nach unten, und Öffnen der **Visual C++-Buildtools** Ordner. Wählen Sie **Visual C++ 2015 X86 Native Tools-Eingabeaufforderung** im Eingabeaufforderungsfenster zu öffnen.

   Wenn Sie eine andere Version von Visual Studio verwenden oder eine andere Version von Windows ausgeführt werden, suchen Sie im Startmenü oder Startseite für einen Ordner der Visual Studio-Tools, der eine Developer-eingabeaufforderungsverknüpfung enthält. Sie können auch die Windows Search-Funktion verwenden, suchen Sie nach "Developer-Eingabeaufforderung", und wählen eine, die die installierte Version von Visual Studio entspricht. Verwenden Sie die Verknüpfung, um das Eingabeaufforderungsfenster zu öffnen.

2. Als Nächstes stellen Sie sicher, dass Visual C++ Developer-Eingabeaufforderung ordnungsgemäß eingerichtet ist. Geben Sie in das Eingabeaufforderungsfenster `cl` und stellen Sie sicher, dass die Ausgabe etwa wie folgt sieht:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Möglicherweise gibt es Unterschiede in der aktuellen Verzeichnis oder Versionsnummern, abhängig von der Version von Visual C++ und alle Updates installiert. Wenn dies gleicht dem, was Sie sehen, sind Sie bereit für C- oder C++-Programme in der Befehlszeile zu erstellen.

   > [!NOTE]
   > Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als ein interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten Sie beim Ausführen der **cl** Befehl, und klicken Sie dann entweder Sie eine Developer-Eingabeaufforderung nicht verwenden oder etwas stimmt nicht mit der Installation von Visual C++. Sie müssen dieses Problem beheben, bevor Sie fortfahren können.

   Wenn Sie die Developer-eingabeaufforderungsverknüpfung finden können, oder wenn Sie eine Fehlermeldung erhalten, bei der Eingabe `cl`, und klicken Sie dann Visual C++-Installation ein Fehler vorliegt. Installieren Sie die Visual C++-Komponente in Visual Studio erneut, oder installieren Sie die Microsoft Visual C++-Buildtools. Nicht fahren Sie mit dem nächsten Abschnitt bis dies funktioniert. Weitere Informationen zur Installation und Problembehandlung in Visual C++ finden Sie unter [installieren Sie Visual Studio](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Je nach Version von Windows auf dem Computer und der Systemsicherheitskonfiguration müssen Sie möglicherweise mit der rechten Maustaste öffnen Sie das Kontextmenü für die Developer-eingabeaufforderungsverknüpfung, und wählen Sie dann **als Administrator ausführen** an Erstellen und das Programm, das Sie erstellen, indem Sie in dieser exemplarischen Vorgehensweise auszuführen.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Erstellen Sie eine Visual C++-Quelldatei und kompilieren Sie diese über die Befehlszeile

1. In der Developer-Eingabeaufforderungsfenster, geben Sie **Md c:\hello** , erstellen Sie ein Verzeichnis aus, und geben dann **cd c:\hello** so ändern Sie in diesem Verzeichnis. Dies ist das Verzeichnis, dem die Quelldatei und das kompilierte Programm erstellt werden.

2. Geben Sie **Notepad hello.cpp** in das Eingabeaufforderungsfenster.

   Wählen Sie **Ja** Wenn Editor aufgefordert, eine Datei zu erstellen. Daraufhin wird ein leeres Editor-Fenster, die für Sie zur Eingabe von Code in einer Datei namens hello.cpp bereit.

3. Geben Sie in Editor die folgenden Codezeilen ein:

   ```cpp
   #include <iostream>
   using namespace std;
   void main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   Dies ist ein sehr einfaches Programm, das eine Zeile Text auf den Bildschirm schreibt und sich dann beendet. Um Fehler zu minimieren, kopieren Sie diesen Code, und fügen Sie ihn in Editor ein.

4. Speichern Sie Ihre Arbeit. Wählen Sie im Editor im Menü **Datei** den Befehl **Speichern**aus.

   Herzlichen Glückwunsch, Sie haben eine Visual C++-Quelldatei hello.cpp, die zum Kompilieren bereit ist.

5. Wechseln Sie in der Developer-Eingabeaufforderungsfenster. Geben Sie **Dir** an der Eingabeaufforderung aus, um den Inhalt des Verzeichnisses c:\hello aufzulisten. Die Quelle Datei hello.cpp in der Verzeichnisliste, die etwa wie folgt aussieht, sollte angezeigt werden:

   ```Output
   c:\hello>dir
    Volume in drive C has no label.
    Volume Serial Number is CC62-6545

    Directory of c:\hello

   05/24/2016  05:36 PM    <DIR>          .
   05/24/2016  05:36 PM    <DIR>          ..
   05/24/2016  05:37 PM               115 hello.cpp
                  1 File(s)            115 bytes
                  2 Dir(s)  571,343,446,016 bytes free

   ```

   Die Datumsangaben und andere Details werden auf Ihrem Computer abweichen. Wenn Sie die Quellcodedatei nicht angezeigt wird, hello.cpp, stellen Sie sicher, dass Sie zum Verzeichnis c:\hello erstellten geändert haben und im Editor, stellen sicher, dass Sie die Quelldatei in diesem Verzeichnis gespeichert. Stellen Sie außerdem sicher, dass Sie den Quellcode mit cpp Dateinamenerweiterung nicht die Erweiterung TXT gespeichert.

6. Geben Sie an der Developer-Eingabeaufforderung `cl /EHsc hello.cpp` um das Programm zu kompilieren.

   Der cl.exe-Compiler generiert eine OBJ-Datei, die den kompilierten Code enthält, und führt dann den Linker aus, um ein ausführbares Programm namens „hello.exe“ zu erstellen. Dieser Name wird in den Zeilen der Ausgabeinformationen angezeigt, die der Compiler anzeigt. Die Ausgabe des Compilers sollte etwa wie folgt aussehen:

   ```Output
   c:\hello>cl /EHsc hello.cpp
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   hello.cpp
   Microsoft (R) Incremental Linker Version 14.10.25017.0
   Copyright (C) Microsoft Corporation.  All rights reserved.

   /out:hello.exe
   hello.obj
   ```

   > [!NOTE]
   > Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als ein interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten, die Developer-Eingabeaufforderung nicht ordnungsgemäß eingerichtet. Informationen zu diesem Problem zu beheben, wechseln Sie zurück zu den **Developer-Eingabeaufforderung öffnen** Abschnitt.

   > [!NOTE]
   > Wenn Sie einen anderen Compiler oder Linkerfehler oder eine Warnung erhalten, überprüfen Sie den Quellcode zum Beheben alle Fehler, speichern Sie es und führen Sie den Compiler erneut aus. Informationen zu bestimmten Fehlern verwenden Sie das Suchfeld auf diesem MSDN-Seite für die dazu gehörende Nummer gesucht werden soll.

7. Geben Sie zum Ausführen des hello.exe-Programms an der Eingabeaufforderung `hello`ein.

   Das Programm zeigt folgenden Text an und wird anschließend beendet:

   ```Output
   Hello, world, from Visual C++!
   ```

   Herzlichen Glückwunsch, Sie haben gerade kompiliert und ein C++-Programms mithilfe der Befehlszeilentools ausführen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Beispiel "Hello, World" ist ungefähr so einfach wie eine C++-Programms erhalten kann. Reales Programme haben Headerdateien und weitere Quelldateien in Bibliotheken verknüpfen, und führen Sie sinnvolle Arbeit.

Sie können die Schritte in dieser exemplarischen Vorgehensweise verwenden, zum Erstellen eigener C++-Codes statt den Beispielcode einzugeben. Sie können auch viele Beispielprogramme für C++-Code erstellen, die Sie an anderer Stelle zu finden. Sie können Quellcode und Erstellen Ihrer apps im alle beschreibbaren Verzeichnisse. Standardmäßig erstellt Visual Studio-IDE-Projekte in Ihrem Ordner "Dokumente" in einem Unterordner Projekte von einer Visual Studio entsprechend benannten Ordner für Ihre Version von Visual Studio.

Um ein Programm zu kompilieren, die mehrere Quellcodedateien verfügt, geben Sie sie alle in der Befehlszeile angegeben, wie folgt aus:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

Die **/EHsc** -Befehlszeilenoption weist den Compiler an, die C++-Ausnahmebehandlung zu aktivieren. Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md).

Wenn Sie mehrere Quelldateien wie folgt angeben, verwendet der Compiler die ersten Eingabedatei den Namen des Programms erstellen. In diesem Fall wird ein Programm namens file1.exe ausgegeben. Fügen Sie zum Ändern des Namens auf program1.exe ein [/out](../build/reference/out-output-file-name.md) (Linkeroption):

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Und wenn Sie um weitere Programmierfehler automatisch zu erfassen, sollten Sie kompilieren, indem Sie entweder die [/W3](../build/reference/compiler-option-warning-level.md) oder [/W4](../build/reference/compiler-option-warning-level.md) aus:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Der Compiler, die cl.exe, verfügt über viele weitere Optionen können Sie anwenden, um "erstellen", zu optimieren, Debuggen und Analysieren von Code. Geben Sie eine kurze Liste **cl /?** an der Developer-Eingabeaufforderung. Sie können auch kompilieren und verknüpfen separat und Optionen des Linkers in komplexeren Buildszenarien anwenden. Weitere Informationen für Compiler und Linkeroptionen und Verwendung finden Sie unter [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md).

Sie können NMAKE und Makefiles oder MSBuild und Projektdateien zu konfigurieren und zum Erstellen komplexerer Projekte in der Befehlszeile verwenden. Weitere Informationen zur Verwendung dieser Tools finden Sie unter [NMAKE-Referenz](../build/nmake-reference.md) und [MSBuild](../build/msbuild-visual-cpp.md).

Die Programmiersprachen C und C++ sind ähnlich, aber nicht identisch. Visual C++-Compiler verwendet eine einfache Regel, um zu bestimmen, welche Sprache verwendet, wenn den Code kompiliert wird. Standardmäßig behandelt der Visual C++-Compiler alle auf .c endenden Dateien als C-Quellcode und alle auf .cpp endenden Dateien als C++-Quellcode. Verwenden Sie zum Erzwingen des Compilers alle Dateien als C++ unabhängig von der Dateierweiterung "" behandelt die [/TC](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) -Compileroption.

Visual C++-Compiler umfasst eine C-Laufzeitbibliothek (CRT), die mit ISO C99-Standard kompatibel, aber nicht unbedingt kompatibel ist. In den meisten Fällen wird die portablen Code kompilieren und wie erwartet ausgeführt werden. Visual C++ unterstützt einige CRT-Änderungen in ISO C11 nicht. Bestimmte Bibliotheksfunktionen und das POSIX-Funktionsnamen werden vom Visual C++-Compiler als veraltet markiert. Die Funktionen werden unterstützt, aber die Namen der bevorzugten wurden geändert. Weitere Informationen finden Sie unter [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md) und [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)  
[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)  
[Compileroptionen](../build/reference/compiler-options.md)  
