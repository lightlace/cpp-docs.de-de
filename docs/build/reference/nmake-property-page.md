---
title: Eigenschaftenseite „NMake“ (Windows C++) | Microsoft-Dokumentation
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
ms.openlocfilehash: c0dbe537635fe6698f814f3d8456f0caa9c8c796
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320603"
---
# <a name="nmake-property-page"></a>NMake (Eigenschaftenseite)

Mit der Eigenschaftenseite **NMake** können Sie Buildeinstellungen für NMake-Projekte angeben. (NMAKE ist die Microsoft-Implementierung von [stellen](https://wikipedia.org/wiki/Make_(software)).)

Weitere Informationen über NMake Projekte finden Sie unter [Creating a Makefile Project (Erstellen eines Makefile-Projekts)](creating-a-makefile-project.md). Nicht - Windows-MakeFile-Projekte, finden Sie unter [MakeFile-Projekteigenschaften (Linux C++)](../../linux/prop-pages/makefile-linux.md), [allgemeine Projekteigenschaften (Android C++-Makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) oder [NMake-Eigenschaften (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).

Die Eigenschaftenseite **NMake** enthält die folgenden Eigenschaften:

## <a name="uielement-list"></a>UIElement-Liste

- **Buildbefehlszeile**

   Gibt den Befehl an, der ausgeführt werden soll, wenn im Menü **Erstellen** auf **Erstellen** geklickt wird.

- **Befehlszeile „Alles neu erstellen“**

   Gibt den Befehl an, der ausgeführt werden soll, wenn im Menü **Erstellen** auf **Alles neu erstellen** geklickt wird.

- **Befehlszeile „Bereinigen“**

   Gibt den Befehl an, der ausgeführt werden soll, wenn im Menü **Erstellen** auf **Bereinigen** geklickt wird.

- **Ausgabe**

   Gibt den Namen der Datei an, in der die Ausgabe für die Befehlszeile enthalten ist. Dieser Dateiname basiert standardmäßig auf dem Projektnamen.

- **Präprozessordefinitionen**

   Gibt alle Präprozessordefinitionen an, die die Quelldateien verwenden. Der Standardwert wird durch die aktuelle Plattform und Konfiguration bestimmt.

- **Includesuchpfad**

   Gibt die Verzeichnisse an, in denen der Compiler nach Includedateien sucht.

- **Erzwungene Includedateien**

   Gibt Dateien an, die der Präprozessor automatisch verarbeitet, selbst wenn sie nicht in den Projektdateien enthalten sind.

- **Assemblysuchpfad**

   Gibt die Verzeichnisse an, in denen .NET Framework beim Auflösen von .NET-Assemblys sucht.

- **Erzwungene Verwendung von Assemblys**

   Gibt Assemblys an, die .NET Framework automatisch verarbeitet.

- **Zusätzliche Optionen**

   Gibt alle zusätzlichen Compileroptionen für die Analyse von C++-Dateien durch IntelliSense an.

Informationen über den Zugriff auf die **NMake** auf der Seite finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

Informationen zum programmgesteuerten Zugriff auf Members dieses Objekts finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.

## <a name="see-also"></a>Siehe auch

[Referenz für C++-Projekt Seite](property-pages-visual-cpp.md)<br>
