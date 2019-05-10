---
title: 'Vorgehensweise: Ändern des Zielframeworks und Plattformtoolset'
ms.custom: conceptual
ms.date: 05/06/2019
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
ms.openlocfilehash: c3d6b50a57cab9cc63657949fceccebf4ea6b8c9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220678"
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>Vorgehensweise: Ändern des Zielframeworks und Plattformtoolset

Sie können Visual Studio ändern C++ projekteinstellungen, verschiedene Versionen von .NET Framework als Ziel und andere Plattformtoolsets zu verwenden. Standardmäßig wird vom Projektsystem die .NET Framework-Version und die Toolsetversion verwendet, die der von Ihnen zum Erstellen des Projekts verwendeten Version von Visual Studio entsprechen. Sie können das Toolset der Zielplattform ändern, indem Sie die Projekteigenschaften ändern. Das Zielframework kann durch Bearbeiten der Projektdatei (.vcxproj) geändert werden. Sie müssen keine separate CodeBase für jedes Kompilierungsziel verwenden.

> [!IMPORTANT]
>  Einige Editionen unterstützen möglicherweise geänderte Zielframeworks oder Plattformtoolsets nicht. Weitere Informationen zur Kompatibilität finden Sie unter [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects).

Wenn Sie das Zielframework ändern, ändern Sie auch das Plattformtoolset in eine Version, die das Zielframework unterstützt. Um zum Beispiel .NET Framework 4.5 als Ziel festzulegen, müssen Sie ein kompatibles Plattformtoolset wie Visual Studio 2015 (v140), Visual Studio 2013 (v120) oder Visual Studio 2012 (v110) verwenden. Sie können das **Windows7.1SDK** -Plattformtoolset verwenden, um .NET Framework 2.0, 3,0, 3,5 und 4 sowie x86, Itanium und x64-Plattformen als Ziel festzulegen.

> [!NOTE]
>  Zum Ändern des Toolsets der Zielplattform muss die zugehörige Version von Visual Studio oder die Windows-Plattform SDK installiert sein. Um beispielsweise die Itanium-Plattform mit dem **Windows7.1SDK** -Plattformtoolset als Ziel festzulegen, muss [Microsoft Windows-SDK für Windows 7 und .NET Framework 4 SP1](http://www.microsoft.com/download/details.aspx?id=8279) installiert sein. Sie können aber auch eine andere Visual Studio-Version für die Entwicklung verwenden, sofern Sie die richtige Frameworkversion und das richtige Plattformtoolset als Ziel festlegen.

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

### <a name="to-change-the-project-toolset"></a>So ändern Sie das Projekttoolset

1. Öffnen Sie in Visual Studio im **Projektmappen-Explorer**das Kontextmenü für das Projekt (nicht für Ihre Projektmappe), und wählen Sie dann **Eigenschaften** , um das Dialogfeld **Eigenschaftenseiten** für Ihr Projekt zu öffnen.

1. Öffnen Sie im Dialogfeld **Eigenschaftenseiten** die Dropdownliste **Konfiguration** , und wählen Sie anschließend **Alle Konfigurationen**aus.

1. Erweitern Sie im linken Bereich des Dialogfelds **Konfigurationseigenschaften** , und wählen Sie dann **Allgemein**aus.

1. Wählen Sie im rechten Bereich **Plattformtoolset** und dann das gewünschte Toolset aus der Dropdownliste aus. Wählen Sie beispielsweise, wenn Sie das Toolset von Visual Studio 2010 installiert haben, **Visual Studio 2010 (v100)** für Ihr Projekt verwendet.

1. Klicken Sie auf die Schaltfläche **OK** .

## <a name="see-also"></a>Siehe auch

[MSBuild in der Befehlszeile – C++](msbuild-visual-cpp.md)
