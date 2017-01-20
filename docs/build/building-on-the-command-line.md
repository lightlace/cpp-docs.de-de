---
title: "Erstellen &#252;ber die Befehlszeile"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Builds [C++], Befehlszeile"
  - "Befehlszeile [C++], Erstellen über"
  - "Befehlszeile [C++], Compiler"
  - "Erstellen über die Befehlszeile [C++]"
  - "Kompilieren von Quellcode [C++], Befehlszeile"
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen &#252;ber die Befehlszeile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können C\- und C\+\+\-Anwendungen in der Befehlszeile erstellen, in dem Sie die in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthaltenen Tools verwenden.  Jede Edition von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installiert ein Befehlszeilentoolset, das einen Compiler, einen Linker und andere Buildtools sowie eine Befehlsdatei enthält, die die erforderliche Buildumgebung festlegt.  Standardmäßig werden diese Tools in *Laufwerk*:\\Program Files \(x86\)\\Microsoft Visual Studio *Version*\\VC\\bin\\ installiert.  \(Das tatsächliche Verzeichnis auf Ihrem Computer hängt vom System, der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Version und Ihren Optionen für die Installation ab.\)  
  
 Für eine ordnungsgemäße Funktionsweise sind für die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Befehlszeilentools verschiedene Umgebungsvariablen erforderlich, die für Ihre Installation angepasst sind.  Wenn [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installiert ist, wird eine vcvarsall.bat\-Befehlsdatei erstellt, die Sie ausführen können, um die erforderlichen Umgebungsvariablen festzulegen.  Außerdem wird eine Verknüpfung erstellt, über die ein Developer\-Eingabeaufforderungsfenster gestartet wird, in dem diese Variablen bereits festgelegt sind.  Diese Umgebungsvariablen sind für Ihre Installation spezifisch und können durch Produktaktualisierungen oder \-upgrades geändert werden.  Daher wird empfohlen, dass Sie vcvarsall.bat oder eine Developer\-Eingabeaufforderungsverknüpfung verwenden, statt sie selbst festzulegen.  Weitere Informationen finden Sie unter [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
### So öffnen Sie ein Developer\-Befehlsaufforderungsfenster  
  
1.  Geben Sie auf dem Windows 8\-Startbildschirm Visual Studio\-Tools ein.  Beachten Sie, dass sich die Suchergebnisse während der Eingabe ändern. Wenn **Visual Studio\-Tools** angezeigt wird, wählen Sie die Option aus.  
  
     In früheren Versionen von Windows wählen Sie **Start** aus, und geben Sie dann in das Suchfeld Visual Studio\-Tools ein.  Wenn **Visual Studio\-Tools** in den Suchergebnissen angezeigt wird, wählen Sie die Option aus.  
  
2.  Öffnen Sie im Ordner **Visual Studio\-Tools** die **Developer\-Befehlsaufforderungg** für Ihre Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 Zum Erstellen eines C\-\/C\+\+\-Projekts in der Befehlszeilen können Sie die folgenden [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Befehlszeilentools verwenden:  
  
 [CL](../build/reference/compiling-a-c-cpp-program.md)  
 Verwenden Sie den Compiler \(cl.exe\), um Quellcodedateien in Apps, Bibliotheken und DLLs zu kompilieren und zu verknüpfen.  
  
 [Link](../build/reference/linking.md)  
 Verwenden Sie den Linker \(link.exe\), um kompilierte Objektdateien in Apps und DLLs zu verknüpfen.  
  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)  
 Verwenden Sie MSBuild \(msbuild.exe\), [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Projekte und [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Lösungen zu erstellen.  Das entspricht der Ausführung des **Build**\-Projeks oder des Befehls **Projektmappe erstellen** in der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-IDE.  
  
 [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md)  
 Verwenden Sie DEVENV \(devenv.exe\) in Kombination mit einem Befehlszeilenswitch, zum Beispiel **\/Build** oder **\/Clean**, um bestimmte Buildbefehle durchzuführen, ohne die [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-IDE anzuzeigen.  
  
 [NMake](../build/nmake-reference.md)  
 Verwenden Sie NMAKE \(nmake.exe\), um Aufgaben zu automatisieren, die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Projekte mithilfe eines herkömmlichen Makefile zu erstellen.  
  
 Wenn Sie über die Befehlszeile erstellen, können Sie Informationen zu Warnmeldungen, Fehlern und Meldungen erhalten, indem Sie [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] starten und dann in der Menüleiste **Hilfe** und **Suchen** auswählen.  
  
## In diesem Abschnitt  
 In den Artikeln in diesem Abschnitt der Dokumentation erfahren Sie, wie Sie Apps über die Befehlszeile erstellen. Zudem wird beschrieben, wie Sie die Befehlszeilen\-Buildumgebung für die Verwendung von 64\-Bit\-Toolsets und das Abzielen auf x86\-, x64\- und ARM\-Plattformen verwenden. Und es wird gezeigt, wie Sie die Befehlszeilen\-Buildtools MSBuild und NMAKE verwenden.  
  
 [Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C\+\+\-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
 Gibt ein Beispiel, das zeigt, wie Sie ein einfaches C\+\+\-Programm über die Befehlszeile erstellen und kompilieren.  
  
 [Exemplarische Vorgehensweise: Kompilieren eines C\-Programms in der Befehlszeile](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
 Beschreibt, wie Sie ein in der Programmiersprache C geschriebenes Programm kompilieren.  
  
 [Exemplarische Vorgehensweise: Kompilieren eines C\+\+\/CLI\-Programms in der Befehlszeile](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)  
 Beschreibt, wie Sie ein C\+\+\-\/CLI\-Programm erstellen und kompilieren, das .NET Framework verwendet.  
  
 [Exemplarische Vorgehensweise: Kompilieren eines C\+\+\/CX\-Programms in der Befehlszeile](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)  
 Beschreibt, wie Sie ein C\+\+\-\/CX\-Programm erstellen und kompilieren, das die Windows Runtime verwendet.  
  
 [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)  
 Beschreibt, wie Sie ein Befehlseingabeaufforderungsfenster starten, in dem die erforderlichen Umgebungsvariablen für Befehlszeilenbuilds festgelegt sind, die auf x86\-, x64\- und ARM\-Plattformen abzielen und für die ein 32\-Bit\- oder 64\-Bit\-Toolset verwendet wird.  
  
 [NMAKE\-Referenz](../build/nmake-reference.md)  
 Enthält Links zu Artikeln, in denen das Microsoft Program Maintenance Utility \(NMAKE.EXE\) beschrieben wird.  
  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)  
 Enthält Links zu Artikeln, in denen die Verwendung von MSBuild.EXE dargestellt wird.  
  
## Verwandte Abschnitte  
 [\/MD, \/MT, \/LD \(Laufzeitbibliothek verwenden\)](../build/reference/md-mt-ld-use-run-time-library.md)  
 Beschreibt die Verwendung dieser Compileroptionen für eine Debug\- oder Releaselaufzeitbibliothek.  
  
 [C\-\/C\+\+\-Compileroptionen](../build/reference/compiler-options.md)  
 Enthält Links zu Artikeln, in denen die C\- und C\+\+\-Compileroptionen sowie CL.exe erläutert werden.  
  
 [Linkeroptionen](../build/reference/linker-options.md)  
 Enthält Links zu Artikeln, in denen die Linkeroptionen und LINK.EXE dargestellt werden.  
  
 [C\-\/C\+\+\-Buildtools](../build/reference/c-cpp-build-tools.md)  
 Enthält Links zu den C\-\/C\+\+\-Buildtools, die in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthalten sind.  
  
## Siehe auch  
 [Erstellen von C\/C\+\+\-Programmen](../build/building-c-cpp-programs.md)