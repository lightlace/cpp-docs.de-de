---
title: Referenz zu MSBuild für C++-Projekten in Visual Studio
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: b6ec6b5d276cb7104cf61c229476596d2a2a7684
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024698"
---
# <a name="msbuild-reference-for-c-projects"></a>Referenz zu MSBuild für C++-Projekte

MSBuild ist das systemeigene Buildsystem für alle Projekte in Visual Studio, einschließlich der C++-Projekte. Wenn Sie ein Projekt in der integrierten Entwicklungsumgebung (IDE) von Visual Studio erstellen, ruft es msbuild.exe-Tools, die wiederum die VCXPROJ-Datei und verschiedene targets- und PROPS-Dateien verwendet. Im Allgemeinen wird dringend empfohlen mithilfe von Visual Studio-IDE zum Festlegen von Projekteigenschaften und Aufrufen von MSBuild. Bearbeiten von Projektdateien manuell kann zu schwerwiegenden Problemen führen nicht ordnungsgemäß ausgeführt.

Wenn Sie MSBuild direkt über die Befehlszeile verwenden möchten, finden Sie unter [Verwenden von MSBuild über die Befehlszeile](../msbuild-visual-cpp.md). Im Allgemeinen finden Sie weitere Informationen zu MSBuild [MSBuild](/visualstudio/msbuild/msbuild) in Visual Studio-Dokumentation.

## <a name="in-this-section"></a>In diesem Abschnitt

[Merkmale von MSBuild für C++-Projekte](msbuild-visual-cpp-overview.md)<br/>
Informationen darüber, wie Eigenschaften und Ziele gespeichert und verarbeitet werden.

[Gängige Makros für Buildbefehle und -eigenschaften](common-macros-for-build-commands-and-properties.md)<br/>
Beschreibt die Makros (Kompilierzeit-Konstanten), die verwendet werden können, um Eigenschaften wie Pfade und Produktversionen zu definieren.

[Für C++-Projekte erstellte Dateitypen](file-types-created-for-visual-cpp-projects.md)<br/>
Beschreibt die verschiedenen Arten von Dateien, die Visual Studio erstellt die für verschiedene Projekttypen zur Verfügung.

[Visual Studio C++-Projektvorlagen](visual-cpp-project-types.md)<br>
Beschreibt die MSBuild-basiertes Projekt-Typen, die für C++ zur Verfügung stehen.

[Neue C++-Elementvorlagen](using-visual-cpp-add-new-item-templates.md)<br>
Beschreibt, Quelldateien und andere Elemente, die Sie ein Visual Studio-Projekt hinzufügen können.

[Vorkompilierte Headerdateien](../creating-precompiled-header-files.md) wie die Verwendung von vorkompilierten Headerdateien und erstellen Ihre eigenen benutzerdefinierten Code, um Entwicklungszeiten zu beschleunigen vorkompilierte.

[Referenz für Visual Studio-Projekt](property-pages-visual-cpp.md)<br/>
Referenzdokumentation für die Projekteigenschaften, die in der Visual Studio-IDE festgelegt werden.

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](c-cpp-building-reference.md)