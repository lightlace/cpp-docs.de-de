---
title: C/C++-Projekte und Buildsysteme in Visual Studio
ms.description: Use Visual Studio to compile and build C++ projects for Windows, ARM or Linux based on any project system.
ms.date: 12/08/2018
f1_keywords:
- vcbuilding
- buildingaprogramVC
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
ms.openlocfilehash: 0c4a74ce69f5c52eb6fc107ea477e5715e86ecd2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825413"
---
# <a name="cc-projects-and-build-systems-in-visual-studio"></a>C/C++-Projekte und Buildsysteme in Visual Studio

Sie können Visual Studio 2017 verwenden, bearbeiten, kompilieren und erstellen C++-Code, der Codebasis mit vollständiger IntelliSense-Unterstützung, ohne diesen Code in eine Visual Studio-Projekt oder die Kompilierung mit dem MSVC-Toolset konvertieren zu müssen. Sie können z. B. ein plattformübergreifenden CMake-Projekts in Visual Studio auf einem Windows-Computer bearbeiten und dann für Linux mit g++ auf einem Linux-Remotecomputer zu kompilieren.

## <a name="c-compilation"></a>C++-Kompilierung

Um *erstellen* ein C++-Programm zum Kompilieren von Quellcode aus einem oder mehreren Dateien, und verknüpfen Sie diese Dateien dann in eine ausführbare Datei (.exe), eine Dynamic-Load-Bibliothek (.dll) oder eine statische Bibliothek (.lib) bedeutet. 

Grundlegende C++-Kompilierung umfasst drei Hauptschritte:

- Der C++-Präprozessor transformiert alle #directives und Makros Definitionen in jeder Quelldatei. Dies erstellt eine *Übersetzungseinheit*.
- Der C++-Compiler kompiliert Jede Übersetzungseinheit in Objektdateien (.obj), Anwenden von die Compileroptionen festgelegt wurden.
- Die *Linker* führt die Objektdateien in einer einzelnen ausführbaren Datei enthält, die Übernahme der Linkeroptionen an, die festgelegt wurden. 

## <a name="the-msvc-toolset"></a>Der MSVC-Toolsets

Microsoft C++-Compiler, Linker, standard-Bibliotheken und zugehörigen Hilfsprogramme umfassen das MSCV-Compilertoolset (auch als eine toolkette oder "build-Tools" bezeichnet). Diese sind in Visual Studio enthalten. Sie können auch herunterladen und verwenden Sie das Toolset als eigenständiges Paket kostenlos von der [Speicherort des Downloads der Build-Tools für Visual Studio 2017](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017).

Sie können einfache Programme erstellen, durch den Aufruf des MSVC-Compilers (cl.exe) direkt über die Befehlszeile. Der folgende Befehl akzeptiert eine einzelne Quellcodedatei, und ruft cl.exe zum Erstellen einer ausführbaren Datei namens *hello.exe*: 

```cmd
cl /EHsc hello.cpp
```
Beachten Sie hier den Compiler (cl.exe) automatisch das C++-Präprozessor "und" Linker ", um die Datei für die endgültige Ausgabe zu erzeugen aufgerufen wird.  Weitere Informationen finden Sie unter [erstellen über die Befehlszeile](building-on-the-command-line.md).

## <a name="build-systems-and-projects"></a>Erstellen von Systemen und Projekte

Die meisten realen-Programme mithilfe bestimmter Art von *Buildsystem* zum Verwalten der Komplexitäten von kompiliert mehrere Quelldateien für Konfigurationen mit mehreren (z. B. debug oder Release), mehrere Plattformen (X86, X64, ARM, und so weiter), benutzerdefinierten Buildprozess Schritte und sogar mehrere ausführbare Dateien, die in einer bestimmten Reihenfolge kompiliert werden muss. Legen Sie Einstellungen in einem Build-Konfiguration-Dateien, und das Buildsystem die Datei als Eingabe akzeptiert, bevor es der Compiler aufgerufen wird. Der Satz von Quellcodedateien und Build-Konfigurationsdateien, die zum Erstellen einer ausführbaren Datei benötigt wird aufgerufen, eine *Projekt*. 

Die folgende Liste enthält verschiedene Optionen für Visual Studio-Projekte – C++:

- Erstellen Sie ein Visual Studio-Projekt mithilfe von Visual Studio-IDE, und konfigurieren Sie sie mithilfe von Eigenschaftenseiten. Visual Studio-Projekte erstellen, Programme, die unter Windows ausgeführt wird. Eine Übersicht finden Sie unter [kompilieren und generieren](/visualstudio/ide/compiling-and-building-in-visual-studio) in Visual Studio-Dokumentation.

- Öffnen Sie einen Ordner, der eine Datei "CMakeLists.txt" enthält. CMake-Unterstützung ist in Visual Studio integriert. Sie können die IDE verwenden, bearbeiten, testen und Debuggen, ohne die CMake-Dateien in irgendeiner Weise ändern. Dadurch können Sie in der gleichen CMake-Projekts als andere arbeiten, die verschiedene Editoren verwenden kann. CMake ist die empfohlene Vorgehensweise für die plattformübergreifende Entwicklung. Weitere Informationen finden Sie unter [CMake-Projekten](cmake-projects-in-visual-studio.md).
 
- Öffnen Sie einen losen Ordner von Quelldateien mit keine Projektdatei an. Visual Studio verwendet Heuristik, um die Dateien zu erstellen. Dies ist eine einfache Möglichkeit zum Kompilieren und Ausführen von kleinen konsolenanwendungen. Weitere Informationen finden Sie unter [Open Folder-Projekte](open-folder-projects-cpp.md).

- Öffnen Sie einen Ordner, der ein Makefile oder einer beliebigen anderen Build Systemkonfigurationsdatei enthält. Sie können Visual Studio, um beliebige Buildaufgabe Befehle aufrufen, indem Sie das Hinzufügen von JSON-Dateien in den Ordner konfigurieren. Weitere Informationen finden Sie unter [Open Folder-Projekte](open-folder-projects-cpp.md).
 
- Öffnen Sie eine Windows-Makefile in Visual Studio. Weitere Informationen finden Sie unter [NMAKE-Referenz](reference/nmake-reference.md).

## <a name="msbuild-from-the-command-line"></a>MSBuild über die Befehlszeile 

Sie können MSBuild über die Befehlszeile aufrufen, durch Übergabe einer .vcxproj-Datei zusammen mit Befehlszeilenoptionen. Dieser Ansatz erfordert gute Kenntnisse von MSBuild, und es wird empfohlen, nur wenn unbedingt erforderlich. Weitere Informationen finden Sie unter [MSBuild](msbuild-visual-cpp.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Visual Studio-Projekte](creating-and-managing-visual-cpp-projects.md) wie erstellen, konfigurieren und Erstellen von C++-Projekte in Visual Studio mit das systemeigene System (MSBuild) erstellen.

[CMake-Projekten](cmake-projects-in-visual-studio.md) wie codieren, erstellen und Bereitstellen von CMake-Projekte in Visual Studio.

[Open Folder-Projekte](open-folder-projects-cpp.md) wie mit Visual Studio code und Bereitstellen von C++-Projekte basierend auf jeder beliebigen Buildsystem oder kein Buildsystem. Überhaupt. 

[Releasebuilds](release-builds.md) erstellen, und beheben die optimierte Version erstellt, für die Bereitstellung für Endbenutzer bereitzustellen.

[Verwenden Sie das MSVC-Toolset, über die Befehlszeile](building-on-the-command-line.md)<br/>
Erläutert, wie die C/C++-Compiler und Buildtools verwenden direkt über die Befehlszeile statt Visual Studio-IDE.

[Erstellen von DLLs in Visual Studio](dlls-in-visual-cpp.md) wie erstellen, Debuggen und Bereitstellen von C/C++-DLLs (freigegebene Bibliotheken) in Visual Studio.

[Erstellen isolierter C/C++-Anwendungen und Side-by-Side Assemblys](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md) beschreibt das Bereitstellungsmodell für Windows Desktop-Anwendungen, basierend auf dem Konzept der isolierten Anwendungen und Side-by-Side Assemblys.

[Konfigurieren von C++-Projekten für 64-Bit-X64 Ziele](configuring-programs-for-64-bit-visual-cpp.md) wie Ziel 64-Bit-X64 Hardware mit dem MSVC-Buildtools.

[Konfigurieren von C++-Projekten für ARM-Prozessoren](configuring-programs-for-arm-processors-visual-cpp.md) wie die MSVC-Buildtools zu verwenden, um die ARM-Hardware ausgerichtet.

[Optimieren Sie Ihren Code](optimizing-your-code.md) wie Sie Ihren Code auf verschiedene Weise einschließlich Profilgesteuerte programmoptimierungen zu optimieren.

[Konfigurieren von Programmen für Windows XP](configuring-programs-for-windows-xp.md) wie Ziel Windows XP mit dem MSVC-Buildtools.

[Referenz zur C/C++-Erstellung](reference/c-cpp-building-reference.md)<br/>
Bietet Links zu Referenzartikeln für das Erstellen von Programmen in C++, zu Compiler- und Linkeroptionen und verschiedenen Buildtools.
