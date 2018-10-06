---
title: 'Exemplarische Vorgehensweise: Kompilieren ein C-Programms in der Befehlszeile | Microsoft-Dokumentation'
ms.custom: conceptual
ms.date: 09/24/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8361890c264e11fbd5817331e07ba9005da17240
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821373"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile

Visual C++ enthält einen C-Compiler, mit denen Sie alles von grundlegenden Konsolenprogrammen vollständige Windows-desktopanwendungen und mobilen apps zu erstellen.

Diese exemplarische Vorgehensweise zeigt, wie zum Erstellen einer einfachen, "Hello, World"-Stil C-Programm mit einem Text-Editor und kompilieren es dann in der Befehlszeile aus. Wenn Sie lieber in C++ in der Befehlszeile arbeiten, finden Sie unter [Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md). Wenn Sie möchten, um zu versuchen der Visual Studio-IDE, anstatt über die Befehlszeile finden Sie unter [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) oder [mithilfe von Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

## <a name="prerequisites"></a>Vorraussetzungen

Um diese exemplarische Vorgehensweise abgeschlossen haben, müssen Sie entweder Visual Studio und die optionalen Visual C++-Komponenten oder der Build-Tools für Visual Studio installiert haben.

Visual Studio ist eine leistungsfähige integrierte Entwicklungsumgebung, die einen Editor mit vollem Funktionsumfang, Ressourcen-Manager, Debugger und Compiler für viele Sprachen und Plattformen unterstützt. Informationen zu diesen Features und zum Herunterladen und installieren Sie Visual Studio, einschließlich der kostenlosen Visual Studio Community Edition finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).

Die Build-Tools für Visual Studio-Version von Visual Studio installiert nur das Befehlszeilen-Toolset, Compiler, Tools und Bibliotheken, die Sie zum Erstellen von C- und C++-Programmen benötigen. Es eignet sich ideal für Build-Laboren oder Classroom ausführt und relativ schnell installiert werden. Um nur befehlszeilentoolsets zu installieren, laden [Build-Tools für Visual Studio](https://go.microsoft.com/fwlink/p/?linkid=875721) und führen Sie den Installer.

Bevor Sie ein C- oder C++-Programm in der Befehlszeile erstellen können, müssen Sie überprüfen, dass die Tools installiert sind und Sie sie über die Befehlszeile zugreifen können. Visual C++ verfügt über komplexe Anforderungen für die Befehlszeilen-Umgebung finden Sie Tools, Header und Bibliotheken, die sie verwendet. **Sie können Visual C++ in einem einfachen Eingabeaufforderungsfenster verwenden** ohne einige Vorbereitungsschritte ausführen. Sie müssen eine *Developer-Eingabeaufforderung* Fenster, das eine normale Eingabeaufforderung-Fenster ist, die alle erforderlichen Umgebungsvariablen, die festgelegt wurde. Visual C++ installiert Glücklicherweise Tastenkombinationen für die Sie zum Starten von eingabeaufforderungen für Entwickler, die die Umgebung, die für Befehlszeilenbuilds eingerichtet haben. Leider sind die Namen von der Developer-Eingabeaufforderung Tastenkombinationen und, wo sie sich befinden sich in fast jeder Version von Visual C++ und in verschiedenen Versionen von Windows. Ihre erste Aufgabe der exemplarischen Vorgehensweise ist, suchen die richtige Verknüpfung verwenden.

> [!NOTE]
> Eine Developer-eingabeaufforderungsverknüpfung legt automatisch die richtigen Pfade für den Compiler und Tools, und für alle erforderlichen Header und Bibliotheken. Einige dieser Werte unterscheiden sich für jede Buildkonfiguration. Sie müssen diese Umgebungswerte selbst festlegen, wenn Sie eine der Verknüpfungen nicht verwenden. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Da die Buildumgebung komplex ist, wird dringend empfohlen, dass Sie eine Developer-eingabeaufforderungsverknüpfung verwenden, anstatt Ihre eigenen erstellen.

## <a name="open-a-developer-command-prompt"></a>Eine Developer-Eingabeaufforderung öffnen

1. Wenn Sie Visual Studio 2017 unter Windows 10 installiert haben, öffnen Sie im Menü Start, und scrollen Sie nach unten, und Öffnen der **Visual Studio 2017** Ordner (nicht der Visual Studio 2017-app). Wählen Sie **Developer-Eingabeaufforderung für Visual Studio 2017** im Eingabeaufforderungsfenster zu öffnen.

   Wenn Sie Microsoft Visual C++ Build Tools 2015 unter Windows 10 installiert haben, öffnen Sie die **starten** Menü, und klicken Sie dann führen Sie einen Bildlauf nach unten aus, und Öffnen der **Visual C++ Build Tools** Ordner. Wählen Sie **Visual C++ 2015 X86 Native Tools-Eingabeaufforderung** im Eingabeaufforderungsfenster zu öffnen.

   Wenn Sie eine andere Version von Visual Studio verwenden oder eine andere Version von Windows ausgeführt werden, suchen Sie im Startmenü oder -Startseite für den Ordner ein Visual Studio-Tools, der eine Developer-eingabeaufforderungsverknüpfung enthält. Sie können auch den Windows Search-Funktion verwenden, suchen Sie nach "Developer Command Prompt", und wählen Sie eine, die die installierte Version von Visual Studio entspricht. Verwenden Sie die Verknüpfung, um das Eingabeaufforderungsfenster zu öffnen.

1. Als Nächstes stellen Sie sicher, dass Visual C++ Developer-Eingabeaufforderung ordnungsgemäß eingerichtet ist. Geben Sie im Eingabeaufforderungsfenster Befehl `cl` und stellen Sie sicher, dass die Ausgabe sieht in etwa so:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Möglicherweise gibt es Unterschiede in der das aktuelle Verzeichnis oder Versionsnummern, abhängig von der Version von Visual C++ und alle Updates installiert. Ist die oben angegebene Ausgabe ähnelt, was Sie sehen, sind Sie bereit zum Erstellen von C- oder C++-Programme in der Befehlszeile.

   > [!NOTE]
   > Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten Sie beim Ausführen der **cl** Befehl, und klicken Sie dann entweder Sie eine Developer-Eingabeaufforderung nicht verwenden oder Es gibt es Probleme bei der Installation von Visual C++. Sie müssen dieses Problem beheben, bevor Sie fortfahren können.

   Wenn Sie die Developer-eingabeaufforderungsverknüpfung nicht finden oder wenn Sie eine Fehlermeldung erhalten, bei der Eingabe `cl`, und klicken Sie dann Visual C++-Installation ein Fehler vorliegt. Wenn Sie Visual Studio 2017 verwenden, installieren Sie erneut die **Desktopentwicklung mit C++** Workload im Visual Studio-Installer. Weitere Informationen finden Sie unter [Installieren von C++-Unterstützung in Visual Studio](../build/vscpp-step-0-installation.md). Oder Installieren der [Build-Tools für Visual Studio](https://go.microsoft.com/fwlink/p/?linkid=875721). Gehen Sie nicht auf mit dem nächsten Abschnitt bis dies funktioniert. Weitere Informationen zur Installation und Problembehandlung bei Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Abhängig von der Version von Windows auf dem Computer und der Systemsicherheitskonfiguration müssen Sie möglicherweise ein mit der rechten Maustaste das Kontextmenü für die Verknüpfung der Developer-Eingabeaufforderung öffnen, und wählen Sie dann **als Administrator ausführen** auf erfolgreich zu erstellen Sie, und führen Sie das Programm, das Sie anhand dieser exemplarischen Vorgehensweise erstellen.

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>Erstellen Sie eine C#-Quelldatei und kompilieren Sie diese in der Befehlszeile

1. Geben Sie in der Developer-Eingabeaufforderungsfenster, `cd c:\` so ändern Sie das aktuelle Arbeitsverzeichnis in das Stammverzeichnis von Laufwerk "c:". Geben Sie als Nächstes `md c:\simple` erstellen Sie ein Verzeichnis, und geben `cd c:\simple` so ändern Sie in diesem Verzeichnis. Dieses Verzeichnis wird die Quelldatei und das kompilierte Programm enthalten.

1. Geben Sie `notepad simple.c` an der Developer-Eingabeaufforderung. Wählen Sie in den Editor Dialogfeld "Warnung", die eingeblendet, **Ja** zum Erstellen einer neuen simple.c-Datei in Ihrem Arbeitsverzeichnis.

1. Geben Sie im Editor die folgenden Codezeilen ein:

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. Wählen Sie auf der Menüleiste von Editor **Datei** > **speichern** simple.c in Ihrem Arbeitsverzeichnis zu speichern.

1. Wechseln Sie in der Developer-Eingabeaufforderungsfenster. Geben Sie `dir` an der Eingabeaufforderung zum Auflisten des Inhalts des Verzeichnisses c:\simple. Sollte die Datei simple.c Quelle, in der verzeichnisauflistung, die in etwas so aussieht:

    ```Output
    C:\simple>dir
     Volume in drive C has no label.
     Volume Serial Number is CC62-6545

     Directory of C:\simple

    10/02/2017  03:46 PM    <DIR>          .
    10/02/2017  03:46 PM    <DIR>          ..
    10/02/2017  03:36 PM               143 simple.c
                   1 File(s)            143 bytes
                   2 Dir(s)  514,900,566,016 bytes free

    ```

   Die Datumsangaben und andere Details variieren auf Ihrem Computer. Wenn die Quellcodedatei nicht angezeigt wird, simple.c, stellen Sie sicher, dass Sie in das Verzeichnis von c:\simple erstellten geändert haben und in Editor, stellen Sie sicher, dass Sie die Quelldatei in diesem Verzeichnis gespeichert haben. Stellen Sie außerdem sicher, dass Sie den Quellcode mit einer Dateierweiterung .c enthält, nicht die Erweiterung TXT gespeichert.

1. Um das Programm zu kompilieren, geben Sie `cl simple.c` an der Developer-Eingabeaufforderung.

   Sie können der Name des ausführbaren Programms, simple.exe, in den Zeilen der Ausgabeinformationen, die der Compiler anzeigt, finden Sie unter:

    ```Output
    c:\simple>cl simple.c
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
    Copyright (C) Microsoft Corporation.  All rights reserved.

    simple.c
    Microsoft (R) Incremental Linker Version 14.10.25017.0
    Copyright (C) Microsoft Corporation.  All rights reserved.

    /out:simple.exe
    simple.obj
    ```

   > [!NOTE]
   > Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten, der Developer-Eingabeaufforderung nicht ordnungsgemäß eingerichtet. Informationen dazu, wie dieses Problem zu beheben, wechseln Sie zurück zu den **Developer-Eingabeaufforderung öffnen** Abschnitt.

   > [!NOTE]
   > Wenn Sie einen anderen Compiler oder Linker-Fehler oder Warnung erhalten, überprüfen Sie Ihren Quellcode zum Korrigieren Sie eventuelle Fehler, speichern Sie ihn, und führen den Compiler erneut aus. Informationen zu bestimmten Fehlern verwenden Sie das Suchfeld am oberen Rand dieser Seite nach der Fehlernummer gesucht werden soll.

1. Um das Programm ausführen, geben Sie `simple` an der Eingabeaufforderung.

   Das Programm zeigt folgenden Text an und wird anschließend beendet:

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   Herzlichen Glückwunsch, Sie kompiliert haben, und führen Sie ein C-Programm über die Befehlszeile.

## <a name="next-steps"></a>Nächste Schritte

In diesem Beispiel "Hello, World" ist ungefähr so einfach, wie ein C-Programm abrufen kann. Realen Programmen verfügen, Headerdateien und mehrere Quelldateien in Bibliotheken auf den link, und die Ausführungszeit sinnvoll nutzen.

Sie können die Schritte in dieser exemplarischen Vorgehensweise verwenden, um Ihren eigenen Code "C" anstatt den Beispielcode zu erstellen. Sie können auch viele C-Codebeispielprogramm erstellen, die Sie an anderer Stelle zu finden. Um ein Programm zu kompilieren, die über zusätzliche Quellcodedateien verfügt, geben Sie sie auf der Befehlszeile angeben, wie:

`cl file1.c file2.c file3.c`

Der Compiler gibt ein Programm namens file1.exe. Um den Namen in program1.exe zu ändern, Hinzufügen einer [/out](../build/reference/out-output-file-name.md) (Linkeroption):

`cl file1.c file2.c file3.c /link /out:program1.exe`

Um weitere Programmierfehler automatisch abzufangen, sollten Sie kompilieren, indem Sie entweder die [/w3](../build/reference/compiler-option-warning-level.md) oder [/W4](../build/reference/compiler-option-warning-level.md) aus:

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

Der Compiler, die cl.exe, verfügt über viele weitere Optionen, die Sie anwenden, um das Erstellen, zu optimieren, Debuggen und Analysieren von Code können. Geben Sie für eine kurze Liste `cl /?` an der Developer-Eingabeaufforderung. Sie können auch kompilieren und separat zu verknüpfen und Optionen des Linkers in komplexere Buildszenarios anwenden. Weitere Informationen für Compiler und Optionen des Linkers und Verwendung finden Sie unter [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md).

Sie können MSBuild und Projektdateien und Makefiles oder NMAKE verwenden, konfigurieren und komplexere Projekte in der Befehlszeile erstellen. Weitere Informationen zur Verwendung dieser Tools finden Sie unter [NMAKE-Referenz](../build/nmake-reference.md) und [MSBuild](../build/msbuild-visual-cpp.md).

Die Programmiersprachen C und C++ sind ähnlich, jedoch nicht identisch. Visual C++-Compiler verwendet eine einfache Regel, um zu bestimmen, welche Sprache verwendet, wenn sie Ihren Code kompiliert wird. Standardmäßig behandelt der Visual C++-Compiler alle auf .c endenden Dateien als C-Quellcode und alle auf .cpp endenden Dateien als C++-Quellcode. Verwenden Sie zum Erzwingen des Compilers alle Dateien als C unabhängige der Dateinamenerweiterung behandelt die [/TC](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) -Compileroption.

Der Visual C++-C-Compiler ist mit dem ISO C99-Standard kompatibel ist, aber nicht unbedingt kompatibel. In den meisten Fällen portablen C++-Code kompiliert und wie erwartet ausgeführt werden. Visual C++ unterstützt nicht die meisten der Änderungen im ISO C11. Bestimmte Bibliotheksfunktionen und POSIX-Funktionsnamen werden vom Visual C++-Compiler als veraltet markiert. Die Funktionen werden unterstützt, aber die Namen der bevorzugten wurden geändert. Weitere Informationen finden Sie unter [Sicherheitsfunktionen in CRT](../c-runtime-library/security-features-in-the-crt.md) und [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Erstellen eines Standard C++-Konsolenprogramms (C++)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C-Sprachreferenz](../c-language/c-language-reference.md)<br/>
[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)<br/>
[Kompatibilität](../c-runtime-library/compatibility.md)
