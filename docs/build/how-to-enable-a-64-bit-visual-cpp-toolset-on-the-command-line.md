---
title: 'Vorgehensweise: Aktivieren eines 64-Bit-MSVC-Toolsets in der Befehlszeile'
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
ms.openlocfilehash: b30b831522016ce61f138f7e0521c42ff44e04d9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809768"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-msvc-toolset-on-the-command-line"></a>Vorgehensweise: Aktivieren eine 64-Bit, X64 gehosteten MSVC-Toolsets auf der Befehlszeile

Visual Studio enthält C++-Compiler, Linker und anderen Tools, die Sie verwenden können, um plattformspezifischen Versionen Ihrer apps zu erstellen, die auf 32-Bit, 64-Bit- oder ARM-basierten Windows-Betriebssystemen ausgeführt werden können. Andere optionale Visual Studio-Workloads können Sie die C++-Tools verwenden, um andere Plattformen wie iOS, Android und Linux. Die Standard-Build-Architektur verwendet 32-Bit, X86-gehosteten Tools, um die 32-Bit, X86 Native Windows-Code zu erstellen. Allerdings müssen Sie wahrscheinlich einen 64-Bit-Computer. Profitieren Sie von den Prozessor und Speicherplatz für 64-Bit-Code verfügbar, mit der 64-Bit, X64 gehostete-Toolset, bei der Erstellung von Code für X86, X64 oder ARM-Prozessoren.

> [!NOTE]
> Informationen zu den spezifischen Tools, die in jeder Edition von Visual Studio enthalten sind, finden Sie unter [Visual C++-Tools und Features in Visual Studio-Editionen](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Weitere Informationen zur Verwendung von Visual Studio-IDE zum Erstellen von 64-Bit-Anwendungen finden Sie unter [Vorgehensweise: Configure Visual C++ Projects to Target 64-Bit, x64 Platforms (Vorgehensweise: Konfigurieren von Visual C++-Projekten für 64-Bit-Zielplattformen (x64))](how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

Wenn Sie eine C++-arbeitsauslastung in Visual Studio-Installer installieren, wird es 32-Bit, X86 gehostete, systemeigene und cross Compilertools zum Erstellen von X86- und X64 Code immer installiert. Wenn Sie die arbeitsauslastung der universellen Windows-Plattform einschließen, wird auch X86 gehostete Cross-Compiler-Tools zum Erstellen von ARM-Code installiert. Bei der Installation von dieser Workloads auf einem 64-Bit-X64-Prozessor, außerdem erhalten Sie die 64-Bit systemeignen und cross Compilertools zum Erstellen von X86, x 64- und ARM code. Die 32-Bit- und 64-Bit-Tools generieren identischen Code, aber die 64-Bit-Tools unterstützen mehr Speicher für vorkompilierte headersymbole und die komplette Programmoptimierung (["/ GL"](reference/gl-whole-program-optimization.md) und ["/ LTCG"](reference/ltcg-link-time-code-generation.md)) Optionen. Wenn Sie Arbeitsspeicherlimits auftreten, wenn Sie die 32-Bit-Tools verwenden, versuchen Sie die 64-Bit-Tools.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Verwenden Sie eine 64-Bit-gehosteten Developer-eingabeaufforderungsverknüpfung

Wenn Visual Studio auf einem 64-Bit-Windows-Betriebssystem installiert ist, sind weitere Verknüpfungen der Eingabeaufforderung für die 64-Bit, X64-gehostete systemeigene und cross-Compiler verfügbar. Zum Zugriff auf diese eingabeaufforderungen unter Windows 10, in der **starten** Menü öffnen Sie den Ordner für Ihre Version von Visual Studio, z. B. **Visual Studio 2017**, und wählen Sie dann eines der X64 native oder Cross-Tool Entwickler-eingabeaufforderungen. Um diese eingabeaufforderungen unter Windows 8 auf den **starten** öffnen **alle apps**. Unter der Überschrift für die installierte Version von Visual Studio, öffnen Sie die **Visual Studio** Ordner (in früheren Versionen von Visual Studio können sie möglicherweise den Namen **Visual Studio-Tools**). Wählen Sie in früheren Versionen von Windows wird **starten**, erweitern Sie **Programme**, den Ordner für Ihre Version von **Visual Studio** (und in älteren Versionen von Visual Studio  **Visual Studio-Tools**). Weitere Informationen finden Sie unter [Developer command prompt shortcuts (Tastenkombinationen für die Developer-Eingabeaufforderung)](building-on-the-command-line.md#developer_command_prompt_shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Verwenden Sie "vcvarsall.bat" zum Festlegen einer 64-Bit-gehostete Build-Architektur

Eine der systemeigenen oder cross Compilertools Projektmappenbuild-Konfigurationen in der Befehlszeile verwendet werden können, indem Sie die vcvarsall.bat ausführen Befehlsdatei. Diese Befehlsdatei konfiguriert den Pfad ein, und Umgebungsvariablen, die einen bestimmten ermöglichen erstellen Architektur in ein vorhandenes Fenster der Eingabeaufforderung. Ausführliche Anweisungen finden Sie unter [Developer-Befehl Dateispeicherorte](building-on-the-command-line.md#developer_command_file_locations).

## <a name="see-also"></a>Siehe auch

[Konfigurieren von C++-Projekten für 64-Bit-X64 Ziele](configuring-programs-for-64-bit-visual-cpp.md)<br/>
