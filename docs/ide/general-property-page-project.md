---
title: Eigenschaftenseite "Allgemein" (Projekt) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.ManagedExtensions
- VC.Project.VCConfiguration.BuildBrowserInformation
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.ATLMinimizesCRunTimeLibraryUsage
- VC.Project.VCConfiguration.ReferencesPath
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.useOfMfc
- VC.Project.VCConfiguration.CharacterSet
- VC.Project.VCGeneralMakefileSettings.ConfigurationType
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.AppSupport
- VC.Project.VCConfiguration.ToolFiles
- VC.Project.VCConfiguration.useOfATL
dev_langs:
- C++
helpviewer_keywords:
- Clean Build option
- output files, setting directory
- Unicode, creating C++ build configuration
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 772192a4b367760e85bb1631f1ef7b50650af0c1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="general-property-page-project"></a>Eigenschaftenseite "Allgemein" (Projekt)

Wenn Sie mit der rechten Maustaste auf einen Projektknoten im Projektmappen-Explorer, und wählen Sie **Eigenschaften**, **allgemeine** Eigenschaftenseite unter der **Konfigurationseigenschaften** Knoten in der linken Bereich werden zwei Abschnitte mit Eigenschaften angezeigt:

- Allgemein

- Projektstandards

Nicht-Windows-Projekte finden Sie unter [Linux C++-Eigenschaft des Seitenverweises](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="general"></a>Allgemein

Die Eigenschaften im Abschnitt "Allgemein" bestimmen den Speicherort der Dateien, die während des Buildprozesses erstellt werden und welche Dateien beim Löschen, der **Bereinigen** Option (**erstellen** Menü) ausgewählt ist.

**Zielplattform**  
Gibt die Plattform an, auf der das Projekt ausgeführt wird. Beispielsweise Windows, Android oder iOS. Der Wert **Windows 10** bedeutet, dass das Projekt auf die universelle Windows-Plattform. Wenn Sie frühere Versionen von Windows als Ziel dient, die Version nicht aufgeführt ist und der Wert in diesem Feld einfach als wird **Windows**. Dies ist ein schreibgeschütztes Feld, das festgelegt wird, wenn Sie ein Projekt erstellen.

**Windows SDK-Version**  
Für die Zielplattform Windows gibt dies die Version des Windows-SDKS, die das Projekt erforderlich ist. Wenn Sie eine C++-Arbeitsauslastung mit dem Visual Studio-Installer installieren, werden auch die erforderlichen Teile des Windows SDK installiert. Wenn Sie andere Windows SDK-Versionen auf Ihrem Computer verfügen, wird jede Version des SDK-Tools, die Sie installiert haben in der Dropdownliste angezeigt.

Um Windows 7 oder Windows Vista anzugeben, verwenden Sie den Wert **8.1**, da Windows SDK 8.1 abwärtskompatibel für diese Plattformen ist. Darüber hinaus sollten Sie den richtigen Wert für definieren **_WIN32_WINNT** in "targetver.h". Für Windows 7 ist dies "0x0601". Finden Sie unter [Ändern von WINVER und _WIN32_WINNT](../porting/modifying-winver-and-win32-winnt.md).

Sie können die in Visual Studio für die aktuelle Version der Bibliotheken verwenden Sie zum Erstellen von Windows XP und Windows Server 2003-Projekten enthaltene Windows XP-Plattformtoolset installieren. Informationen zum Herunterladen und verwenden dieses Plattformtoolsets finden Sie unter [Konfigurieren von Programmen für Windows XP](../build/configuring-programs-for-windows-xp.md). Weitere Informationen zum Ändern des Plattformtoolsets finden Sie unter [Vorgehensweise: Ändern des Zielframeworks und des Plattformtoolsets](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

**Mindestversion der Zielplattform**   
Gibt die niedrigste Version der Plattform an, auf der das Projekt ausgeführt werden kann. Diese Eigenschaft wird nur angezeigt, wenn der Projekttyp sie unterstützt, z. B. in universellen Windows-Projekten. Wenn Ihre App Features in einer neueren Version des Windows SDK nutzen, unter früheren Versionen aber weiterhin ohne diese Features ausgeführt werden kann (möglicherweise mit verringerter Funktionalität), kann der Wert dieser beiden Eigenschaften unterschiedlich sein. Ist dies der Fall, sollte in Ihrem Code zur Laufzeit die Version der Plattform geprüft werden, auf der er ausgeführt wird. Es sollte nicht versucht werden, Features zu verwenden, die in älteren Plattformversionen nicht verfügbar sind.

Beachten Sie, dass Visual C++ diese Option nicht erzwingt. Sie ist aus Gründen der Konsistenz mit anderen Sprachen wie C# und JavaScript sowie als Leitfaden für jede Person eingefügt, die Ihr Projekt verwendet. Visual C++ generiert keinen Fehler, wenn Sie eine Funktion verwenden, das in der Mindestversion nicht verfügbar ist.

**Ausgabeverzeichnis**  
Legt das Verzeichnis fest, in dem Tools wie Linker alle endgültigen Ausgabedateien ablegen, die während des Buildprozesses erstellt werden. In der Regel handelt es sich um Ausgabedateien von Tools wie Linker, Bibliothekar oder BSCMake. Standardmäßig ist diese Eigenschaft durch die Makros $(SolutionDir) $(Konfiguration) angegebene Verzeichnis \.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A>.

**Zwischenverzeichnis**  
Legt das Verzeichnis fest, in dem Tools wie der Compiler alle Zwischendateien ablegt, die während des Buildprozesses erstellt werden. In der Regel handelt es sich um Ausgabedateien von Tools wie C/C++-Compiler, MIDL und Ressourcencompiler. Diese Eigenschaft ist standardmäßig das Verzeichnis, die gemäß des Makros $(Konfiguration) \.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A>.

**Zielname**  
Gibt den von diesem Projekt generierten Dateinamen an. Standardmäßig ist diese Eigenschaft den Dateinamen, die durch das Makro $(projectname) angegeben.

**Zielerweiterung**  
Gibt die vom Projekt generierte Dateierweiterung an, z. B. .exe oder .dll.

**Bei der Bereinigung zu löschende Erweiterungen**  
Die **Bereinigen** Option (**erstellen** Menü) Löscht Dateien aus dem Zwischenverzeichnis, an dem Konfiguration des Projekts erstellt wird. Dateien mit Erweiterungen, die durch diese Eigenschaft festgelegt werden, werden gelöscht, sobald **Bereinigen** ausgeführt wird oder wenn Sie eine Wiederherstellung ausführen. Zusätzlich zu Dateien, die über diese Erweiterungen verfügen und sich im Zwischenverzeichnis befinden, werden vom Buildsystem alle bekannten Ausgaben (einschließlich Zwischenausgaben wie OBJ-Dateien) des Builds unabhängig von ihrem Speicherort gelöscht. Sie können auch Platzhalterzeichen angeben.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>.

**Buildprotokolldatei**  
Ermöglicht es Ihnen, ein vom Standardspeicherort abweichendes Verzeichnis für die Protokolldatei anzugeben, die bei jedem Erstellen eines Projekts generiert wird. Der Standardspeicherort wird durch die Makros $(intdir)$ (MSBuildProjectName) .log angegeben.

Sie können Projektmakros verwenden, um den Verzeichnispfad zu ändern. Finden Sie unter [allgemeine Makros für Buildbefehle und-Eigenschaften](../ide/common-macros-for-build-commands-and-properties.md).

**Plattformtoolset**  
Ermöglicht eine Ausrichtung des Projekts auf andere Versionen der Visual C++-Bibliotheken und des Compilers. Visual C++-Projekte können entweder das Visual Studio oder eines Toolsets installiert, indem Sie mehrere früheren Versionen von Visual Studio, einschließlich Toolsets, die ausführbaren Dateien zu erstellen, mit dem auf Windowx XP installierte Standardtoolset abzielen. Informationen zum Ändern des Plattformtoolsets finden Sie unter [Vorgehensweise: Ändern des Zielframeworks und Plattformtoolset](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

**Aktivieren der verwalteten inkrementellen Build**  
Für verwaltete Projekte kann diese erkannt werden der Außenstehenden Einsicht in Assemblys zu generieren. Wenn eine Änderung an einem verwalteten Projekt nicht auf andere Projekte angezeigt wird, werden abhängige Projekte nicht neu erstellt. Dies kann Buildzeiten in Projektmappen, die verwaltete Projekte enthalten, erheblich verbessern.

## <a name="project-defaults"></a>Projektstandards

Die Eigenschaften im Abschnitt “Projektstandards“ stellen änderbare Standardeigenschaften dar. Die Definition für diese Eigenschaften finden Sie in den PROPS-Dateien in *Installationsverzeichnis*\VC\VCProjectDefaults.

**Konfigurationstyp**  
Sie können aus einer Reihe unterschiedlicher Konfigurationstypen auswählen:

- **Anwendung (.exe)**, zeigt das Linkertoolset (C/C++-Compiler, MIDL, Ressourcencompiler, Linker, BSCMake, XML-Webdienst-Proxy-Generator, benutzerdefinierte Build-, Prebuild-, Prelink- und Postbuildereignisse).

- **Dynamische Bibliothek (.dll)**, zeigt das Linkertoolset, legt die/DLL-Linkeroption fest und fügt für CL die _WINDLL-Definition.

- **Makefile**, zeigt das Makefiletoolset (NMake).

- **Statische Bibliothek (.lib)**, zeigt das Bibliothekstoolset an (identisch mit dem Linkertoolset außer Linker, Bibliothekar ersetzen und XML-Webdienst-Proxy-Generator).

- **Hilfsprogramm**, zeigt das Hilfsprogramm-Toolset (MIDL, benutzerdefinierte Build-, Prebuild-, Postbuildereignisse) an.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A>.

**Verwendung von MFC**  
Legt fest, ob das MFC-Projekt statisch oder dynamisch mit der MFC-DLL verknüpft wird. MFC-fremde Projekte Auszuwählender **Windows-Standardbibliotheken verwenden** mit verschiedenen Win32-Bibliotheken verknüpfen, die bei Verwendung von MFC einbezogen werden.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>.

**Verwendung von ATL**  
Legt fest, ob das ATL-Projekt statisch oder dynamisch mit der ATL-DLL verknüpft wird. Wenn Sie eine andere als **ATL wird nicht verwendet**, eine Definition für des Compilers hinzugefügt wird **Befehlszeile** Eigenschaftenseite.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL%2A>.

**Zeichensatz**  
Legt fest, ob _UNICODE oder _MBCS verwendet werden soll. Außerdem kann sich diese Option ggf. auf den Linkereinstiegspunkt auswirken.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>.

**Common Language Runtime-Unterstützung**  
Bewirkt, dass die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption verwendet werden.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>.

**.NET Framework-Zielversion**  
In verwalteten Projekten gibt die .NET Framework-Version zum Ziel.

**Optimierung des gesamten Programms**  
Gibt an, die [/GL](../build/reference/gl-whole-program-optimization.md) (Compileroption) und [/LTCG](../build/reference/ltcg-link-time-code-generation.md) (Linkeroption). Standardmäßig ist dies für Debugkonfigurationen deaktiviert und für Einzelhandel Konfigurationen aktiviert.

**Unterstützung für Windows Store-App**  
Gibt an, ob dieses Projekt (universelle Windows-Plattform) für Windows-Runtime-apps unterstützt. Weitere Informationen finden Sie unter [/ZW (Windows-Runtime-Kompilierung)](../build/reference/zw-windows-runtime-compilation.md), und im Windows Developer Center.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)  