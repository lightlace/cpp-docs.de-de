---
title: MSBuild in der Befehlszeile – C++
ms.date: 12/12/2018
helpviewer_keywords:
- MSBuild
ms.assetid: 7a1be7ff-0312-4669-adf2-5f5bf507d560
ms.openlocfilehash: e95d99cf5c63c824bb9bade8e76bc3ca99079669
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220576"
---
# <a name="msbuild-on-the-command-line---c"></a>MSBuild in der Befehlszeile – C++

Im Allgemeinen empfehlen wir, dass Sie Visual Studio zum Festlegen von Projekteigenschaften, und rufen das MSBuild-System verwenden. Sie können jedoch die **MSBuild** Tool direkt von der Befehlszeile aus. Der Buildprozess wird durch die Informationen in einer Projektdatei (.vcxproj) gesteuert, die Sie erstellen und bearbeiten können. Die Projektdatei gibt an, basierend auf Buildoptionen Phasen, Bedingungen und Ereignisse erstellen. Darüber hinaus können Sie angeben, 0 (null) oder mehr Befehlszeile *Optionen* Argumente.

> **MSBuild.exe** [ *Project_file* ] [ *Optionen* ]

Verwenden der **/target** (oder **/t /**) und **"/ Property"** (oder **/p**) außer Kraft setzen, bestimmte Eigenschaften und Ziele, die Befehlszeilenoptionen in der Projektdatei angegeben.

Eine wesentliche Funktion der Projektdatei ist an eine *Ziel*, d.h., dass eine bestimmte Operation zu Ihrem Projekt, und die Eingaben und Ausgaben, die zum Ausführen dieses Vorgangs erforderlich sind. Eine Projektdatei kann ein oder mehrere Ziele angeben, zu denen auch ein Standardziel gehören kann.

Jedes Ziel besteht aus einer Sequenz von einem oder mehreren *Aufgaben*. Jede Aufgabe wird durch eine .NET Framework-Klasse dargestellt, die einen ausführbaren Befehl enthält. Z. B. die [CL-Aufgabe](/visualstudio/msbuild/cl-task) enthält die [cl.exe](reference/compiling-a-c-cpp-program.md) Befehl.

Ein *Aufgabenparameter* ist eine Eigenschaft der Klassenaufgabe und stellt in der Regel eine Befehlszeilenoption des ausführbaren Befehls dar. Z. B. die `FavorSizeOrSpeed` Parameter, der die `CL` Task entspricht der **/OS** und **/Ot** Compileroptionen.

Zusätzliche Aufgabenparameter unterstützen die MSBuild-Infrastruktur. Der `Sources`-Aufgabenparameter gibt z. B. einen Satz von Aufgaben an, die von anderen Aufgaben genutzt werden können. Weitere Informationen zu MSBuild-Aufgaben, finden Sie unter [Aufgabenreferenz](/visualstudio/msbuild/msbuild-task-reference).

Die meisten Aufgaben erfordern Eingaben und Ausgaben, z. B. Dateinamen, Pfade und Zeichenfolgenparameter bzw. numerische oder boolesche Parameter. Eine allgemeine Eingabe ist z. B. der Name einer zu kompilierenden CPP-Quelldatei. Ein wichtiger Eingabeparameter ist eine Zeichenfolge, der angibt, die Buildkonfiguration und Plattform, z. B. "Debug\|Win32". Eingaben und Ausgaben werden von einem oder mehreren benutzerdefinierten XML-`Item`-Elementen angegeben, die in einem `ItemGroup`-Element enthalten sind.

Eine Projektdatei kann auch angeben, eine benutzerdefinierte *Eigenschaften* und `ItemDefinitionGroup` *Elemente*. Eigenschaften und Elemente bilden Name-Wert-Paare, die als Variablen im Build verwendet werden können. Die Namenskomponente eines Paars definiert ein *Makro*, und die Wertkomponente deklariert den *Makrowert*. Ein erfolgt mithilfe von $(*Namen*)-Notation ein, und ein Elementmakro erfolgt mithilfe der %(*Namen*) Notation.

Andere XML-Elemente in einer Projektdatei können Makros testen und anschließend den Wert eines Makros bedingt festlegen oder die Ausführung des Builds steuern. Makronamen und Literalzeichenfolgen können verkettet werden, um Konstrukte, wie z. B. einen Pfad oder einen Dateinamen, zu generieren. In der Befehlszeile die **"/ Property"** Option legt fest oder überschreibt eine Projekteigenschaft. Auf Elemente kann in der Befehlszeile nicht verwiesen werden.

Das MSBuild-System kann vor bzw. nach einem anderen Ziel ein Ziel bedingt ausführen. Das System kann außerdem ein Ziel aufgrund dessen erstellen, ob die Dateien, die das Ziel nutzt, neuer als die vom Ziel ausgegebenen Dateien sind.

Weitere Informationen zu MSBuild finden Sie unter:

- [MSBuild](/visualstudio/msbuild/msbuild) Übersicht der MSBuild-Konzepte.

- [MSBuild-Referenz](/visualstudio/msbuild/msbuild-reference) Referenzinformationen zum MSBuild-System.

- [Projekt-Verweis auf Konfigurationsdateischema](/visualstudio/msbuild/msbuild-project-file-schema-reference) werden die MSBuild-XML-Schema-Elemente, sowie ihre Attribute sowie die übergeordneten und untergeordneten Elementen aufgelistet. Beachten Sie insbesondere die [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [Ziel](/visualstudio/msbuild/target-element-msbuild), und [Aufgabe](/visualstudio/msbuild/task-element-msbuild) Elemente.

- [Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference) beschreibt die Befehlszeilenargumente und die Optionen, mit denen Sie mit msbuild.exe.

- [Task Reference](/visualstudio/msbuild/msbuild-task-reference) Beschreibt MSBuild-Aufgaben. Beachten Sie insbesondere diese Aufgaben, die Visual C++-spezifisch sind: [BscMake-Aufgabe](/visualstudio/msbuild/bscmake-task), [CL-Aufgabe](/visualstudio/msbuild/cl-task), [CPPClean-Aufgabe](/visualstudio/msbuild/cppclean-task), [LIB-Aufgabe](/visualstudio/msbuild/lib-task), [Link-Aufgabe](/visualstudio/msbuild/link-task), [MIDL-Aufgabe](/visualstudio/msbuild/midl-task), [MT-Aufgabe](/visualstudio/msbuild/mt-task), [RC-Aufgabe](/visualstudio/msbuild/rc-task), [SetEnv-Aufgabe](/visualstudio/msbuild/setenv-task), [VCMessage-Aufgabe](/visualstudio/msbuild/vcmessage-task)

## <a name="in-this-section"></a>In diesem Abschnitt

|Begriff|Definition|
|----------|----------------|
|[Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines C++-Projekts](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)|Veranschaulicht das Erstellen eines Visual Studio C++ -Projekt mit **MSBuild**.|
|[Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten](how-to-use-build-events-in-msbuild-projects.md)|Veranschaulicht, wie eine Aktion angeben, die zu einem Zeitpunkt Linkschritt im Build tritt auf,:, bevor der Build gestartet wird. Bevor Sie die Link-Schritt-beginnt. oder nach dem Ende des Buildvorgangs.|
|[Vorgehensweise: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten](how-to-add-a-custom-build-step-to-msbuild-projects.md)|Veranschaulicht, wie eine benutzerdefinierte Phase die Buildsequenz hinzufügen.|
|[Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten](how-to-add-custom-build-tools-to-msbuild-projects.md)|Veranschaulicht, wie eine bestimmte Datei Buildtool zugeordnet werden soll.|
|[Vorgehensweise: Integrieren von benutzerdefinierte Tools in die Projekteigenschaften](how-to-integrate-custom-tools-into-the-project-properties.md)|Veranschaulicht das Hinzufügen von Optionen für ein benutzerdefiniertes Tool in den Projekteigenschaften.|
|[Vorgehensweise: Ändern des Zielframeworks und des Plattformtoolsets](how-to-modify-the-target-framework-and-platform-toolset.md)|Veranschaulicht, wie ein Projekt für mehrere Frameworks oder Toolsets zu kompilieren.|

## <a name="see-also"></a>Siehe auch

[Verwenden des MSVC-Toolsets über die Befehlszeile](building-on-the-command-line.md)
