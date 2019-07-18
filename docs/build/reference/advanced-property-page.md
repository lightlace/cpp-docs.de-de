---
title: Erweiterte Eigenschaften Seite (Projekt)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCConfiguration.VCToolsVersion
ms.description: Use the Advanced property page in Visual Studio 2019 to set various properties for C++ projects.
ms.openlocfilehash: fae3c76d4a62e3b0409664b3630ad76ab601c52b
ms.sourcegitcommit: 610751254a01cba6ad15fb1e1764ecb2e71f66bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "68315529"
---
# <a name="advanced-property-page"></a>Erweiterte Eigenschaften Seite

Die Eigenschaften Seite erweitert ist in Visual Studio 2019 und höher verfügbar.

::: moniker range="vs-2019"

## <a name="advanced-properties"></a>Erweiterte Eigenschaften

- **Ziel Dateierweiterung**

   Gibt die Dateierweiterung an, die für die Buildausgabe verwendet werden soll. Der Standardwert ist " **. exe** " für Anwendungen, " **. lib** " für statische Bibliotheken und " **. dll** " für DLLs.

- **Bei der Bereinigung zu löschende Erweiterungen**

   Durch die Option **Bereinigen** (Menü **Build**) werden Dateien aus dem Zwischenverzeichnis gelöscht, in dem die Projektkonfiguration erstellt wurde. Dateien mit Erweiterungen, die durch diese Eigenschaft festgelegt werden, werden gelöscht, sobald **Bereinigen** ausgeführt bzw. eine Neuerstellung gestartet wurde. Zusätzlich zu Dateien, die über diese Erweiterungen verfügen und sich im Zwischenverzeichnis befinden, werden vom Buildsystem alle bekannten Ausgaben (einschließlich Zwischenausgaben wie OBJ-Dateien) des Builds unabhängig von ihrem Speicherort gelöscht. Sie können auch Platzhalterzeichen angeben.

   Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>.

- **Buildprotokolldatei**

   Ermöglicht es Ihnen, ein vom Standardspeicherort abweichendes Verzeichnis für die Protokolldatei anzugeben, die bei jedem Erstellen eines Projekts generiert wird. Der Standardspeicherort wird durch die Makros $(IntDir)$(MSBuildProjectName).log angegeben.

   Sie können Projektmakros verwenden, um den Verzeichnispfad zu ändern. Siehe [Allgemeine Makros für Buildbefehle und-Eigenschaften](common-macros-for-build-commands-and-properties.md).

- **Bevorzugte buildtoolarchitektur**

   Gibt an, ob die x86-oder x64-Buildtools verwendet werden.

- **Debugbibliotheken verwenden**

   Gibt an, ob ein Debug-oder Releasebuild erstellt werden soll.

- **Unity-Build (groß) aktivieren**

   Ermöglicht einen Buildprozess, C++ bei dem viele Quelldateien vor der Kompilierung in einer oder mehreren "Unity"-Dateien kombiniert werden, um die Leistung zu verbessern. Nicht im Zusammenhang mit der Unity-Spiel-Engine.

- **Verwendung von MFC**

   Legt fest, ob das MFC-Projekt statisch oder dynamisch mit der MFC-DLL verknüpft wird. Für MFC-fremde Projekte kann **Windows-Standardbibliotheken verwenden** ausgewählt werden, um eine Verknüpfung mit verschiedenen Win32-Bibliotheken herzustellen, die bei Verwendung von MFC einbezogen werden.

   Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>.

- **Zeichensatz**

   Legt fest, ob _UNICODE oder _MBCS verwendet werden soll. Außerdem kann sich diese Option ggf. auf den Linkereinstiegspunkt auswirken.

   Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>.

- **Optimierung des gesamten Programms**

   Legt die Verwendung der [/GL](gl-whole-program-optimization.md)-Compileroption und der [/LTCG](ltcg-link-time-code-generation.md)-Linkeroption fest. Dies ist standardmäßig für die Debugkonfiguration deaktiviert und für die Verkaufskonfiguration aktiviert.

- **MSVC-Toolsetversion**

   Gibt die Vollversion des MSVC-Toolsets an, das zum Erstellen des Projekts verwendet wird. Wenn Sie verschiedene Update-und Vorschau Versionen eines Toolsets installiert haben, können Sie angeben, welches hier verwendet werden soll.

## <a name="ccli-properties"></a>C++/CLI-Eigenschaften

- **Common Language Runtime-Unterstützung**

   Bewirkt, dass die [/clr](clr-common-language-runtime-compilation.md)-Compileroption verwendet wird.

   Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>.

- **.NET Framework-Zielversion**

   Gibt in verwalteten Projekten die Zielversion von .NET-Framework an.

- **Verwalteten inkrementellen Build aktivieren**

   Für verwaltete Projekte aktiviert diese Option die Erkennung von externer Sichtbarkeit, wenn Sie Assemblys generieren. Wenn eine Änderung an einem verwalteten Projekt nicht für andere Projekte sichtbar ist, werden abhängige Projekte nicht neu erstellt. Dies kann Buildzeiten in Projektmappen mit verwalteten Projekten deutlich verbessern.

::: moniker-end
