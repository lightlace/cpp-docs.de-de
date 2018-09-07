---
title: Visual C++-Tools und -Features in Visual Studio-Editionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- versions [C++]
- Visual C++, versions
- editions [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79814d96bac185e73cc1c42a98be6d7b35e9a75d
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42578146"
---
# <a name="visual-c-tools-and-features-in-visual-studio-editions"></a>Visual C++-Tools und -Features in Visual Studio-Editionen

Die folgenden Tabellen zeigen die Visual C++-Funktionen, die in Visual Studio verfügbar sind. Ein „X“ in einer Zelle gibt an, dass die Funktion verfügbar ist. Eine leere Zelle gibt an, dass die Funktion nicht verfügbar ist. Hinweise in Klammern geben an, dass eine Funktion eingeschränkt verfügbar ist.

## <a name="platforms"></a>Plattformen

||||||
|-|-|-|-|-|
|Plattform|Visual Studio Express für Windows 10|Visual Studio Express für Windows Desktop|Visual Studio-Community/Professional|Visual Studio Enterprise|
|Windows-Desktop||X|X|X|
|Universelle Windows-Plattform ((Telefon, Tablet, PC, Xbox, IoT und HoloLens)) |X||X|X|
|Microsoft Store 8.1|||X|X|
|Windows Phone 8.0|||X|X|
|Android|||X|X|
|iOS|||X|X|

## <a name="compilers"></a>Compiler

|Compiler|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|32-Bit-X86-Compiler|X|X|X|X|
|X86_arm-Cross-Compiler|X||X|X|
|64-Bit x64-Compiler|||X|X|
|x86_x64-Cross-Compiler|X|X|X|X|

## <a name="libraries-and-headers"></a>Bibliotheken und Header

|Bibliothek oder Header|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Windows-Header und Bibliotheken und CRT-Bibliothek|(X)|X|X|X|
|C++-Standardbibliothek|X|X|X|X|
|ATL|||X|X|
|MFC|||X|X|
|.NET Framework-Klassenbibliothek||X|X|X|
|C++-Unterstützungsbibliothek für .NET||X|X|X|
|OpenMP|X|X|X|X|

## <a name="project-templates"></a>Projektvorlagen

|Vorlage|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML-Vorlagen für UWP, Windows 8.1, Windows Phone 8.0|X||X|X|
|Direct3D-App|X||X|X|
|DLL (Universelles Windows)|X||X|X|
|Statische Bibliothek (Universelles Windows)|X||X|X|
|Komponente für Windows-Runtime|X||X|X|
|Komponententest-App (Universelles Windows)|X||X|X|
|ATL-Projekt|||X|X|
|Klassenbibliothek (CLR)||X|X|X|
|CLR-Konsolenanwendung||X|X|X|
|Leeres CLR-Projekt||X|X|X|
|Benutzerdefinierter Assistent|||X|X|
|Leeres Projekt||X|X|X|
|Makefile-Projekt||X|X|X|
|MFC-ActiveX-Steuerelement|||X|X|
|MFC-Anwendung|||X|X|
|MFC-DLL|||X|X|
|Testprojekt|X|X|X|X|
|Win32-Konsolenanwendung||X|X|X|
|Win32-Projekt||X|X|X|

## <a name="tools"></a>Tools

|Tool|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Incremental Linker (Link.exe)|X|X|X|X|
|Program Maintenance Utility (Nmake.exe)||X|X|X|
|Lib-Generator (Lib.exe)|X|X|X|X|
|Windows-Ressourcencompiler (Rc.exe)|X|X|X|X|
|Windows Resource to Object Converter (CvtRes.exe)||X|X|X|
|Browse Information Maintenance-Programm (BscMake.exe)|X|X|X|X|
|C++ Name Undecorator (Undname.exe)|X|X|X|X|
|COFF/PE-Dumper (Dumpbin.exe)|X|X|X|X|
|COFF/PE-Editor (Editbin.exe)|X|X|X|X|
|MASM (Ml.exe)|||X|X|
|Spy++|||X|X|
|ErrLook|||X|X|
|AtlTrace|||X|X|
|Devenv.com|||X|X|
|Rückschlussregeln|||X|X|
|Aktualisieren von VCBuild-VCPROJ-Projekten auf MSBuild (VCUpgrade.exe)|X|X|X|X|
|Profilgesteuerte Optimierungen (PGO)|||X|X|

## <a name="debugging-features"></a>Debugfeatures

|Debugfunktion|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Systemeigenes Debuggen|X|X|X|X|
|Natvis (Visualisierung des systemeigenen Typs)|X|X|X|X|
|Grafikdebugging|X||X|X|
|Verwaltetes Debuggen||X|X|X|
|GPU-Nutzung|X||X|X|
|Speicherauslastung|X||X|X|
|Remotedebugging|X|X|X|X|
|SQL-Debugging|||X|X|
|Statische Codeanalyse|Eingeschränkt|Eingeschränkt|X|X|

## <a name="designers-and-editors"></a>Designer und Editoren

|Designer oder Editor|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML-Designer|X||X|X|
|CSS-Format-Designer/Editor|X|X|X|X|
|HTML-Designer/Editor|X|X|X|X|
|XML-Editor|X|X|X|X|
|Quellcode-Editor|X|X|X|X|
|Produktivitätsfeatures: Umgestaltung, IntelliSense, C++-Codeformatierung|X|X|X|X|
|Windows Forms-Designer||X|X|X|
|Daten-Designer|||X|X|
|Systemeigener Ressourcen-Editor (RC-Dateien)|||X|X|
|Ressourcen-Editor|X|X|X|X|
|Modell-Editor|X||X|X|
|Shader-Designer|X||X|X|

## <a name="data-features"></a>Datenfeatures

|Datenfunktion|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Daten-Designer|||X|X|
|Datenobjekte|||X|X|
|Webdienste|||X|X|
|Server-Explorer|||X|X|

## <a name="build-and-project-systems"></a>Build- und Projektsysteme

|Build- oder Projektfunktion|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Befehlszeilenbuilds (msbuild.exe)|X|X|X|X|
|Systemeigene Festlegung von Zielversionen||X|X|X|
|Verwaltete Festlegung von Zielversionen||X|X|X|
|Parallele Builds|X|X|X|X|
|Buildanpassungen|X|X|X|X|
|Erweiterbarkeit der Eigenschaftenseiten|X|X|X|X|

## <a name="automation-and-extensibility"></a>Automatisierung und Erweiterbarkeit

|Automatisierung und Erweiterbarkeit|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Erweiterbarkeitsobjektmodelle|||X|X|
|Codemodell|||X|X|
|Projektmodell|||X|X|
|Modell für den Ressourcen-Editor|||X|X|
|Assistentenmodell|||X|X|
|Debuggerobjektmodell|||X|X|

## <a name="application-lifecycle-management-tools"></a>Anwendungslebenszyklus-Verwaltungstools

||||||
|-|-|-|-|-|
|Tool|Visual Studio Express für Windows|Visual Studio Express für Windows Desktop|Visual Studio Professional / Community|Visual Studio Enterprise|
|Komponententests (systemeigenes Framework)|X|X|X|X|
|Komponententests (verwaltetes Framework)||X|X|X|
|Codeabdeckung||||X|
|Manuelle Tests||||X|
|Explorative Tests||||X|
|Testfallverwaltung||||X|
|Codezuordnung und Abhängigkeitsdiagramme|||Schreibgeschützt|X|
|Code Map-Debugging||||X|

## <a name="see-also"></a>Siehe auch

[Installieren von Visual Studio](/visualstudio/install/install-visual-studio)<br/>
[Neues in Visual Studio](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual C++-Projekttypen](../ide/visual-cpp-project-types.md)<br/>
[SQL Server-Datentools](https://msdn.microsoft.com/library/hh272686)<br/>
