---
title: Eigenschaftenseite „NMake“ (Windows C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs:
- C++
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 030aba197b2f480212f20eb5e9c298461d8f03da
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384779"
---
# <a name="nmake-property-page"></a>NMake (Eigenschaftenseite)

Mit der Eigenschaftenseite **NMake** können Sie Buildeinstellungen für NMake-Projekte angeben.

Weitere Informationen über NMake Projekte finden Sie unter [Creating a Makefile Project (Erstellen eines Makefile-Projekts)](../ide/creating-a-makefile-project.md). Informationen über Makefile-Projekten unter anderen Betriebssystemen finden Sie unter [Makefile-Projekteigenschaften (Linux C++)](../linux/prop-pages/makefile-linux.md), [Allgemeine Projekteigenschaften (Android C++-Makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) oder [NMake-Eigenschaften (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).

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

Informationen dazu, wie Sie auf die **NMake**-Eigenschaftenseite zugreifen, finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).

Informationen zum programmgesteuerten Zugriff auf Members dieses Objekts finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)<br>
[Vorgehensweise: Aktivieren von IntelliSense für Makefile-Projekte](../ide/how-to-enable-intellisense-for-makefile-projects.md)