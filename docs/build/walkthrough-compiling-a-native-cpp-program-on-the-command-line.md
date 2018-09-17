---
title: 'Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile | Microsoft-Dokumentation'
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
ms.openlocfilehash: 855b3e3947839a08d920bb27b664ea4ce1027bf8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713115"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C++-Programms in der Befehlszeile

Visual C++ enthält einen C++-Befehlszeilencompiler, den Sie verwenden können, von einfachen Konsolen-apps für universelle Windows-Plattform-apps, Desktop-apps, Gerätetreiber und .NET-Komponenten alles erstellen.

In dieser exemplarischen Vorgehensweise erstellen Sie eine einfache, "Hello, World"-Stil C++-Programm mit einem Text-Editor und kompilieren es dann in der Befehlszeile aus. Wenn Sie möchten, um zu versuchen der Visual Studio-IDE, anstatt über die Befehlszeile finden Sie unter [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) oder [mithilfe von Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

In dieser exemplarischen Vorgehensweise können Sie Ihr eigenes Visual C++-Programm verwenden, statt das gezeigte einzugeben, oder Sie können ein Visual C++-Codebeispiel aus einem anderen Hilfeartikel verwenden.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Abschließen dieser exemplarischen Vorgehensweise müssen installiert sein Visual Studio und den optionalen **Desktopentwicklung mit C++** Workload oder die Befehlszeilen-Buildtools für Visual Studio.

Visual Studio ist eine leistungsfähige integrierte Entwicklungsumgebung (IDE), die einen Editor mit vollem Funktionsumfang, Ressourcen-Manager, Debugger und Compiler für viele Sprachen und Plattformen unterstützt. Weitere Informationen zum Herunterladen und installieren Visual Studio, einschließlich der kostenlosen Visual Studio Community Edition und Unterstützung für C/C++-Entwicklung, finden Sie unter [Installieren von C++-Unterstützung in Visual Studio](../build/vscpp-step-0-installation.md).

Die Build-Tools für Visual Studio installiert nur die Befehlszeilencompiler, Tools und Bibliotheken, die Sie zum Erstellen von C- und C++-Programmen benötigen. Es eignet sich ideal für Build-Laboren oder Classroom ausführt und relativ schnell installiert werden. Um nur die Befehlszeilentools zu installieren, laden [Build-Tools für Visual Studio 2017](https://go.microsoft.com/fwlink/p/?linkid=875721).

Bevor Sie ein C- oder C++-Programm in der Befehlszeile erstellen können, müssen Sie überprüfen, dass die Tools installiert sind und Sie sie über die Befehlszeile zugreifen können. Visual C++ stellt komplexe Anforderungen an die der befehlszeilenumgebung um Tools, Header und Bibliotheken verwendeten zu finden. **Sie können Visual C++ in einem einfachen Eingabeaufforderungsfenster verwenden** ohne einige Vorbereitungsschritte ausführen. Visual C++ installiert Glücklicherweise Tastenkombinationen für die Sie eine Developer-Eingabeaufforderung zu starten, die in der Umgebung, die für Befehlszeilenbuilds eingerichtet sind. Leider sind die Namen der Developer-eingabeaufforderungsverknüpfungen und wo sich diese befinden sich in fast jeder Version von Visual C++ und in verschiedenen Versionen von Windows. Die erste Aufgabe der exemplarischen Vorgehensweise findet das richtige Abonnement verwenden.

> [!NOTE]
> Eine Developer-eingabeaufforderungsverknüpfung legt automatisch die richtigen Pfade für den Compiler und Tools, und für alle erforderlichen Header und Bibliotheken. Sie müssen diese Umgebungswerte selbst festlegen bei Verwendung einer regulären Eingabeaufforderungsfensters. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Es wird empfohlen, dass Sie eine Developer-eingabeaufforderungsverknüpfung verwenden, anstatt Ihre eigenen erstellen.

### <a name="open-a-developer-command-prompt"></a>Eine Developer-Eingabeaufforderung öffnen

1. Wenn Sie Visual Studio 2017 unter Windows 10 installiert haben, öffnen Sie im Startmenü, und wählen Sie **alle apps**. Führen Sie einen Bildlauf nach unten, und Öffnen der **Visual Studio 2017** Ordner (nicht der Visual Studio 2017-app). Wählen Sie **Developer-Eingabeaufforderung für Visual Studio 2017** im Eingabeaufforderungsfenster zu öffnen.

   Wenn Sie Microsoft Visual C++ Build Tools 2015 unter Windows 10 installiert haben, öffnen Sie die **starten** Menü, und wählen Sie **alle apps**. Führen Sie einen Bildlauf nach unten, und Öffnen der **Visual C++ Build Tools** Ordner. Wählen Sie **Visual C++ 2015 X86 Native Tools-Eingabeaufforderung** im Eingabeaufforderungsfenster zu öffnen.

   Wenn Sie eine andere Version von Visual Studio verwenden oder eine andere Version von Windows ausgeführt werden, suchen Sie im Startmenü oder -Startseite für den Ordner ein Visual Studio-Tools, der eine Developer-eingabeaufforderungsverknüpfung enthält. Sie können auch den Windows Search-Funktion verwenden, suchen Sie nach "Developer Command Prompt", und wählen Sie eine, die die installierte Version von Visual Studio entspricht. Verwenden Sie die Verknüpfung, um das Eingabeaufforderungsfenster zu öffnen.

2. Als Nächstes stellen Sie sicher, dass Visual C++ Developer-Eingabeaufforderung ordnungsgemäß eingerichtet ist. Geben Sie im Eingabeaufforderungsfenster Befehl `cl` und stellen Sie sicher, dass die Ausgabe sieht in etwa wie folgt:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Möglicherweise gibt es Unterschiede in der das aktuelle Verzeichnis oder Versionsnummern, abhängig von der Version von Visual C++ und alle Updates installiert. Wenn dies ähnlich ist, was Sie sehen, sind Sie bereit für C- oder C++-Programme in der Befehlszeile zu erstellen.

   > [!NOTE]
   > Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten Sie beim Ausführen der **cl** Befehl, und klicken Sie dann entweder Sie eine Developer-Eingabeaufforderung nicht verwenden oder Es gibt es Probleme bei der Installation von Visual C++. Sie müssen dieses Problem beheben, bevor Sie fortfahren können.

   Wenn Sie die Developer-eingabeaufforderungsverknüpfung nicht finden oder wenn Sie eine Fehlermeldung erhalten, bei der Eingabe `cl`, und klicken Sie dann Visual C++-Installation ein Fehler vorliegt. Installieren Sie die Visual C++-Komponente in Visual Studio erneut, oder installieren Sie Microsoft Visual C++ Build Tools neu. Gehen Sie nicht auf mit dem nächsten Abschnitt bis dies funktioniert. Weitere Informationen zur Installation und Problembehandlung in Visual C++ finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Abhängig von der Version von Windows auf dem Computer und der Systemsicherheitskonfiguration müssen Sie möglicherweise ein mit der rechten Maustaste das Kontextmenü für die Verknüpfung der Developer-Eingabeaufforderung öffnen, und wählen Sie dann **als Administrator ausführen** auf erfolgreich zu erstellen Sie, und führen Sie das Programm, das Sie anhand dieser exemplarischen Vorgehensweise erstellen.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Erstellen Sie eine Visual C++-Quelldatei und kompilieren Sie diese in der Befehlszeile

1. Geben Sie in der Developer-Eingabeaufforderungsfenster, **Md c:\hello** erstellen Sie ein Verzeichnis, und geben **cd c:\hello** so ändern Sie in diesem Verzeichnis. Dies ist das Verzeichnis, dem die Quelldatei und das kompilierte Programm erstellt werden.

2. Geben Sie **Notepad hello.cpp** im Eingabeaufforderungsfenster Befehl.

   Wählen Sie **Ja** Wenn Editor fordert Sie auf eine Datei zu erstellen. Daraufhin wird ein leeres Editor-Fenster, die für Sie zur Eingabe von Code in einer Datei namens hello.cpp bereit.

3. Geben Sie im Editor die folgenden Codezeilen ein:

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

   Herzlichen Glückwunsch! Sie haben eine Visual C++-Quelldatei hello.cpp, die kompiliert werden kann.

5. Wechseln Sie in der Developer-Eingabeaufforderungsfenster. Geben Sie **Dir** an der Eingabeaufforderung zum Auflisten des Inhalts des Verzeichnisses c:\hello. Hello.cpp der Quelle-Datei in der verzeichnisauflistung sollte die wie folgt aussehen:

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

   Die Datumsangaben und andere Details variieren auf Ihrem Computer. Wenn die Quellcodedatei nicht angezeigt wird, hello.cpp, stellen Sie sicher, dass Sie zum Verzeichnis c:\hello erstellten geändert haben und in Editor, stellen Sie sicher, dass Sie die Quelldatei in diesem Verzeichnis gespeichert haben. Außerdem stellen Sie sicher, dass Sie den Quellcode mit einer CPP Dateinamenerweiterung, nicht die Erweiterung TXT gespeichert.

6. Geben Sie an der Developer-Eingabeaufforderung `cl /EHsc hello.cpp` auf Ihr Programm zu kompilieren.

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
   > Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten, der Developer-Eingabeaufforderung nicht ordnungsgemäß eingerichtet. Informationen dazu, wie dieses Problem zu beheben, wechseln Sie zurück zu den **Developer-Eingabeaufforderung öffnen** Abschnitt.

   > [!NOTE]
   > Wenn Sie einen anderen Compiler oder Linker-Fehler oder Warnung erhalten, überprüfen Sie Ihren Quellcode zum Korrigieren Sie eventuelle Fehler, speichern Sie ihn, und führen den Compiler erneut aus. Informationen zu bestimmten Fehlern verwenden Sie das Suchfeld auf dieser Seite des MSDN nach der Fehlernummer gesucht werden soll.

7. Geben Sie zum Ausführen des hello.exe-Programms an der Eingabeaufforderung `hello`ein.

   Das Programm zeigt folgenden Text an und wird anschließend beendet:

   ```Output
   Hello, world, from Visual C++!
   ```

   Herzlichen Glückwunsch! Sie haben gerade kompiliert und ein C++-Programm mithilfe der Befehlszeilentools ausführen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Beispiel "Hello, World" ist ein C++-Programm erhalten kann. Realen Programmen verfügen, Headerdateien und mehrere Quelldateien in Bibliotheken auf den link, und die Ausführungszeit sinnvoll nutzen.

Sie können die Schritte in dieser exemplarischen Vorgehensweise verwenden, um Ihre eigenen C++-Code anstatt den Beispielcode zu erstellen. Sie können auch viele C++-Codebeispielprogramm erstellen, die Sie an anderer Stelle zu finden. Sie können Ihren Quellcode platzieren und erstellen Sie Ihre apps in einem Verzeichnis geschrieben. Standardmäßig erstellt Visual Studio-IDE Projekte im Ordner "Dokumente", in einem Unterordner Projekte eines Visual Studio-Ordners, der mit dem Namen für Ihre Version von Visual Studio.

Um ein Programm zu kompilieren, die über mehrere Quellcodedateien verfügt, geben Sie sie auf der Befehlszeile wie folgt aus:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

Die **/EHsc** -Befehlszeilenoption weist den Compiler an, die C++-Ausnahmebehandlung zu aktivieren. Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md).

Wenn Sie mehrere Quelldateien wie folgt angeben, verwendet der Compiler der erste Eingabedatei den Namen des Programms zu erstellen. In diesem Fall gibt es ein Programm namens file1.exe. Um den Namen in program1.exe zu ändern, Hinzufügen einer [/out](../build/reference/out-output-file-name.md) (Linkeroption):

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Um weitere Programmierfehler automatisch abzufangen, sollten Sie kompilieren, indem Sie entweder die [/w3](../build/reference/compiler-option-warning-level.md) oder [/W4](../build/reference/compiler-option-warning-level.md) aus:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Der Compiler, die cl.exe, verfügt über viele weitere Optionen, die Sie anwenden, um das Erstellen, zu optimieren, Debuggen und Analysieren von Code können. Geben Sie für eine kurze Liste **cl /?** in der Developer-Eingabeaufforderung. Sie können auch kompilieren und separat zu verknüpfen und Optionen des Linkers in komplexere Buildszenarios anwenden. Weitere Informationen für Compiler und Optionen des Linkers und Verwendung finden Sie unter [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md).

Sie können MSBuild und Projektdateien und Makefiles oder NMAKE verwenden, konfigurieren und komplexere Projekte in der Befehlszeile erstellen. Weitere Informationen zur Verwendung dieser Tools finden Sie unter [NMAKE-Referenz](../build/nmake-reference.md) und [MSBuild](../build/msbuild-visual-cpp.md).

Die Programmiersprachen C und C++ sind ähnlich, jedoch nicht identisch. Visual C++-Compiler verwendet eine einfache Regel, um zu bestimmen, welche Sprache verwendet, wenn sie Ihren Code kompiliert wird. Standardmäßig behandelt der Visual C++-Compiler alle auf .c endenden Dateien als C-Quellcode und alle auf .cpp endenden Dateien als C++-Quellcode. Verwenden Sie zum Erzwingen des Compilers alle Dateien als C++ unabhängig von der Dateierweiterung behandelt die [/TC](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) -Compileroption.

Visual C++-Compiler umfasst eine C-Laufzeitbibliothek (CRT), die mit dem ISO C99-Standard kompatibel ist, aber nicht unbedingt kompatibel ist. In den meisten Fällen portablen Code kompiliert und wie erwartet ausgeführt werden. Visual C++ unterstützt einige der CRT-Änderungen im ISO C11 nicht. Bestimmte Bibliotheksfunktionen und POSIX-Funktionsnamen werden vom Visual C++-Compiler als veraltet markiert. Die Funktionen werden unterstützt, aber die Namen der bevorzugten wurden geändert. Weitere Informationen finden Sie unter [Sicherheitsfunktionen in CRT](../c-runtime-library/security-features-in-the-crt.md) und [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)<br/>
[Compileroptionen](../build/reference/compiler-options.md)
