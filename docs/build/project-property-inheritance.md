---
title: Vererbung von Eigenschaften in Visual Studio-Projekte – C++
ms.date: 12/10/2018
helpviewer_keywords:
- Visual C++ projects, property inheritance
ms.openlocfilehash: edd6d3bf82f7a13cf6687abeba3758dcceca5e84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295440"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Vererbung von Eigenschaften in Visual Studio-Projekten

Die Visual Studio-Projektsystem beruht auf MSBuild, die Dateiformate und die Regeln für das Erstellen von Projekte eines beliebigen Typs definiert. MSBuild verwaltet einen Großteil der Komplexität für das Erstellen für mehrere Konfigurationen und Plattformen. Sie sollten jedoch die Funktionsweise kennen. Dies ist besonders wichtig, wenn Sie benutzerdefinierte Konfigurationen definieren oder wiederverwendbare Eigenschaften erstellen möchten, die Sie für mehrere Projekte freigeben und in diese importieren können.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>Die VCXPROJ-Datei, props- und TARGETS-Dateien

Projekteigenschaften werden gespeichert, entweder direkt in der Projektdatei (*.vcxproj) oder in anderen targets oder PROPS-Dateien, die die Importe von Projekt und die Standardwerte angeben. Für Visual Studio 2015 befinden sich diese Dateien unter **\Programme (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Für Visual Studio 2017 befinden sich diese Dateien unter **\\Programme (x86)\\Microsoft Visual Studio\\2017\\_Edition_\\Common7\\IDE\\VC\\VCTargets**. Hierbei entspricht _Edition_ der installierten Visual Studio-Edition. Eigenschaften werden ebenfalls in einer PROPS-Datei gespeichert, die Sie zu Ihrem Projekt hinzufügen können. Es wird dringend empfohlen, diese Dateien nicht manuell zu bearbeiten, sondern die Eigenschaftenseiten in der IDE dafür zu verwenden. Dies gilt insbesondere für die Dateien, die in die Vererbung mit einbezogen werden, sofern Sie nicht über gute MSBuild-Kenntnisse verfügen.

Wie bereits erwähnt, kann die gleiche Eigenschaft für die gleiche Konfiguration einen anderen Wert in diesen verschiedenen Dateien zugewiesen werden. Wenn Sie ein Projekt erstellen, wertet die MSBuild-Engine die Projektdatei und alle importierten Dateien in einer klar definierten Reihenfolge (siehe unten) aus. Während die Dateien ausgewertet werden, überschreiben alle Eigenschaftswerte, die in den Dateien definiert sind, die vorhandenen Werte. Alle nicht angegebenen Werte werden von Dateien geerbt, die zuvor ausgewertet wurden. Deshalb ist beim Festlegen einer Eigenschaft mit Eigenschaftenseiten ebenfalls wichtig, darauf zu achten, wo Sie diese festlegen. Wenn Sie eine Eigenschaft in einer PROPS-Datei auf „X“ festlegen, diese aber in der Projektdatei auf „Y“ festgelegt ist, wird das Projekt mit der auf „Y“ festgelegten Eigenschaft erstellt. Wenn die gleiche Eigenschaft in einem Projektelement (z.B. in einer CPP-Datei) auf „Z“ festgelegt ist, verwendet die MSBuild-Engine den Wert „Z“. 

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

Um einen besseren Überblick über die Konfigurationen zu erhalten, öffnen Sie **Eigenschaften-Manager** dazu **Ansicht &#124; Eigenschaften-Manager** oder **Ansicht &#124; andere Windows &#124; Eigenschaften-Manager**  abhängig von Ihren Einstellungen. **Eigenschaften-Manager** hat der Knoten für jedes Paar der Konfiguration/Plattform im Projekt. Unter jedem dieser Knoten sind Knoten für Eigenschaftenblätter (PROPS-Dateien), die für diese Konfiguration spezifische Eigenschaften festlegen.

![Eigenschaften-Manager](media/property-manager.png "Property Manager")

Wenn Sie wechseln Sie zum Bereich "Allgemein" auf den Eigenschaftenseiten, und legen Sie die Eigenschaft Zeichensatz auf "Nicht festgelegt" anstelle von "Verwenden von Unicode", und klicken Sie auf **OK**, Eigenschaften-Manager zeigt keine **Unicode-Unterstützung** Eigenschaftenblatt für die aktuelle Konfiguration, aber es wird weiterhin für andere Konfigurationen bestehen.

Weitere Informationen zu Eigenschaften-Manager und Eigenschaftenseiten finden Sie unter [Freigabe oder beabsichtigen Visual Studio C++-projekteinstellungen](create-reusable-property-configurations.md).

> [!TIP]
> Bei der USER-Datei handelt es sich um ein veraltetes Feature. Es wird empfohlen, diese zu löschen, damit die Eigenschaften entsprechend der Konfiguration und Plattform richtig gruppiert werden.



