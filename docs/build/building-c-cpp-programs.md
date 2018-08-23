---
title: Erstellen von C/C++-Programmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- vcbuilding
- buildingaprogramVC
dev_langs:
- C++
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fa07308d04d14395b0ca9773e2a0c81ed0c2bc2
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571863"
---
# <a name="building-cc-programs"></a>Erstellen von C/C++-Programmen

Sie können Projekte in Visual C++ entweder in Visual Studio oder der Befehlszeile entwickeln. Visual Studio-IDE verwendet [MSBuild](../build/msbuild-visual-cpp.md) Projekte und Projektmappen zu erstellen. In der Befehlszeile können Sie den C-/C++-Compiler (cl.exe) und den Linker (link.exe) für einfache Projekte nutzen. Um komplexere Projekte in der Befehlszeile zu erstellen, können Sie MSBuild verwenden oder [NMAKE](../build/nmake-reference.md). Eine Übersicht über das Visual Studio zum Erstellen von Projekten und Projektmappen verwenden, finden Sie unter [kompilieren und generieren](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

[Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)  
Erläutert den Einsatz der Visual Studio-IDE für die Entwicklung von C-/C++-Projekten.  
  
[Erstellen von C/C++-Code in der Befehlszeile](../build/building-on-the-command-line.md)  
Erläutert der Einsatz des C-/C++-Befehlszeilecompilers sowie der Buildtools. die in Visual Studio enthalten sind.  
  
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
Beschreibt das Bereitstellungsmodell für Windows Desktop-Anwendungen auf Grundlage der Idee isolierter Anwendungen und paralleler Assemblys.  
  
[Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md)  
Bietet Links zu Referenzartikeln für das Erstellen von Programmen in C++, zu Compiler- und Linkeroptionen und verschiedenen Buildtools.  
  
[Konfigurieren von Visual C++ für 64-Bit-x64-Ziele](../build/configuring-programs-for-64-bit-visual-cpp.md)  
Beschreibt, wie sowohl Visual Studio als auch die Befehlszeile für die Verwendung des 64-Bit-Toolsets und die Ausrichtung auf 64-Bit-Architekturen verwendet wird und erläutert häufige Migrationsprobleme, wenn Code in eine 64-Bit-Architektur bewegt wird.  
  
[Konfigurieren von Visual C++ für ARM-Prozessoren](../build/configuring-programs-for-arm-processors-visual-cpp.md)  
Beschreibt die in ARM-Prozessoren verwendeten Konventionen und erläutert häufige Migrationsprobleme, wenn Code an eine ARM-Architektur verschoben wird.  
  
[Konfigurieren von Programmen für Windows XP](../build/configuring-programs-for-windows-xp.md)  
Beschreibt, wie das Plattformtoolset für die Windows XP-Entwicklung eingerichtet wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Kompilieren und Erstellen](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Beschreibt das Visual Studio-Buildsystem und die entsprechenden Tools.