---
title: Einführung in Microsoft C++ für UNIX-Benutzer
ms.date: 10/23/2019
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
ms.openlocfilehash: 791c513553acbd300204746ae1e1dddf7a3ae5c4
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626989"
---
# <a name="introduction-to-microsoft-c-for-unix-users"></a>Einführung in Microsoft C++ für UNIX-Benutzer

Dieses Thema enthält Informationen für Benutzer aller UNIX-UNIX-Versionen, die mit Visual Studio noch nicht vertraut sind und sich C++ entweder über die Befehlszeile oder mithilfe von Visual Studio produktiv einsetzen möchten. Mithilfe von Visual Studio mit dem Microsoft C++ -Compiler können Sie Windows als Ziel verwenden. Sie können auch die Visual Studio-IDE mit gcc oder clang in UNIX-Umgebungen verwenden, wie z. b. Linux-Remote Computern, MinGW-W64 und Windows-Subsystem für Linux. Um in C++ Visual Studio verwenden zu können, muss die **Desktop Entwicklung mit C++**  Arbeitsauslastung installiert sein. Öffnen Sie die Visual Studio-Installer, um die Arbeitsauslastung zu installieren oder optionale Komponenten hinzuzufügen oder zu entfernen. Installieren Sie auch die **Linux- C++ Entwicklung mit** der Arbeitsauslastung, wenn Sie einen Linux-Remote Computer als Ziel haben. Installieren Sie bei der Android-oder IOS-Entwicklung die **Mobile-Entwicklung mit C++**  der Arbeitsauslastung.

## <a name="getting-started-on-the-command-line"></a>Ersten Einstieg in der Befehlszeile

Sie können den Microsoft C++ -Compiler von der Befehlszeile aus auf ähnliche Weise wie eine UNIX-Befehlszeilen Umgebung verwenden. Die Kompilierung erfolgt mithilfe der Eingabeaufforderung mit dem C/C++-Befehlszeilencompiler (CL.EXE), dem Linker (LINK.EXE) und weiteren Tools, darunter NMAKE.EXE, der Microsoft-Version des UNIX-Dienstprogramms Make.

Unter UNIX werden Befehle in einem gemeinsam genutzten Ordner, z. B. /usr/bin, installiert. In Visual Studio werden die Befehlszeilentools in Ihrem Visual Studio-Installationsverzeichnis im Unterverzeichnis „VC\bin“ und seinen Unterverzeichnissen installiert. Im Gegensatz zu UNIX sind diese Tools nicht in einem einfachen Eingabeaufforderungsfenster verfügbar. Um die Befehlszeilen Tools verwenden zu können, müssen Sie eine spezielle Entwickler Eingabeaufforderung verwenden, mit der der Pfad und andere Umgebungsvariablen eingerichtet werden, die C++ zum Kompilieren von Programmen benötigt werden. Weitere Informationen finden Sie unter [Erstellen von C/C++-Code über die Befehlszeile](../build/building-on-the-command-line.md) und unter [Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).

## <a name="debugging-your-code"></a>Debuggen von Code

Sie können den Visual Studio-Debugger für Microsoft C++ -Projekte über die Befehlszeile oder innerhalb der IDE verwenden. Kompilieren Sie mit dem Schalter [/Z7,/Zi,/Zi (Debug Information Format)](../build/reference/z7-zi-zi-debug-information-format.md) , um das Durchlaufen von Quellen zu ermöglichen. Weitere Informationen finden Sie unter [Debuggen von nativem Code](/visualstudio/debugger/debugging-native-code) und [Verwenden der Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

Bei Programmen, die mit gcc oder clang kompiliert werden, ruft Visual Studio gdb, lldb oder den von Ihnen angegebenen benutzerdefinierten Debugger auf.

## <a name="visual-studio-project-system"></a>Visual Studio-Projekt System

Das Visual Studio-Projekt System heißt MSBuild. Sie verwendet Projektdateien im XML-Format. C++ Projektdateien haben die Erweiterung ". vcxproj". Eine Anwendung, die aus mehreren Bibliotheken und ausführbaren Dateien besteht, von denen möglicherweise jede mit einem anderen Satz von Compileroptionen oder sogar in einer anderen Sprache erstellt wurde, wird in mehreren Projekten gespeichert, die Teil einer einzigen *Projektmappe* sind. Eine Projektmappe stellt einen abstrakten Container dar, der zur Gruppierung mehrerer Projekte dient. Informationen über Projektmappen werden in einer Projektmappendatei mit der Erweiterung SLN gespeichert. Weitere Informationen finden Sie unter [Projektmappen und Projekte in Visual Studio](/visualstudio/ide/solutions-and-projects-in-visual-studio) und unter [Verwenden der Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md). Wählen Sie im Hauptmenü **Datei** > **neue** > **Projekt** aus, um die verfügbaren Visual Studio-Projektvorlagen anzuzeigen.

Ab Visual Studio 2017 werden die Unterstützung für cmake-Projekte sowie Optionen für die Verwendung des Microsoft C++ -Compilers mit beliebigem Buildsystem oder mit einem losen Ordner von Quelldateien und ohne Projektdateien hinzugefügt. Weitere Informationen finden Sie unter [cmake-Projekte in Visual Studio](../build/cmake-projects-in-visual-studio.md) und [Öffnen von Ordner Projekten in Visual Studio](../build/open-folder-projects-cpp.md).

## <a name="microsoft-specific-modifiers"></a>Microsoft-spezifische Modifizierer

Der Microsoft Visual C++-Compiler implementiert mehrere Erweiterungen der C++-Standardprogrammiersprache, um die Programmierung für Windows-Betriebssysteme zu unterstützen. Diese Erweiterungen werden unter anderem zum Angeben von Speicherklassenattributen, Funktionsaufrufknventionen sowie der Adressierungsart verwendet. Eine vollständige Liste aller unterstützten C++-Erweiterungen finden Sie unter [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).

Sie können alle Microsoft-spezifischen Erweiterungen von C++ deaktivieren, indem Sie die `/Za`-Compileroption verwenden. Diese Option wird für das Schreiben von Code empfohlen, der auf mehreren Plattformen ausgeführt werden soll. Weitere Informationen zur `/Za`-Compileroption finden Sie unter [/Za, /Ze (Disable Language Extensions) (/Za, /Ze (Spracherweiterungen deaktivieren))](../build/reference/za-ze-disable-language-extensions.md). Weitere Informationen zur C++ Compilerkonformität finden Sie unter [Microsoft C++ Language Konformitäts Table](../overview/visual-cpp-language-conformance.md) und [Nonstandard Behavior](../cpp/nonstandard-behavior.md).

## <a name="precompiled-headers"></a>Vorkompilierte Header

Die Microsoft C- und C++-Compiler stellen Optionen für das Vorkompilieren von beliebigem C- oder C++-Code bereit, einschließlich Inlinecode. Mithilfe dieser leistungsstarken Funktion können Sie einen stabilen Codeabschnitt kompilieren, den Code im kompilierten Zustand in einer Datei speichern und bei nachfolgenden Kompilierungen den vorkompilierten Code mit dem noch in Entwicklung befindlichen Code kombinieren. So können nachfolgende Kompilierungen beschleunigt werden, da der bereits stabile Code nicht neu kompiliert werden muss.

Sämtlicher vorkompilierter Code wird standardmäßig in den Dateien *pch.h* und *pch.cpp* (*stdafx.h* und *stdafx.cpp* in Visual Studio 2017 und früher) angegeben. Weitere Informationen zu vorkompilierten Headern finden Sie unter [Erstellen vorkompilierter Headerdateien](../build/creating-precompiled-header-files.md).

## <a name="related-sections"></a>Verwandte Abschnitte

Weitere Informationen finden Sie unter [Ausführen von Linux-Programmen unter Windows](../porting/porting-from-unix-to-win32.md).

## <a name="see-also"></a>Siehe auch

[Projekte und Buildsysteme](../build/projects-and-build-systems-cpp.md)
