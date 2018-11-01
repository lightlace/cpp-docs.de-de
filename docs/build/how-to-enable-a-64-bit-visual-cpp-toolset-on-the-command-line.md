---
title: 'Gewusst wie: Aktivieren eines 64-Bit-Visual C++-Toolsets auf der Befehlszeile'
ms.date: 03/29/2018
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
ms.openlocfilehash: 5c5fe144fe81fcc0fb1194c57dec7fa7556101f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572366"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>Gewusst wie: Aktivieren Sie eine 64-Bit, X64 gehostet, Visual C++-Toolsets in der Befehlszeile

Visual C++ enthält Compiler, Linker und anderen Tools, die Sie verwenden können, um plattformspezifischen Versionen Ihrer apps zu erstellen, die auf 32-Bit, 64-Bit- oder ARM-basierten Windows-Betriebssystemen ausgeführt werden können. Andere optionale Visual Studio-Workloads können Sie die C++-Tools verwenden, um andere Plattformen wie iOS, Android und Linux. Die Standard-Build-Architektur verwendet 32-Bit, X86-gehosteten Tools, um die 32-Bit, X86 Native Windows-Code zu erstellen. Allerdings müssen Sie wahrscheinlich einen 64-Bit-Computer. Profitieren Sie von den Prozessor und Speicherplatz für 64-Bit-Code verfügbar, mit der 64-Bit, X64 gehostete-Toolset, bei der Erstellung von Code für X86, X64 oder ARM-Prozessoren.

> [!NOTE]
> Informationen zu den spezifischen Tools, die in jeder Edition von Visual C++ enthalten sind, finden Sie unter [Visual C++-Tools und Features in Visual Studio-Editionen](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Weitere Informationen zur Verwendung von Visual Studio-IDE zum Erstellen von 64-Bit-Anwendungen finden Sie unter [Vorgehensweise: Konfigurieren von Visual C++ Projekten für Ziel-64-Bit X64 Plattformen](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

Wenn Sie eine C++-arbeitsauslastung in Visual Studio-Installer installieren, wird es 32-Bit, X86 gehostete, systemeigene und cross Compilertools zum Erstellen von X86- und X64 Code immer installiert. Wenn Sie die arbeitsauslastung der universellen Windows-Plattform einschließen, wird auch X86 gehostete Cross-Compiler-Tools zum Erstellen von ARM-Code installiert. Bei der Installation von dieser Workloads auf einem 64-Bit-X64-Prozessor, außerdem erhalten Sie die 64-Bit systemeignen und cross Compilertools zum Erstellen von X86, x 64- und ARM code. Die 32-Bit- und 64-Bit-Tools generieren identischen Code, aber die 64-Bit-Tools unterstützen mehr Speicher für vorkompilierte headersymbole und die komplette Programmoptimierung (["/ GL"](../build/reference/gl-whole-program-optimization.md) und ["/ LTCG"](../build/reference/ltcg-link-time-code-generation.md)) Optionen. Wenn Sie Arbeitsspeicherlimits auftreten, wenn Sie die 32-Bit-Tools verwenden, versuchen Sie die 64-Bit-Tools.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Verwenden Sie eine 64-Bit-gehosteten Developer-eingabeaufforderungsverknüpfung

Wenn Visual Studio auf einem 64-Bit-Windows-Betriebssystem installiert ist, sind weitere Verknüpfungen der Eingabeaufforderung für die 64-Bit, X64-gehostete systemeigene und cross-Compiler verfügbar. Zum Zugriff auf diese eingabeaufforderungen unter Windows 10, in der **starten** Menü öffnen Sie den Ordner für Ihre Version von Visual Studio, z. B. **Visual Studio 2017**, und wählen Sie dann eines der X64 native oder Cross-Tool Entwickler-eingabeaufforderungen. Um diese eingabeaufforderungen unter Windows 8 auf den **starten** öffnen **alle apps**. Unter der Überschrift für die installierte Version von Visual Studio, öffnen Sie die **Visual Studio** Ordner (in früheren Versionen von Visual Studio können sie möglicherweise den Namen **Visual Studio-Tools**). Wählen Sie in früheren Versionen von Windows wird **starten**, erweitern Sie **Programme**, den Ordner für Ihre Version von **Visual Studio** (und in älteren Versionen von Visual Studio  **Visual Studio-Tools**). Weitere Informationen finden Sie unter [Developer command prompt shortcuts (Tastenkombinationen für die Developer-Eingabeaufforderung)](../build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Verwenden Sie "vcvarsall.bat" zum Festlegen einer 64-Bit-gehostete Build-Architektur

Eine der systemeigenen oder cross Compilertools Projektmappenbuild-Konfigurationen in der Befehlszeile verwendet werden können, indem Sie die vcvarsall.bat ausführen Befehlsdatei. Diese Befehlsdatei konfiguriert den Pfad ein, und Umgebungsvariablen, die einen bestimmten ermöglichen erstellen Architektur in ein vorhandenes Fenster der Eingabeaufforderung. Ausführliche Anweisungen finden Sie unter [Developer-Befehlsdateien und Speicherorte](../build/building-on-the-command-line.md#developer-command-files-and-locations).

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Visual C++ für 64-Bit-x64-Ziele](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
