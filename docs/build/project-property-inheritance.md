---
title: 'Vererbung von Eigenschaften in Visual Studio-Projekten: C++'
description: Funktionsweise der Eigenschafts Vererbung in systemeigenen (MSBuild) Visual Studio C++ -Projekten.
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 2032ab63c7d278a080742dba8d8d0c6c3ed7a094
ms.sourcegitcommit: 9a63e9b36d5e7fb13eab15c2c35bedad4fb03ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "77600022"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Vererbung von Eigenschaften in Visual Studio-Projekten

Das Native Visual Studio-Projekt System basiert auf MSBuild. MSBuild definiert Dateiformate und Regeln zum Erstellen von Projekten beliebiger Art. Es verwaltet den größten Teil der Komplexität beim Aufbau mehrerer Konfigurationen und Plattformen. Es ist hilfreich, die Funktionsweise zu verstehen. Dies ist besonders wichtig, wenn Sie benutzerdefinierte Konfigurationen definieren möchten. Oder, um wiederverwendbare Sätze von Eigenschaften zu erstellen, die Sie freigeben und in mehrere Projekte importieren können.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>Die VCXPROJ-Datei, PROPS- und TARGETS-Dateien

Projekteigenschaften werden entweder direkt in der Projektdatei ( *`.vcxproj`* ) oder in anderen *`.targets`* -oder *`.props`* Dateien gespeichert, die von der Projektdatei importiert werden und die Standardwerte bereitstellen. Für Visual Studio 2015 befinden sich diese Dateien in *`\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140`* . Für Visual Studio 2017 befinden sich diese Dateien in *`\Program Files (x86)\Microsoft Visual Studio\2017\<edition>\Common7\IDE\VC\VCTargets`* , in dem *`<edition>`* die installierte Version von Visual Studio ist. In Visual Studio 2019 befinden sich diese Dateien in *`\Program Files (x86)\Microsoft Visual Studio\2019\<edition>\MSBuild\Microsoft\VC\v160`* . Eigenschaften werden auch in allen benutzerdefinierten *`.props`* Dateien gespeichert, die Sie Ihrem eigenen Projekt hinzufügen können. Es wird dringend empfohlen, diese Dateien nicht manuell zu bearbeiten. Verwenden Sie stattdessen die Eigenschaften Seiten in der IDE, um alle Eigenschaften zu ändern, insbesondere diejenigen, die an der Vererbung beteiligt sind, es sei denn, Sie haben ein tiefgreifendes Verständnis von MSBuild.

Wie zuvor beschrieben kann der gleichen Eigenschaft für die gleiche Konfiguration in verschiedenen Dateien ein anderer Wert zugewiesen werden. Wenn Sie ein Projekt erstellen, wertet die MSBuild-Engine die Projektdatei und alle importierten Dateien in einer klar definierten Reihenfolge (siehe unten) aus. Während die Dateien ausgewertet werden, überschreiben alle Eigenschaftswerte, die in den Dateien definiert sind, die vorhandenen Werte. Alle Werte, die nicht angegeben werden, werden von Dateien geerbt, die zuvor ausgewertet wurden. Wenn Sie eine Eigenschaft mit Eigenschaften Seiten festlegen, ist es auch wichtig, darauf zu achten, wo Sie Sie festlegen. Wenn Sie eine Eigenschaft in einer *`.props`* Datei auf "X" festlegen, aber die-Eigenschaft in der Projektdatei auf "y" festgelegt ist, wird das Projekt erstellt, wobei die-Eigenschaft auf "y" festgelegt ist. Wenn die gleiche Eigenschaft für ein Projekt Element auf "z" festgelegt ist (z. b. eine *`.cpp`* Datei), verwendet die MSBuild-Engine den Wert "z".

So sieht die grundlegende Vererbungsstruktur aus:

1. Standardeinstellungen aus dem MSBuild-Toolset für cpp (.. \Program ..\programme\msbuild\microsoft.cpp\v4.0\Microsoft.cpp.default.Props ", das von der *`.vcxproj`* Datei importiert wird.)

1. Eigenschaftenblätter

1. *`.vcxproj`* Datei. (Kann Standard- und die Eigenschaftenblatteinstellungen überschreiben.)

1. Elementmetadaten

> [!TIP]
> Auf einer Eigenschaften Seite wird eine **Fett** formatierte Eigenschaft im aktuellen Kontext definiert. Eine Eigenschaft in normaler Schriftart ist geerbt.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>Anzeigen einer erweiterten Projektdatei mit allen importierten Werten

Manchmal ist es hilfreich, die erweiterte Datei anzuzeigen, um zu bestimmen, wie ein bestimmter Eigenschaftswert vererbt wird. Um die erweiterte Version anzuzeigen, geben Sie folgenden Befehl an einer Visual Studio-Eingabeaufforderung ein. (Ändern Sie die Platzhalterdateinamen in die Namen der Dateien, die Sie verwenden möchten.)

> **MSBuild/PP:** _Temp_ **. txt** _myapp_ **. vcxproj**

Erweiterte Projektdateien können groß und schwer zu verstehen sein, es sei denn, Sie sind mit MSBuild vertraut. So sieht die grundlegende Struktur einer Projektdatei aus:

1. Grundlegende Projekteigenschaften, die in der IDE nicht verfügbar gemacht werden.

1. Import von *`Microsoft.cpp.default.props`* , die einige grundlegende, toolsetunabhängige Eigenschaften definiert.

1. Globale Konfigurationseigenschaften (verfügbar als Standardeigenschaften **PlatformToolset** und **Project** auf der Seite **Konfiguration > Allgemein**). Diese Eigenschaften bestimmen, welche Toolset-und systeminternen Eigenschaften Blätter in *`Microsoft.cpp.props`* im nächsten Schritt importiert werden.

1. Der Import von *`Microsoft.cpp.props`* , der die meisten Projekt Standardwerte festlegt.

1. Importieren aller Eigenschaften Blätter, einschließlich *`.user`* Dateien Diese Eigenschaftenblätter können alle Eigenschaften außer die Standardeigenschaften **PlatformToolset** und **Project** überschreiben.

1. Der Rest der Projekt Konfigurations Eigenschaften. Diese Werte können das überschreiben, was in den Eigenschaftenblättern festgelegt wurde.

1. Elemente (Dateien) zusammen mit ihren Metadaten. Diese Elemente sind immer das letzte Wort in den MSBuild-Auswertungs Regeln, auch wenn Sie vor anderen Eigenschaften und Importen auftreten.

Weitere Informationen finden Sie unter [MSBuild-Eigenschaften](/visualstudio/msbuild/msbuild-properties).

## <a name="build-configurations"></a>Buildkonfigurationen

Eine Konfiguration ist nur eine beliebige Gruppe von Eigenschaften, denen ein Name zugewiesen wird. Visual Studio bietet Debug-und Releasekonfigurationen. Jede legt verschiedene Eigenschaften für einen Debugbuild oder Releasebuild entsprechend fest. Sie können den **Configuration Manager** verwenden, um benutzerdefinierte Konfigurationen zu definieren. Sie sind eine bequeme Methode, um Eigenschaften für eine bestimmte Art von Build zu gruppieren.

Um eine bessere Vorstellung von Buildkonfigurationen zu erhalten, öffnen Sie **Eigenschaften-Manager**. Sie können Sie öffnen, indem Sie in Abhängigkeit von Ihren Einstellungen **> Eigenschaften-Manager** anzeigen oder **> anderen Windows-> Eigenschaften-Manager anzeigen**. **Eigenschaften-Manager** verfügt über Knoten für jedes Konfigurations-und Platt Form Paar im Projekt. Unter jedem dieser Knoten befinden sich Knoten für Eigenschaften Blätter ( *`.props`* Dateien), mit denen bestimmte Eigenschaften für diese Konfiguration festgelegt werden.

![Eigenschaften-Manager](media/property-manager.png "Eigenschaften-Manager")

Beispielsweise können Sie auf den Eigenschaften Seiten zum Bereich Allgemein wechseln. Ändern Sie die Eigenschaft Zeichensatz in "nicht festgelegt" anstelle von "Unicode verwenden", und klicken Sie dann auf **OK**. Die Eigenschaften-Manager zeigt jetzt kein Eigenschaften Blatt für die **Unicode-Unterstützung** an. Sie wird für die aktuelle Konfiguration entfernt, ist aber noch für andere Konfigurationen vorhanden.

Weitere Informationen zum Eigenschaften-Manager und zu Eigenschaftenblättern finden Sie unter [Teilen oder Wiederverwenden von Visual Studio C++-Projekteinstellungen](create-reusable-property-configurations.md).

> [!TIP]
> Die *`.user`* -Datei ist ein Legacy Feature. Es wird empfohlen, dass Sie Sie löschen, damit die Eigenschaften entsprechend der Konfiguration und Plattform ordnungsgemäß gruppiert bleiben.
