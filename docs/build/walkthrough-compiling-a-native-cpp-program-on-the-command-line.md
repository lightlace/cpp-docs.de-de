---
title: 'Exemplarische Vorgehensweise: Kompilieren eines System C++ eigenen Programms in der Befehlszeile'
description: Verwenden Sie den C++ Microsoft-Compiler über eine Eingabeaufforderung.
ms.custom: conceptual
ms.date: 04/23/2019
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: 36017b28ab91478da2515cd7c8588a998013171d
ms.sourcegitcommit: c53a3efcc5d51fc55fa57ac83cca796b33ae888f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71960719"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>Exemplarische Vorgehensweise: Kompilieren eines System C++ eigenen Programms in der Befehlszeile

Visual Studio enthält einen Befehlszeilen C++ Compiler, mit dem Sie alles aus grundlegenden Konsolen-apps zu universelle Windows-Plattform-apps, Desktop-Apps, Gerätetreibern und .NET-Komponenten erstellen können.

In dieser exemplarischen Vorgehensweise C++ erstellen Sie ein einfaches Programm "Hello, World" mit einem Text-Editor und kompilieren es dann in der Befehlszeile. Wenn Sie die Visual Studio-IDE testen möchten, anstatt die Befehlszeile zu verwenden, finden Sie weitere Informationen unter [walkthrough: Arbeiten mit Projekten und Projektmappen (C++) ](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) oder [der Verwendung der Visual C++ Studio-IDE für die Desktop Entwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

In dieser exemplarischen Vorgehensweise können Sie Ihr eigenes Visual C++-Programm verwenden, statt das gezeigte einzugeben, oder Sie können ein Visual C++-Codebeispiel aus einem anderen Hilfeartikel verwenden.

## <a name="prerequisites"></a>Erforderliche Komponenten

Um diese exemplarische Vorgehensweise durchführen zu können, müssen Sie entweder Visual Studio und die optionale **Desktop Entwicklung mit C++**  der Arbeitsauslastung oder die Befehlszeilen-Buildtools für Visual Studio installiert haben.

Visual Studio ist eine leistungsfähige integrierte Entwicklungsumgebung (Integrated Development Environment, IDE), die einen voll funktionsfähigen Editor, Ressourcen-Manager, Debugger und Compiler für viele Sprachen und Plattformen unterstützt. Weitere Informationen zum herunterladen und Installieren von Visual Studio, einschließlich der kostenlosen Visual Studio Community Edition, sowie zur Unterstützung für CC++ /Development finden Sie [unter Installieren C++ der Unterstützung in Visual Studio](vscpp-step-0-installation.md).

Die Buildtools für Visual Studio installieren nur die Befehlszeilen Compiler, Tools und Bibliotheken, die Sie benötigen, um C und C++ Programme zu erstellen. Es eignet sich ideal für buildlabs oder Schulungs Übungen und die Installation relativ schnell. Um nur die Befehlszeilen Tools zu installieren, suchen Sie auf der [Visual Studio-Download](https://visualstudio.microsoft.com/downloads/) Seite nach Buildtools für Visual Studio.

Bevor Sie ein C-oder C++ -Programm in der Befehlszeile erstellen können, müssen Sie sicherstellen, dass die Tools installiert sind und dass Sie über die Befehlszeile darauf zugreifen können. Visual C++ hat komplexe Anforderungen an die Befehlszeilen Umgebung, um die verwendeten Tools, Header und Bibliotheken zu finden. Das **visuelle C++ Element kann nicht in einem einfachen Eingabe** Aufforderungs Fenster ohne Vorbereitung verwendet werden. Glücklicherweise installiert Visual C++ die Tastenkombinationen, um eine Developer-Eingabeaufforderung zu starten, in der die Umgebung für Befehlszeilenbuilds eingerichtet ist. Leider unterscheiden sich die Namen der Verknüpfungen für Entwickler-Eingabe Aufforderungen und deren Position in nahezu jeder Version von C++ Visual und unterschiedlichen Versionen von Windows. Die erste Exemplarische Vorgehensweise ist die Suche nach dem richtigen zu verwendenden.

> [!NOTE]
> Eine Eingabe Aufforderungs Verknüpfung für Entwickler legt automatisch die richtigen Pfade für den Compiler und die Tools sowie für alle erforderlichen Header und Bibliotheken fest. Sie müssen diese Umgebungs Werte selbst festlegen, wenn Sie ein reguläres **Eingabe** Aufforderungs Fenster verwenden. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](setting-the-path-and-environment-variables-for-command-line-builds.md). Es wird empfohlen, dass Sie eine Eingabeaufforderung für Entwickler verwenden, anstatt ihre eigenen zu entwickeln.

### <a name="open-a-developer-command-prompt"></a>Öffnen Sie eine Developer-Eingabeaufforderung.

1. Wenn Sie Visual Studio 2017 oder höher unter Windows 10 installiert haben, öffnen Sie das Startmenü, und wählen Sie **alle apps**aus. Scrollen Sie nach unten, und öffnen Sie den **Visual Studio** -Ordner (nicht die Visual Studio-Anwendung). Wählen Sie **Developer-Eingabeaufforderung für vs aus** , um das Eingabe Aufforderungs Fenster zu öffnen.

   Wenn Sie Microsoft Visual C++ Build Tools 2015 unter Windows 10 installiert haben, öffnen Sie **das Startmenü** , und wählen Sie **alle apps**aus. Scrollen Sie nach unten, und öffnen Sie den Ordner  **C++ Visual Build Tools** . Wählen **Sie C++ Visual 2015 x86 Native Tools-Eingabeaufforderung** aus, um das Eingabe Aufforderungs Fenster zu öffnen.

   Sie können auch die Windows Search-Funktion verwenden, um nach "Developer Command Prompt" zu suchen und eine solche auszuwählen, die mit der installierten Version von Visual Studio übereinstimmt. Verwenden Sie die Verknüpfung, um das Eingabe Aufforderungs Fenster zu öffnen.

1. Überprüfen Sie als nächstes, C++ ob die Visual Developer-Eingabeaufforderung ordnungsgemäß eingerichtet ist. Geben Sie im Eingabe Aufforderungs Fenster `cl` ein, und überprüfen Sie, ob die Ausgabe in etwa wie folgt aussieht:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Abhängig von der Version von Visual C++ und allen installierten Updates gibt es möglicherweise Unterschiede in den aktuellen Verzeichnis-oder Versionsnummern. Wenn die oben genannte Ausgabe ähnlich aussieht wie Sie sehen, können Sie C-oder C++ -Programme in der Befehlszeile erstellen.

   > [!NOTE]
   > Wenn ein Fehler wie "CL" nicht als interner oder externer Befehl, ausführbares Programm oder eine Batchdatei (Fehler C1034 oder Fehler LNK1104 erkannt wird, wenn Sie den **cl** -Befehl ausführen, wird entweder keine Entwickler-Eingabeaufforderung verwendet, oder etwas ist falsch. mit Ihrer Installation von Visual C++. Sie müssen dieses Problem beheben, bevor Sie fortfahren können.

   Wenn Sie die Verknüpfung für Entwickler-Eingabe Aufforderungen nicht finden oder wenn Sie eine Fehlermeldung erhalten, wenn Sie `cl` eingeben, C++ tritt bei der visuellen Installation möglicherweise ein Problem auf. Versuchen Sie, die visuelle C++ Komponente in Visual Studio erneut zu installieren, oder installieren Sie C++ Microsoft Visual Build Tools neu. Fahren Sie nicht mit dem nächsten Abschnitt fort, bis dies funktioniert. Weitere Informationen zur Installation und Problembehandlung in C++Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Abhängig von der Windows-Version auf dem Computer und der System Sicherheitskonfiguration müssen Sie möglicherweise mit der rechten Maustaste klicken, um das Kontextmenü für die Eingabeaufforderung für Entwickler-Eingabeaufforderung zu öffnen. Wählen Sie dann **als Administrator ausführen** aus, um erfolgreich zu erstellen und auszuführen. Das Programm, das Sie nach dieser exemplarischen Vorgehensweise erstellen.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Erstellen einer visuellen C++ Quelldatei und Kompilieren in der Befehlszeile

1. Geben Sie im Eingabe Aufforderungs Fenster des Entwicklers `md c:\hello` ein, um ein Verzeichnis zu erstellen, und geben Sie dann `cd c:\hello` ein, um zu diesem Verzeichnis zu wechseln. In diesem Verzeichnis werden die Quelldatei und das kompilierte Programm in erstellt.

1. Geben Sie im Eingabe Aufforderungs Fenster `notepad hello.cpp` ein.

   Wählen Sie **Ja** aus, wenn Sie von Notepad aufgefordert werden, eine Datei zu erstellen. In diesem Schritt wird ein leeres Editor Fenster geöffnet, in dem Sie Ihren Code in eine Datei mit dem Namen Hello. cpp eingeben können.

1. Geben Sie im Editor die folgenden Codezeilen ein:

   ```cpp
   #include <iostream>
   using namespace std;
   void main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   Bei diesem Code handelt es sich um ein einfaches Programm, das eine Textzeile auf dem Bildschirm schreibt und dann beendet wird. Um Fehler zu minimieren, kopieren Sie diesen Code, und fügen Sie ihn in Editor ein.

1. Speichern Sie Ihre Arbeit. Wählen Sie im Editor im Menü **Datei** den Befehl **Speichern**aus.

   Herzlichen Glückwunsch, Sie haben C++ die Quelldatei "Hello. cpp" erstellt, die kompiliert werden kann.

1. Wechseln Sie zurück zum Entwickler-Eingabe Aufforderungs Fenster. Geben Sie `dir` an der Eingabeaufforderung ein, um den Inhalt des Verzeichnisses "c:\hello" aufzulisten. Die Quelldatei "Hello. cpp" sollte in der Verzeichnis Auflistung angezeigt werden, was etwa wie folgt aussieht:

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

   Die Datumsangaben und andere Details unterscheiden sich auf Ihrem Computer. Wenn die Quell Code Datei "Hello. cpp" nicht angezeigt wird, stellen Sie sicher, dass Sie das Verzeichnis "c:\hello" geändert haben, das Sie erstellt haben, und stellen Sie sicher, dass Sie die Quelldatei in diesem Verzeichnis gespeichert haben. Stellen Sie außerdem sicher, dass Sie den Quellcode mit der Dateinamenerweiterung ". cpp" und nicht mit der Erweiterung ". txt" gespeichert haben.

1. Geben Sie an der Developer-Eingabeaufforderung `cl /EHsc hello.cpp` ein, um das Programm zu kompilieren.

   Der cl.exe-Compiler generiert eine OBJ-Datei, die den kompilierten Code enthält, und führt dann den Linker aus, um ein ausführbares Programm namens „hello.exe“ zu erstellen. Dieser Name wird in den Zeilen der Ausgabeinformationen angezeigt, die der Compiler anzeigt. Die Ausgabe des Compilers sollte in etwa wie folgt aussehen:

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
   > Wenn Sie einen Fehler wie "CL" erhalten, der nicht als interner oder externer Befehl, ausführbares Programm oder eine Batchdatei (Fehler C1034 oder Fehler LNK1104) erkannt wird, ist die Entwickler-Eingabeaufforderung nicht ordnungsgemäß eingerichtet. Weitere Informationen zum Beheben dieses Problems finden Sie im Abschnitt **Öffnen einer Developer-Eingabeaufforderung** .

   > [!NOTE]
   > Wenn Sie einen anderen Compiler oder Linker-Fehler oder eine andere Warnung erhalten, überprüfen Sie den Quellcode, um alle Fehler zu beheben, speichern Sie ihn, und führen Sie den Compiler erneut aus. Um Informationen zu bestimmten Fehlern zu erhalten, verwenden Sie das Suchfeld auf dieser MSDN-Seite, um nach der Fehlernummer zu suchen.

1. Geben Sie zum Ausführen des hello.exe-Programms an der Eingabeaufforderung `hello`ein.

   Das Programm zeigt folgenden Text an und wird anschließend beendet:

   ```Output
   Hello, world, from Visual C++!
   ```

   Herzlichen Glückwunsch, Sie haben ein C++ Programm mit den Befehlszeilen Tools kompiliert und ausgeführt.

## <a name="next-steps"></a>Nächste Schritte

Dieses "Hello, World"-Beispiel ist so einfach wie ein C++ Programm. In realen Programmen sind Header Dateien und weitere Quelldateien vorhanden, die in Bibliotheken verknüpft sind und nützliche Arbeiten bewirken.

Sie können die Schritte in dieser exemplarischen Vorgehensweise verwenden, um C++ ihren eigenen Code zu erstellen, anstatt den gezeigten Beispielcode einzugeben. Sie können auch viele C++ Codebeispiel Programme erstellen, die Sie an anderer Stelle finden. Sie können Ihren Quellcode platzieren und ihre apps in jedem beschreibbaren Verzeichnis erstellen. Standardmäßig erstellt die Visual Studio-IDE Projekte im Ordner "Dokumente" im Unterordner "Projekte" eines Visual Studio-Ordners, der für Ihre Version von Visual Studio benannt ist.

Wenn Sie ein Programm mit zusätzlichen Quell Code Dateien kompilieren möchten, geben Sie alle in der Befehlszeile ein, z. b.:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

Die `/EHsc`-Befehlszeilenoption weist den Compiler an, die C++-Ausnahmebehandlung zu aktivieren. Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](reference/eh-exception-handling-model.md).

Wenn Sie zusätzliche Quelldateien angeben, verwendet der Compiler die erste Eingabedatei zum Erstellen des Programm namens. In diesem Fall wird ein Programm mit dem Namen file1. exe ausgegeben. Um den Namen in Program1. exe zu ändern, fügen Sie eine [/out](reference/out-output-file-name.md) Linker-Option hinzu:

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Um automatisch mehr Programmierfehler zu erfassen, empfiehlt es sich, die Kompilierung entweder mithilfe der [/w3](reference/compiler-option-warning-level.md) -Option oder der [/W4](reference/compiler-option-warning-level.md) -Warnstufe zu kompilieren:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Der Compiler "CL. exe" verfügt über viele weitere Optionen, die Sie zum Erstellen, optimieren, Debuggen und analysieren Ihres Codes anwenden können. Geben Sie `cl /?` an der Developer-Eingabeaufforderung ein, um eine kurze Liste zu erhalten. Sie können auch separat kompilieren und verknüpfen und Linkeroptionen in komplexeren Buildszenarien anwenden. Weitere Informationen zu den Optionen und der Verwendung von Compileroptionen und Linkeroptionen finden Sie unter [C/C++ Building Reference](reference/c-cpp-building-reference.md).

Sie können NMAKE-und Makefiles-oder MSBuild-und Projektdateien verwenden, um komplexere Projekte in der Befehlszeile zu konfigurieren und zu erstellen. Weitere Informationen zur Verwendung dieser Tools finden Sie unter [NMAKE Reference](reference/nmake-reference.md) und [MSBuild](msbuild-visual-cpp.md).

Die C- C++ und-Sprachen sind ähnlich, aber nicht identisch. Der MSVC-Compiler verwendet eine einfache Regel, um zu bestimmen, welche Sprache verwendet werden soll, wenn der Code kompiliert wird. Standardmäßig behandelt der MSVC-Compiler alle Dateien, die mit. c enden, als c-Quellcode und alle Dateien, die auf. cpp C++ enden, als Quellcode. Verwenden Sie die [/tp](reference/tc-tp-tc-tp-specify-source-file-type.md) -Compileroption, C++ um zu erzwingen, dass der Compiler alle Dateien als nicht-abhängig von der Dateinamenerweiterung behandelt.

Der MSVC-Compiler enthält eine C-Lauf Zeit Bibliothek (C Runtime Library, CRT), die mit dem ISO C99-Standard kompatibel ist, jedoch nicht streng kompatibel ist In den meisten Fällen wird portabler Code kompiliert und erwartungsgemäß ausgeführt. Visual C++ unterstützt einige der CRT-Änderungen in ISO C11 nicht. Bestimmte Bibliotheksfunktionen und POSIX-Funktionsnamen werden vom MSVC-Compiler als veraltet markiert. Die Funktionen werden unterstützt, aber die bevorzugten Namen wurden geändert. Weitere Informationen finden Sie unter [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md) und [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Projekte und Buildsysteme](projects-and-build-systems-cpp.md)<br/>
[MSVC-Compileroptionen](reference/compiler-options.md)
