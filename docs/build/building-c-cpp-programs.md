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
ms.openlocfilehash: 2792b49d7d3d3f107e39931ff62e6c4137c9c5ca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723267"
---
# <a name="building-cc-programs"></a>Erstellen von C/C++-Programmen

Sie können Projekte in Visual C++ entweder in Visual Studio oder der Befehlszeile entwickeln. Visual Studio-IDE verwendet [MSBuild](../build/msbuild-visual-cpp.md) Projekte und Projektmappen zu erstellen. In der Befehlszeile können Sie den C-/C++-Compiler (cl.exe) und den Linker (link.exe) für einfache Projekte nutzen. Um komplexere Projekte in der Befehlszeile zu erstellen, können Sie MSBuild verwenden oder [NMAKE](../build/nmake-reference.md). Eine Übersicht über das Visual Studio zum Erstellen von Projekten und Projektmappen verwenden, finden Sie unter [kompilieren und generieren](/visualstudio/ide/compiling-and-building-in-visual-studio).

## <a name="in-this-section"></a>In diesem Abschnitt

[Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md) wird erläutert, wie Visual Studio-IDE zu verwenden, um das C/C++-Projekt zu erstellen.

[Erstellen von C/C++-Code in der Befehlszeile](../build/building-on-the-command-line.md) wird erläutert, wie der C/C++-Befehlszeilen-Compiler und Buildtools verwenden, die in Visual Studio enthalten sind.

[Erstellen isolierter C/C++-Anwendungen und Side-by-Side Assemblys](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md) beschreibt das Bereitstellungsmodell für Windows Desktop-Anwendungen, basierend auf dem Konzept der isolierten Anwendungen und Side-by-Side Assemblys.

[Referenz zur C/C++-erstellen](../build/reference/c-cpp-building-reference.md) bietet links zu Referenzartikeln über das Programm erstellen, die in C++, Compiler- und Linkeroptionen und verschiedenen Buildtools.

[Konfigurieren von Visual C++ für 64-Bit-X64 Ziele](../build/configuring-programs-for-64-bit-visual-cpp.md) beschreibt, wie sowohl Visual Studio als auch die Befehlszeile aus, um die 64-Bit-Toolsets zu verwenden, konfigurieren und wie Sie die 64-Bit-Architekturen abzielen, und erläutert häufige Migrationsprobleme, wenn Code auf 64-Bit-bewegt wird Architekturen.

[Konfigurieren von Visual C++ für ARM-Prozessoren](../build/configuring-programs-for-arm-processors-visual-cpp.md) beschreibt die ARM-Prozessoren verwendeten Konventionen und erläutert häufige Migrationsprobleme, wenn Code auf ARM-Architekturen verschoben wird.

[Konfigurieren von Programmen für Windows XP](../build/configuring-programs-for-windows-xp.md) wird beschrieben, wie das Plattformtoolset auf Ziel Windows XP-Entwicklung festgelegt.

## <a name="related-sections"></a>Verwandte Abschnitte

[Kompilieren und generieren](/visualstudio/ide/compiling-and-building-in-visual-studio) beschreibt die Visual Studio erstellen, System- und Tools.