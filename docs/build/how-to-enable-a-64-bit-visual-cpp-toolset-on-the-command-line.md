---
title: 'Vorgehensweise: Aktivieren Sie eine 64-Bit-Visual C++-Toolsets in der Befehlszeile | Microsoft Docs'
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22290cdf9418299cbba51ab1d893d60cb790e2e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369139"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>Vorgehensweise: Aktivieren Sie eine 64-Bit, X64 gehostet Visual C++-Toolsets in der Befehlszeile

Visual C++ enthält Compiler, Linker und andere Tools, die Sie verwenden können, um plattformspezifischen Versionen der apps zu erstellen, die auf 32-Bit, 64-Bit- oder ARM-basierten Windows-Betriebssystemen ausgeführt werden können. Andere optionale Visual Studio-Arbeitslasten können Sie die C++-Tools verwenden, um andere Zielplattformen wie iOS, Android und Linux. Die Standard-Build-Architektur verwendet 32-Bit, X86 gehostete Tools zum Erstellen von 32-Bit, X86 systemeigene Windows-Code. Allerdings haben Sie wahrscheinlich einen 64-Bit-Computer. Sie können nutzen die Prozessor- und Speicherbereich für 64-Bit-Code verfügbar, mit der 64-Bit, X64 gehostete Toolset beim Erstellen von Code für X86, X64 oder ARM-Prozessoren.

> [!NOTE]
> Informationen über die einzelnen Tools, die in jeder Edition von Visual C++ enthalten sind, finden Sie unter [Visual C++-Tools und Funktionen in Visual Studio-Editionen](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Informationen zur Verwendung von Visual Studio-IDE zum Erstellen von 64-Bit-Anwendungen finden Sie unter [Vorgehensweise: Konfigurieren von Visual C++-Projekte zu Ziel 64-Bit, X64 Plattformen](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

Wenn Sie eine C++-arbeitsauslastung in der Visual Studio-Installer installieren, wird er immer 32-Bit, X86 gehostete, systemeigene und cross Compilertools zur Erstellung von X86- und X64 Code installiert. Wenn Sie die arbeitsauslastung für die universelle Windows-Plattform enthalten, werden auch X86 gehostete Cross-Compiler-Tools zum Erstellen von ARM-Code installiert. Wenn Sie diese arbeitsauslastungen auf einer 64-Bit-X64 installieren Prozessor Außerdem erhalten Sie systemeigene 64-Bit- und cross Compilertools zum Erstellen von X86, x 64 und ARM-code. Die 32-Bit und 64-Bit-Tools generieren einen identischen Code, aber die 64-Bit-Tools unterstützen mehr Speicher für vorkompilierte headersymbole und die Optimierung des gesamten Programms ([/GL](../build/reference/gl-whole-program-optimization.md) und [/LTCG](../build/reference/ltcg-link-time-code-generation.md)) Optionen. Wenn Sie in Arbeitsspeichergrenze ausführen, wenn Sie die 32-Bit-Tools verwenden, versuchen Sie die 64-Bit-Tools.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Verwenden Sie eine 64-Bit-gehosteten Developer-eingabeaufforderungsverknüpfung

Wenn Visual Studio auf einem 64-Bit-Windows-Betriebssystem installiert ist, sind zusätzliche Developer-Eingabeaufforderung Tastenkombinationen für die 64-Bit, X64-gehostete systemeigene und cross-Compiler verfügbar. Zum Zugriff auf diese eingabeaufforderungen unter Windows 10, in der **starten** Menü öffnen Sie den Ordner für Ihre Version von Visual Studio, z. B. **Visual Studio 2017**, und wählen Sie dann eine der X64 native "oder" Cross-Tool Developer-eingabeaufforderungen. Zum Zugriff auf diese eingabeaufforderungen unter Windows 8, in der **starten** -Bildschirm **alle apps**. Unter der Überschrift für die installierte Version von Visual Studio, öffnen Sie die **Visual Studio** Ordner (in früheren Versionen von Visual Studio können sie möglicherweise den Namen **Visual Studio-Tools**). Wählen Sie in früheren Versionen von Windows **starten**, erweitern Sie **Programme**, den Ordner für Ihre Version von **Visual Studio** (und in älteren Versionen von Visual Studio  **Visual Studio-Tools**). Weitere Informationen finden Sie unter [Developer command prompt shortcuts (Tastenkombinationen für die Developer-Eingabeaufforderung)](../build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Verwenden Sie "vcvarsall.bat", um eine gehostete Build 64-Bit-Architektur festzulegen

Alle für das systemeigene und cross Compilertools Projektmappenbuild-Konfigurationen in der Befehlszeile verwendet werden können, indem Sie die vcvarsall.bat ausführen Befehlsdatei. Diese Befehlsdatei konfiguriert den Pfad, und Umgebungsvariablen, die eine bestimmten ermöglichen erstellen Architektur in einer vorhandenen Eingabeaufforderungsfenster. Ausführliche Anweisungen finden Sie unter [Befehlsdateien für Entwickler und Speicherorte](../build/building-on-the-command-line.md#developer-command-files-and-locations).

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Visual C++ für 64-Bit-x64-Ziele](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
