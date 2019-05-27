---
title: 'Vererbung von Eigenschaften in Visual Studio-Projekten: C++'
ms.date: 05/16/2019
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 472700226ffc1f265f6fab84dbd44fca651b3c87
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837403"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Vererbung von Eigenschaften in Visual Studio-Projekten

Das Visual Studio-Projektsystem basiert auf MSBuild. MSBuild definiert die Dateiformate und die Regeln für das Erstellen von Projekten. MSBuild verwaltet einen Großteil der Komplexität für das Erstellen für mehrere Konfigurationen und Plattformen. Sie sollten jedoch die Funktionsweise kennen. Dies ist besonders wichtig, wenn Sie benutzerdefinierte Konfigurationen definieren oder wiederverwendbare Eigenschaften erstellen möchten, die Sie für mehrere Projekte freigeben und in diese importieren können.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>Die VCXPROJ-Datei, PROPS- und TARGETS-Dateien

Projekteigenschaften werden entweder direkt in der Projektdatei (*.vcxproj) oder in weiteren TARGETS- oder PROPS-Dateien gespeichert, die Standardwerte angeben und von der Projektdatei importiert werden. Für Visual Studio 2015 befinden sich diese Dateien unter **\Programme (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Für Visual Studio 2017 oder Visual Studio 2019 befinden sich diese Dateien unter **\\Programme (x86)\\Microsoft Visual Studio\\&lt;2017 oder 2019>\\_Edition_\\Common7\\IDE\\VC\\VCTargets**. Hierbei entspricht _Edition_ der installierten Visual Studio-Edition. Eigenschaften werden ebenfalls in einer PROPS-Datei gespeichert, die Sie zu Ihrem Projekt hinzufügen können. Es wird dringend empfohlen, diese Dateien nicht manuell zu bearbeiten, sondern die Eigenschaftenseiten in der IDE dafür zu verwenden. Dies gilt insbesondere für die Dateien, die in die Vererbung mit einbezogen werden, sofern Sie nicht über gute MSBuild-Kenntnisse verfügen.

Wie zuvor beschrieben kann der gleichen Eigenschaft für die gleiche Konfiguration in verschiedenen Dateien ein anderer Wert zugewiesen werden. Wenn Sie ein Projekt erstellen, wertet die MSBuild-Engine die Projektdatei und alle importierten Dateien in einer klar definierten Reihenfolge (siehe unten) aus. Während die Dateien ausgewertet werden, überschreiben alle Eigenschaftswerte, die in den Dateien definiert sind, die vorhandenen Werte. Alle nicht angegebenen Werte werden von Dateien geerbt, die zuvor ausgewertet wurden. Deshalb ist beim Festlegen einer Eigenschaft mit Eigenschaftenseiten ebenfalls wichtig, darauf zu achten, wo Sie diese festlegen. Wenn Sie eine Eigenschaft in einer PROPS-Datei auf „X“ festlegen, diese aber in der Projektdatei auf „Y“ festgelegt ist, wird das Projekt mit der auf „Y“ festgelegten Eigenschaft erstellt. Wenn die gleiche Eigenschaft in einem Projektelement (z.B. in einer CPP-Datei) auf „Z“ festgelegt ist, verwendet die MSBuild-Engine den Wert „Z“. 

So sieht die grundlegende Vererbungsstruktur aus:

1. Standardeinstellungen von MSBuild CPP Toolset („..\Programme\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props“, die durch die VCXPROJ-Datei importiert wird)

2. Eigenschaftenblätter

3. VCXPROJ-Datei (Kann Standard- und die Eigenschaftenblatteinstellungen überschreiben.)

4. Elementmetadaten

> [!TIP]
> Auf einer Eigenschaftenseite wird eine Eigenschaft in `bold` im aktuellen Kontext definiert. Eine Eigenschaft in normaler Schriftart ist geerbt.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>Anzeigen einer erweiterten Projektdatei mit allen importierten Werten

Manchmal ist es hilfreich, die erweiterte Datei anzuzeigen, um zu bestimmen, wie ein bestimmter Eigenschaftswert vererbt wird. Um die erweiterte Version anzuzeigen, geben Sie folgenden Befehl an einer Visual Studio-Eingabeaufforderung ein. (Ändern Sie die Platzhalterdateinamen in die Namen der Dateien, die Sie verwenden möchten.)

**msbuild /pp:** *temp* **.txt** *myapp* **.vcxproj**

Erweiterte Projektdateien können sehr groß und schwierig zu verstehen sein, wenn Sie nicht mit MSBuild vertraut sind. So sieht die grundlegende Struktur einer Projektdatei aus:

1. Grundlegende Projekteigenschaften, die in der IDE nicht verfügbar gemacht werden.

2. Import von Microsoft.cpp.default.props, die einige einfache, Toolset-unabhängige Eigenschaften definiert.

3. Globale Konfigurationseigenschaften (verfügbar als Standardeigenschaften **PlatformToolset** und **Project** auf der Seite **Konfiguration > Allgemein**). Diese Eigenschaften bestimmen, welche Toolset- und systeminternen Eigenschaftenblätter im nächsten Schritt in Microsoft.cpp.props importiert werden.

4. Import von Microsoft.cpp.props, die die meisten Projektstandardwerte festlegt.

5. Import aller Eigenschaftenblätter, einschließlich USER-Dateien. Diese Eigenschaftenblätter können alle Eigenschaften außer die Standardeigenschaften **PlatformToolset** und **Project** überschreiben.

6. Die restlichen Eigenschaften der Projektkonfiguration. Diese Werte können das überschreiben, was in den Eigenschaftenblättern festgelegt wurde.

7. Elemente (Dateien) zusammen mit ihren Metadaten. Diese stellen immer das letzte Wort in den MSBuild-Auswertungsregeln dar, selbst wenn sie vor anderen Eigenschaften und Importen auftreten.

Weitere Informationen finden Sie unter [MSBuild Properties](/visualstudio/msbuild/msbuild-properties) (MSBuild-Eigenschaften).

## <a name="build-configurations"></a>Buildkonfigurationen

Eine Konfiguration ist nur eine beliebige Gruppe von Eigenschaften, denen ein Name zugewiesen wird. Visual Studio stellt Debug- und Releasekonfigurationen bereit und legt jeweils verschiedene Eigenschaften fest, die einem Debugbuild oder einem Releasebuild entsprechen. Sie können den **Konfigurations-Manager** verwenden, um benutzerdefinierte Konfigurationen zu definieren und somit Eigenschaften einfach für einen bestimmten Build gruppieren. 

Um eine bessere Vorstellung von Buildkonfigurationen zu bekommen, öffnen Sie den **Eigenschaften-Manager**, indem Sie **Ansicht &#124; Eigenschaften-Manager** oder **Ansicht &#124; Weitere Fenster &#124; Eigenschaften-Manager** auswählen, je nach Ihren Einstellungen. Der **Eigenschaften-Manager** weist Knoten für jede Konfiguration/jedes Plattform-Paar im Projekt auf. Unter jedem dieser Knoten sind Knoten für Eigenschaftenblätter (PROPS-Dateien), die für diese Konfiguration spezifische Eigenschaften festlegen.

![Eigenschaften-Manager](media/property-manager.png "Property Manager")

Wenn Sie auf den Eigenschaftenseiten zum Bereich „Allgemein“ wechseln und die Eigenschaft „Zeichensatz“ auf „Nicht festgelegt“ statt auf „Unicode-Zeichensatz verwenden“ festlegen und auf **OK** klicken, zeigt der Eigenschaften-Manager das Eigenschaftenblatt **Unicode-Unterstützung** für die aktuelle Konfiguration nicht an. Für andere Konfigurationen ist es jedoch vorhanden.

Weitere Informationen zum Eigenschaften-Manager und zu Eigenschaftenblättern finden Sie unter [Teilen oder Wiederverwenden von Visual Studio C++-Projekteinstellungen](create-reusable-property-configurations.md).

> [!TIP]
> Bei der USER-Datei handelt es sich um ein veraltetes Feature. Es wird empfohlen, diese zu löschen, damit die Eigenschaften entsprechend der Konfiguration und Plattform richtig gruppiert werden.



