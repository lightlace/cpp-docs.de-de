---
title: "Gewusst wie: &#196;ndern des Zielframeworks und des Plattformtoolsets | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "msbuild.cpp.howto.modifytargetframeworkandplatformtoolset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), Gewusst wie: Ändern des Zielframeworks und des Plattformtoolsets"
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# Gewusst wie: &#196;ndern des Zielframeworks und des Plattformtoolsets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Projekteinstellungen ändern, um andere .NET Framework\-Versionen als Ziel festzulegen, und um andere Plattformtoolsets zu verwenden. Standardmäßig wird vom Projektsystem die .NET Framework\-Version und die Toolsetversion verwendet, die der von Ihnen zum Erstellen des Projekts verwendeten Version von Visual Studio entsprechen. Sie können das Toolset der Zielplattform ändern, indem Sie die Projekteigenschaften ändern. Das Zielframework kann durch Bearbeiten der Projektdatei \(.vcxproj\) geändert werden. Sie müssen keine separate CodeBase für jedes Kompilierungsziel verwenden.  
  
> [!IMPORTANT]
>  Einige Editionen unterstützen möglicherweise geänderte Zielframeworks oder Plattformtoolsets nicht. Informationen zur Kompatibilität finden Sie unter [Portieren, Migrieren und Aktualisieren von Visual Studio\-Projekten](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md).  
  
 Wenn Sie das Zielframework ändern, ändern Sie auch das Plattformtoolset in eine Version, die das Zielframework unterstützt. Um zum Beispiel .NET Framework 4.5 als Ziel festzulegen, müssen Sie ein kompatibles Plattformtoolset wie Visual Studio 2015 \(v140\), Visual Studio 2013 \(v120\) oder Visual Studio 2012 \(v110\) verwenden. Sie können das **Windows7.1SDK**\-Plattformtoolset verwenden, um .NET Framework 2.0, 3,0, 3,5 und 4 sowie x86, Itanium und x64\-Plattformen als Ziel festzulegen.  
  
> [!NOTE]
>  Zum Ändern des Toolsets der Zielplattform muss die zugehörige Version von Visual Studio oder die Windows\-Plattform SDK installiert sein. Um beispielsweise die Itanium\-Plattform mit dem **Windows7.1SDK**\-Plattformtoolset als Ziel festzulegen, muss [Microsoft Windows\-SDK für Windows 7 und .NET Framework 4 SP1](http://www.microsoft.com/download/details.aspx?id=8279) installiert sein. Sie können aber auch eine andere Visual Studio\-Version für die Entwicklung verwenden, sofern Sie die richtige Frameworkversion und das richtige Plattformtoolset als Ziel festlegen.  
  
 Sie können die Zielplattform zusätzlich erweitern, indem Sie ein benutzerdefiniertes Plattformtoolset erstellen. Weitere Informationen finden Sie unter [Systemeigene Festlegung von C\+\+\-Zielversionen](http://go.microsoft.com/fwlink/?LinkId=196619) im Visual C\+\+\-Blog.  
  
### So ändern Sie das Zielframework  
  
1.  Wählen Sie in Visual Studio im **Projektmappen\-Explorer** das Projekt aus. Öffnen Sie auf der Menüleiste das Menü **Projekt**, und wählen Sie **Projekt entladen** aus. Dadurch wird die Projektdatei \(.vcxproj\) für das Projekt entladen.  
  
    > [!NOTE]
    >  Ein C\+\+\-Projekt kann nicht geladen werden, während die Projektdatei in Visual Studio geändert wird. Sie können allerdings einen anderen Editor, wie den Editor in Windows, zum Ändern der Projektdatei verwenden, während das Projekt in Visual Studio geladen wird. Visual Studio erkennt, dass die Projektdatei geändert wurde, und Sie werden aufgefordert, das Projekt erneut zu laden.  
  
2.  Wählen Sie in der Menüleiste das Menü **Datei**, den Menüeintrag **Öffnen** und anschließend **Datei** aus. Navigieren Sie im Dialogfeld **Datei öffnen** zum Projektordner, und öffnen Sie dann die Projektdatei \(.vcxproj\).  
  
3.  Suchen Sie in der Projektdatei den Eintrag für die Framework\-Zielversion. Wenn das Projekt für .NET Framework 4.5 entworfen wurde, suchen Sie `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` im `<PropertyGroup Label="Globals">`\-Element des `<Project>`\-Elements. Wenn das `<TargetFrameworkVersion>`\-Element nicht vorhanden ist, verwendet das Projekt .NET Framework nicht, und es ist keine Änderung erforderlich.  
  
4.  Ändern Sie den Wert in die gewünschte Frameworkversion,  zum Beispiel v3.5 oder v4.6.  
  
5.  Speichern Sie die Änderungen, und schließen Sie den Editor.  
  
6.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für Ihr Projekt, und wählen Sie **Projekt erneut laden** aus.  
  
7.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das Projekt durch Rechtsklick \(nicht für Ihre Projektmappe\), und wählen Sie dann **Eigenschaften** aus, um das Dialogfeld **Eigenschaftenseiten** für Ihr Projekt zu öffnen. Erweitern Sie im linken Bereich des Dialogfelds **Konfigurationseigenschaften**, und wählen Sie dann **Allgemein** aus. Stellen Sie sicher, dass die **.NET Framework\-Zielversion** die neue Frameworkversion anzeigt.  
  
### So ändern Sie das Projekttoolset  
  
1.  Öffnen Sie in Visual Studio im **Projektmappen\-Explorer** das Kontextmenü für das Projekt \(nicht für Ihre Projektmappe\), und wählen Sie dann **Eigenschaften**, um das Dialogfeld **Eigenschaftenseiten** für Ihr Projekt zu öffnen.  
  
2.  Öffnen Sie im Dialogfeld **Eigenschaftenseiten** die Dropdownliste **Konfiguration**, und wählen Sie anschließend **Alle Konfigurationen** aus.  
  
3.  Erweitern Sie im linken Bereich des Dialogfelds **Konfigurationseigenschaften**, und wählen Sie dann **Allgemein** aus.  
  
4.  Wählen Sie im rechten Bereich **Plattformtoolset** und dann das gewünschte Toolset aus der Dropdownliste aus. Wenn Sie beispielsweise das [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)]\-Toolset installiert haben, wählen Sie **Visual Studio 2010 \(v100\)** für das Projekt aus.  
  
5.  Klicken Sie auf die Schaltfläche **OK**.  
  
## Siehe auch  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)