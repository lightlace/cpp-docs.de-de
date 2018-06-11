---
title: 'Exemplarische Vorgehensweise: Kompilieren ein C-Programms in der Befehlszeile | Microsoft Docs'
ms.custom: conceptual
ms.date: 06/08/2018
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
ms.openlocfilehash: 27e303a9e1618c73d173e9d23c614cfc506ec68a
ms.sourcegitcommit: 1c2e035f98fb55d9b3c08ec3bb562179a368d0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35253788"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile
Visual C++ enthält einen C-Compiler, den Sie verwenden können, um alles von grundlegenden Konsolenprogrammen an eine vollständige Windows-desktopanwendungen und mobiler apps erstellen.  
  
 In dieser exemplarischen Vorgehensweise wird gezeigt, wie zum Erstellen einer grundlegenden, "Hello, World"-Stil C-Programm mit einem Text-Editor und kompilieren es dann in der Befehlszeile angegeben. Wenn Sie lieber in C++ in der Befehlszeile arbeiten, finden Sie unter [Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md). Wenn Sie möchten, um zu versuchen das Visual Studio-IDE statt über die Befehlszeile finden Sie unter [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) oder [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten

Um diese exemplarische Vorgehensweise abgeschlossen haben, müssen Sie entweder Visual Studio und die optionalen Visual C++-Komponenten oder die Build-Tools für Visual Studio installiert haben.  
  
Visual Studio ist eine leistungsstarke integrierte Entwicklungsumgebung, die einem voll ausgestatteten-Editor, Ressourcen-Manager, Debugger und Compilern für viele Sprachen und Plattformen unterstützt. Informationen zu diesen Funktionen und zum Herunterladen und Installieren von Visual Studio, einschließlich der kostenlosen Visual Studio Community Edition finden Sie unter [installieren Sie Visual Studio](/visualstudio/install/install-visual-studio).  
  
Der Build-Tools für Visual Studio-Version von Visual Studio installiert nur befehlszeilentoolsets, Compiler, Tools und Bibliotheken, die zum Erstellen von C und C++-Programmen erforderlich. Ist es perfekt für Build Labs oder Schulungsraum ausführt und relativ schnell installiert. Laden Sie zum Installieren nur befehlszeilentoolsets [Build-Tools für Visual Studio](https://go.microsoft.com/fwlink/p/?linkid=840931) und führen Sie das Installationsprogramm.  
  
Bevor Sie eine C- oder C++-Programm in der Befehlszeile erstellen können, müssen Sie sicherstellen, dass die Verwaltungstools installiert sind und Sie sie über die Befehlszeile zugreifen können. Visual C++ stellt komplexe Anforderungen an die befehlszeilenumgebung zum Suchen von Tools, Header und Bibliotheken, die verwendet. **Sie können Visual C++ in einem einfachen Eingabeaufforderungsfenster verwenden**. Sie müssen eine *entwicklereingabeaufforderung* im Fenster eine reguläre Eingabeaufforderungsfenster ein, die alle erforderlichen Umgebungsvariablen, die festgelegt wurde. Visual C++ installiert Glücklicherweise Tastenkombinationen für die Developer-Eingabeaufforderungsfenster geöffnet, in dem die Umgebung für Befehlszeilenbuilds eingerichtet haben. Leider sind die Namen der Verknüpfungen mit der Developer-Eingabeaufforderung und wo sich diese befinden sich in fast jeder Version von Visual C++ und in verschiedenen Versionen von Windows. Die erste Aufgabe für die exemplarische Vorgehensweise ist, suchen die richtige Verknüpfung verwenden.  
  
> [!NOTE]
> Eine Developer-eingabeaufforderungsverknüpfung legt automatisch die richtigen Pfade für den Compiler und Tools, und für alle erforderlichen Header und Bibliotheken. Einige dieser Werte sind für jede Buildkonfiguration, unterschiedlich. Sie müssen diese Umgebungswerte festgelegt selbst, wenn Sie nicht eine der Tastenkombinationen verwenden. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Da die Buildumgebung komplex ist, wird dringend empfohlen, dass Sie eine Developer-eingabeaufforderungsverknüpfung verwenden, anstatt eine eigene erstellen.  
  
## <a name="open-a-developer-command-prompt"></a>Öffnen Sie eine Developer-Eingabeaufforderung  
  
1.  Wenn Sie Visual Studio 2017 unter Windows 10 installiert haben, öffnen Sie das Menü Start, und klicken Sie dann einen Bildlauf nach unten, und Öffnen der **Visual Studio 2017** Ordner (nicht die Visual Studio-2017-app). Wählen Sie **Developer-Eingabeaufforderung für VS 2017** im Eingabeaufforderungsfenster zu öffnen.  
  
     Wenn Sie Microsoft Visual C++ erstellen Tools 2015 für Windows 10 installiert haben, öffnen Sie die **starten** Menü, und klicken Sie dann einen Bildlauf nach unten aus, und Öffnen der **Visual C++-Buildtools** Ordner. Wählen Sie **Visual C++ 2015 X86 Native Tools-Eingabeaufforderung** im Eingabeaufforderungsfenster zu öffnen.  
  
     Wenn Sie eine andere Version von Visual Studio verwenden oder eine andere Version von Windows ausgeführt werden, suchen Sie im Startmenü oder Startseite für einen Ordner der Visual Studio-Tools, der eine Developer-eingabeaufforderungsverknüpfung enthält. Sie können auch die Windows Search-Funktion verwenden, suchen Sie nach "Developer-Eingabeaufforderung", und wählen eine, die die installierte Version von Visual Studio entspricht. Verwenden Sie die Verknüpfung, um das Eingabeaufforderungsfenster zu öffnen.  
  
2.  Als Nächstes stellen Sie sicher, dass Visual C++ Developer-Eingabeaufforderung ordnungsgemäß eingerichtet ist. Geben Sie in das Eingabeaufforderungsfenster `cl` und stellen Sie sicher, dass die Ausgabe etwa wie folgt sieht:  
  
    ```Output  
    C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl  
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86  
    Copyright (C) Microsoft Corporation.  All rights reserved.  
    
    usage: cl [ option... ] filename... [ /link linkoption... ]  
    
    C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>  
    ```  
  
     Möglicherweise gibt es Unterschiede in der aktuellen Verzeichnis oder Versionsnummern, abhängig von der Version von Visual C++ und alle Updates installiert. Wenn dies gleicht dem, was Sie sehen, sind Sie bereit für C- oder C++-Programme in der Befehlszeile zu erstellen.  
  
    > [!NOTE]
    >  Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als ein interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten Sie beim Ausführen der **cl** Befehl, und klicken Sie dann entweder Sie eine Developer-Eingabeaufforderung nicht verwenden oder etwas stimmt nicht mit der Installation von Visual C++. Sie müssen dieses Problem beheben, bevor Sie fortfahren können.  
  
     Wenn Sie die Developer-eingabeaufforderungsverknüpfung finden können, oder wenn Sie eine Fehlermeldung erhalten, bei der Eingabe `cl`, und klicken Sie dann Visual C++-Installation ein Fehler vorliegt. Installieren Sie die Visual C++-Komponente in Visual Studio erneut, oder installieren Sie die Build-Tools für Visual Studio. Nicht fahren Sie mit dem nächsten Abschnitt bis dies funktioniert. Weitere Informationen zur Installation und Problembehandlung bei Visual Studio finden Sie unter [installieren Sie Visual Studio](/visualstudio/install/install-visual-studio).  
  
    > [!NOTE]
    >  Je nach Version von Windows auf dem Computer und der Systemsicherheitskonfiguration müssen Sie möglicherweise mit der rechten Maustaste öffnen Sie das Kontextmenü für die Developer-eingabeaufforderungsverknüpfung, und wählen Sie dann **als Administrator ausführen** an Erstellen und das Programm, das Sie erstellen, indem Sie in dieser exemplarischen Vorgehensweise auszuführen.  
  
## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>Erstellen Sie eine C#-Quelldatei und kompilieren Sie diese über die Befehlszeile  
  
1.  In der Developer-Eingabeaufforderungsfenster, geben Sie **cd "c:"\\**  so ändern Sie das aktuelle Arbeitsverzeichnis auf den Stamm von Laufwerk "c:". Geben Sie anschließend **Md c:\simple** , erstellen Sie ein Verzeichnis aus, und geben dann **cd c:\simple** so ändern Sie in diesem Verzeichnis. Dies ist das Verzeichnis, das die Quelldatei und das kompilierte Programm enthält.  
  
2.  Geben Sie **Editor simple.c** an der Developer-Eingabeaufforderung. Wählen Sie in den Editor Dialogfeld Warnung angezeigt wird, **Ja** zum Erstellen einer neuen simple.c-Datei in Ihrem Arbeitsverzeichnis.  
  
3.  Geben Sie in Editor die folgenden Codezeilen ein:  
  
    ```C  
    #include <stdio.h>  
  
    int main()  
    {  
        printf("Hello, World! This is a native C program compiled on the command line.\n");  
        return 0;  
    }   
    ```  
  
4.  Wählen Sie in der Menüleiste von Editor **Datei**, **speichern** simple.c in Ihrem Arbeitsverzeichnis zu speichern.  
  
5.  Wechseln Sie in der Developer-Eingabeaufforderungsfenster. Geben Sie **Dir** an der Eingabeaufforderung aus, um den Inhalt des Verzeichnisses c:\simple aufzulisten. Die Quelle Datei simple.c in der Verzeichnisliste die etwa wie folgt aussieht, sollte angezeigt werden:  
  
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
  
     Die Datumsangaben und andere Details werden auf Ihrem Computer abweichen. Wenn die Quellcodedatei nicht angezeigt wird, wird simple.c, stellen Sie sicher, dass Sie in das Verzeichnis von c:\simple erstellten geändert haben und im Editor, stellen sicher, dass Sie die Quelldatei in diesem Verzeichnis gespeichert. Stellen Sie außerdem sicher, dass Sie den Quellcode mit .c Dateinamenerweiterung nicht die Erweiterung TXT gespeichert.  
  
6.  Um das Programm zu kompilieren, geben Sie **cl simple.c** an der Developer-Eingabeaufforderung.  
  
     Sie können der Name des ausführbaren Programms, simple.exe, in den Zeilen der Ausgabeinformationen anzeigen, die der Compiler anzeigt:  
  
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
    >  Wenn Sie eine Fehlermeldung erhalten, wie z. B. "'cl' nicht als ein interner oder externer Befehl, ausführbares Programm oder Batchdatei erkannt", Fehler C1034 oder Fehler LNK1104 erhalten, die Developer-Eingabeaufforderung nicht ordnungsgemäß eingerichtet. Informationen zu diesem Problem zu beheben, wechseln Sie zurück zu den **Developer-Eingabeaufforderung öffnen** Abschnitt.  
  
    > [!NOTE]
    >  Wenn Sie einen anderen Compiler oder Linkerfehler oder eine Warnung erhalten, überprüfen Sie den Quellcode zum Beheben alle Fehler, speichern Sie es und führen Sie den Compiler erneut aus. Informationen zu bestimmten Fehlern verwenden Sie das Suchfeld auf diesem MSDN-Seite für die dazu gehörende Nummer gesucht werden soll.  
  
7.  Um das Programm auszuführen, geben Sie **einfache** an der Eingabeaufforderung.  
  
     Das Programm zeigt folgenden Text an und wird anschließend beendet:  
  
    ```Output  
    Hello, World! This is a native C program compiled on the command line.  
    ```  
  
     Herzlichen Glückwunsch, Sie haben gerade kompiliert und einem C-Programm mithilfe der Befehlszeile ausführen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In diesem Beispiel "Hello, World" ist ungefähr so einfach wie ein C-Programm erhalten kann. Reales Programme haben Headerdateien und weitere Quelldateien in Bibliotheken verknüpfen, und führen Sie sinnvolle Arbeit.  
  
 Sie können die Schritte in dieser exemplarischen Vorgehensweise verwenden, erstellen Sie einen eigene C-Code statt den Beispielcode einzugeben. Sie können auch viele C-Codebeispielprogramm erstellen, die Sie an anderer Stelle zu finden. Um ein Programm zu kompilieren, die mehrere Quellcodedateien verfügt, geben Sie sie alle in der Befehlszeile angegeben, wie folgt aus:  
  
 `cl file1.c file2.c file3.c`  
  
 Der Compiler gibt ein Programm namens file1.exe. Fügen Sie zum Ändern des Namens auf program1.exe ein [/out](../build/reference/out-output-file-name.md) (Linkeroption):  
  
 `cl file1.c file2.c file3.c /link /out:program1.exe`  
  
 Und wenn Sie um weitere Programmierfehler automatisch zu erfassen, sollten Sie kompilieren, indem Sie entweder die [/W3](../build/reference/compiler-option-warning-level.md) oder [/W4](../build/reference/compiler-option-warning-level.md) aus:  
  
 `cl /W4 file1.c file2.c file3.c /link /out:program1.exe`  
  
 Der Compiler, die cl.exe, verfügt über viele weitere Optionen können Sie anwenden, um "erstellen", zu optimieren, Debuggen und Analysieren von Code. Geben Sie eine kurze Liste **cl /?** an der Developer-Eingabeaufforderung. Sie können auch kompilieren und verknüpfen separat und Optionen des Linkers in komplexeren Buildszenarien anwenden. Weitere Informationen für Compiler und Linkeroptionen und Verwendung finden Sie unter [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md).  
  
 Sie können NMAKE und Makefiles oder MSBuild und Projektdateien zu konfigurieren und zum Erstellen komplexerer Projekte in der Befehlszeile verwenden. Weitere Informationen zur Verwendung dieser Tools finden Sie unter [NMAKE-Referenz](../build/nmake-reference.md) und [MSBuild](../build/msbuild-visual-cpp.md).  
  
 Die Programmiersprachen C und C++ sind ähnlich, aber nicht identisch. Visual C++-Compiler verwendet eine einfache Regel, um zu bestimmen, welche Sprache verwendet, wenn den Code kompiliert wird. Standardmäßig behandelt der Visual C++-Compiler alle auf .c endenden Dateien als C-Quellcode und alle auf .cpp endenden Dateien als C++-Quellcode. Verwenden Sie zum Erzwingen des Compilers alle Dateien unabhängig von der Dateinamenerweiterung als C behandelt die [/TC](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) -Compileroption.  
  
 Der Visual C++ C-Compiler ist im Allgemeinen mit ISO C99-Standard kompatibel, aber nicht unbedingt kompatibel. In den meisten Fällen wird portable C#-Code kompilieren und wie erwartet ausgeführt werden. Visual C++ unterstützt nicht die meisten der Änderungen im ISO-C11. Bestimmte Bibliotheksfunktionen und das POSIX-Funktionsnamen werden vom Visual C++-Compiler als veraltet markiert. Die Funktionen werden unterstützt, aber die Namen der bevorzugten wurden geändert. Weitere Informationen finden Sie unter [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md) und [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen eines standardmäßigen C++-Programms (C++)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)   
 [C-Sprachreferenz](../c-language/c-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)   
 [Kompatibilität](../c-runtime-library/compatibility.md)