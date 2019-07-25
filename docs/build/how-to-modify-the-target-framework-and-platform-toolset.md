---
title: 'Vorgehensweise: Ändern des Ziel Frameworks und des Platt Form Toolsets'
ms.custom: conceptual
ms.date: 07/24/2019
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
ms.openlocfilehash: 6af7a4eb47c1d3f8b9c52eec39795c9307ca9d8e
ms.sourcegitcommit: ce3393846c86e7905ff0c86e4cd6610476809585
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2019
ms.locfileid: "68492233"
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>Vorgehensweise: Ändern des Ziel Frameworks und des Platt Form Toolsets

Sie können eine Visual Studio C++ -Projektdatei bearbeiten, um verschiedene Versionen des C++ Platt Form Toolsets, den Windows SDK und die .NET FrameworkC++(nur/CLI-Projekte) als Ziel festzulegen. Standardmäßig wird vom Projektsystem die .NET Framework-Version und die Toolsetversion verwendet, die der von Ihnen zum Erstellen des Projekts verwendeten Version von Visual Studio entsprechen. Sie können alle diese Werte in der vcxproj-Datei ändern, damit Sie die gleiche Codebasis für jedes Kompilierungs Ziel verwenden können.

## <a name="platform-toolset"></a>Platt Form Toolset

Das Platt Form Toolset besteht aus C++ dem Compiler (cl. exe) und dem Linker (Link. exe) zusammen mit den CC++ /Standard-Bibliotheken. Seit Visual Studio 2015 ist die Hauptversion des Toolsets 14. Dies bedeutet, dass Projekte, die mit Visual Studio 2019 oder Visual Studio 2017 kompiliert wurden, mit mit Visual Studio 2015 kompilierten Projekten ABI-abwärts kompatibel sind. Die neben Version wurde für jede Version seit Visual Studio 2015 um 1 aktualisiert:

- Visual Studio 2015: V140
- Visual Studio 2017: v141
- Visual Studio 2019: v142

Diese Toolsets unterstützen .NET Framework 4,5 und höher.

Visual Studio unterstützt auch die fest C++ Steuerung von zielprojekten. Sie können die Visual Studio-IDE verwenden, um Projekte zu bearbeiten und zu erstellen, die mit älteren Versionen von Visual Studio erstellt wurden, ohne Sie zu aktualisieren, um eine neue Version des Toolsets zu verwenden. Die älteren Toolsets müssen auf dem Computer installiert sein. Weitere Informationen finden Sie unter [Verwenden der nativen fest Zuweisungs Ziel-Zielplattform in Visual Studio](../porting/use-native-multi-targeting.md). Beispielsweise können Sie in Visual Studio 2015 .NET Framework 2,0 als *Ziel* verwenden, aber Sie müssen ein früheres Toolset verwenden, das es unterstützt.

## <a name="target-framework-ccli-project-only"></a>Ziel Framework (C++nur/CLI-Projekt)

Wenn Sie das Zielframework ändern, ändern Sie auch das Plattformtoolset in eine Version, die das Zielframework unterstützt. Um zum Beispiel .NET Framework 4.5 als Ziel festzulegen, müssen Sie ein kompatibles Plattformtoolset wie Visual Studio 2015 (v140), Visual Studio 2013 (v120) oder Visual Studio 2012 (v110) verwenden. Sie können das [Windows 7,1 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=8279) -Platt Form Toolset verwenden, um die .NET Framework 2,0, 3,0, 3,5 und 4 sowie die x86/x64-Plattformen als Ziel festzulegen.

Sie können die Zielplattform zusätzlich erweitern, indem Sie ein benutzerdefiniertes Plattformtoolset erstellen. Weitere Informationen finden Sie unter [Systemeigene Festlegung von C++-Zielversionen](https://blogs.msdn.microsoft.com/vcblog/2009/12/08/c-native-multi-targeting/) im Visual C++-Blog.

### <a name="to-change-the-target-framework"></a>So ändern Sie das Zielframework

1. Wählen Sie in Visual Studio im **Projektmappen-Explorer**das Projekt aus. Öffnen Sie auf der Menüleiste das Menü **Projekt** , und wählen Sie **Projekt entladen**aus. Dadurch wird die Projektdatei (.vcxproj) für das Projekt entladen.

   > [!NOTE]
   >  Ein C++-Projekt kann nicht geladen werden, während die Projektdatei in Visual Studio geändert wird. Sie können allerdings einen anderen Editor, wie den Editor in Windows, zum Ändern der Projektdatei verwenden, während das Projekt in Visual Studio geladen wird. Visual Studio erkennt, dass die Projektdatei geändert wurde, und Sie werden aufgefordert, das Projekt erneut zu laden.

1. Wählen Sie in der Menüleiste das Menü **Datei**, den Menüeintrag **Öffnen**und anschließend **Datei**aus. Navigieren Sie im Dialogfeld **Datei öffnen** zum Projektordner, und öffnen Sie dann die Projektdatei (.vcxproj).

1. Suchen Sie in der Projektdatei den Eintrag für die Framework-Zielversion. Wenn das Projekt für .NET Framework 4.5 entworfen wurde, suchen Sie `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` im `<PropertyGroup Label="Globals">` -Element des `<Project>` -Elements. Wenn das `<TargetFrameworkVersion>` -Element nicht vorhanden ist, verwendet das Projekt .NET Framework nicht, und es ist keine Änderung erforderlich.

1. Ändern Sie den Wert in die gewünschte Frameworkversion,  zum Beispiel v3.5 oder v4.6.

1. Speichern Sie die Änderungen, und schließen Sie den Editor.

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für Ihr Projekt, und wählen Sie **Projekt erneut laden**aus.

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt durch Rechtsklick (nicht für Ihre Projektmappe), und wählen Sie dann **Eigenschaften** aus, um das Dialogfeld **Eigenschaftenseiten** für Ihr Projekt zu öffnen. Erweitern Sie im linken Bereich des Dialogfelds **Konfigurationseigenschaften** , und wählen Sie dann **Allgemein**aus. Stellen Sie sicher, dass die **.NET Framework-Zielversion** die neue Frameworkversion anzeigt.

### <a name="to-change-the-platform-toolset"></a>So ändern Sie das Platt Form Toolset

1. Öffnen Sie in Visual Studio im **Projektmappen-Explorer**das Kontextmenü für das Projekt (nicht für Ihre Projektmappe), und wählen Sie dann **Eigenschaften** , um das Dialogfeld **Eigenschaftenseiten** für Ihr Projekt zu öffnen.

1. Öffnen Sie im Dialogfeld **Eigenschaftenseiten** die Dropdownliste **Konfiguration** , und wählen Sie anschließend **Alle Konfigurationen**aus.

1. Erweitern Sie im linken Bereich des Dialogfelds **Konfigurationseigenschaften** , und wählen Sie dann **Allgemein**aus.

1. Wählen Sie im rechten Bereich **Plattformtoolset** und dann das gewünschte Toolset aus der Dropdownliste aus. Wenn Sie z. b. das Visual Studio 2010-Toolset installiert haben, wählen Sie **Visual Studio 2010 (V100)** aus, um es für Ihr Projekt zu verwenden.

1. Klicken Sie auf die Schaltfläche **OK** .

## <a name="see-also"></a>Siehe auch

[MSBuild on the Command Line – C++ (C++: MSBuild in der Befehlszeile)](msbuild-visual-cpp.md)
