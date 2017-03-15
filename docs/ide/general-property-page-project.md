---
title: "Eigenschaftenseite &quot;Allgemein&quot; (Projekt) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCConfiguration.IntermediateDirectory"
  - "VC.Project.VCConfiguration.ConfigurationType"
  - "VC.Project.VCConfiguration.ManagedExtensions"
  - "VC.Project.VCConfiguration.BuildBrowserInformation"
  - "VC.Project.VCConfiguration.BuildLogFile"
  - "VC.Project.VCConfiguration.PlatformToolset"
  - "VC.Project.VCConfiguration.TargetName"
  - "VC.Project.VCConfiguration."
  - "VC.Project.VCConfiguration.TargetExt"
  - "VC.Project.VCConfiguration.ATLMinimizesCRunTimeLibraryUsage"
  - "VC.Project.VCConfiguration.ReferencesPath"
  - "VC.Project.VCConfiguration.DeleteExtensionsOnClean"
  - "VC.Project.VCConfiguration.useOfMfc"
  - "VC.Project.VCConfiguration.CharacterSet"
  - "VC.Project.VCGeneralMakefileSettings.ConfigurationType"
  - "VC.Project.VCConfiguration.OutputDirectory"
  - "VC.Project.VCConfiguration.AppSupport"
  - "VC.Project.VCConfiguration.ToolFiles"
  - "VC.Project.VCConfiguration.useOfATL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bereinigen (Option im Menü) Erstellen"
  - "Ausgabedateien, Festlegen des Verzeichnisses"
  - "Unicode, Erstellen einer C++-Buildkonfiguration"
ms.assetid: 593b383c-cd0f-4dcd-ad65-9ec9b4b19c45
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# Eigenschaftenseite &quot;Allgemein&quot; (Projekt)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie im Projektmappen\-Explorer mit der rechten Maustaste auf einen Projektknoten klicken und **Eigenschaften** auswählen, werden auf der Eigenschaftenseite **Allgemein** unterhalb des Knotens **Konfigurationseigenschaften** im linken Bereich zwei Abschnitte mit Eigenschaften angezeigt:  
  
-   Allgemein  
  
-   Projektstandards  
  
## Allgemein  
 Die Eigenschaften im Abschnitt “Allgemein“ bestimmen den Speicherort der Dateien, die während des Buildvorgangs erstellt werden, und legen fest, welche Dateien bei Auswahl der Option **Bereinigen** \(Menü **Erstellen**\) gelöscht werden.  
  
 **Zielplattform**  
 Gibt die Plattform an, auf der das Projekt ausgeführt wird. Beispielsweise Windows, Android oder iOS. Der Wert **Windows 10** bedeutet, dass das Projekt für die Universelle Windows\-Plattform vorgesehen ist. Wenn Sie auf frühere Versionen von Windows abzielen, wird die Version nicht aufgeführt, und der Wert in diesem Feld wird einfach als **Windows** angezeigt. Dies ist ein schreibgeschütztes Feld, das festgelegt wird, wenn Sie ein Projekt erstellen.  
  
 **Version der Zielplattform**  
 Gibt für die Windows\-Plattform die Version des Windows SDK an, mit dem Ihr Projekt erstellt wird. Für Windows ist dies die Windows SDK\-Version.[!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] umfasst Windows SDK 8.1. Wenn Sie die [Tools für Windows 10](http://go.microsoft.com/fwlink/p/?LinkId=617631) installiert haben, wird jede Version der Tools, die Sie installiert haben, in der Dropdownliste angezeigt.  
  
 Um Windows 7 oder Windows Vista anzugeben, verwenden Sie den Wert **8.1**, da Windows SDK 8.1 abwärtskompatibel für diese Plattformen ist. Darüber hinaus müssen Sie den entsprechenden Wert für \_WIN32\_WINNT in "targetver.h" definieren. Für Windows 7 ist dies "0x0601". Siehe [Ändern von WINVER und \_WIN32\_WINNT](../porting/modifying-winver-and-win32-winnt.md).  
  
 Sie können das in [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] enthaltene v110\_xp\-Plattformtoolset so installieren, dass die aktuelle Version von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] zum Erstellen von Windows XP\- und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]\-Projekten verwendet wird. Weitere Informationen zum Herunterladen und Verwenden dieses Plattformtoolsets finden Sie unter [Konfigurieren von C\+\+ 11\-Programmen für Windows XP](../build/configuring-programs-for-windows-xp.md). Weitere Informationen zum Ändern des Plattformtoolsets finden Sie unter [Gewusst wie: Ändern des Zielframeworks und des Plattformtoolsets](../build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
 **Mindestversion der Zielplattform**  
 Gibt die niedrigste Version der Plattform an, auf der das Projekt ausgeführt werden kann. Diese Eigenschaft wird nur angezeigt, wenn der Projekttyp sie unterstützt, z. B. in universellen Windows\-Projekten. Wenn Ihre App Features in einer neueren Version des Windows SDK nutzen, unter früheren Versionen aber weiterhin ohne diese Features ausgeführt werden kann \(möglicherweise mit verringerter Funktionalität\), kann der Wert dieser beiden Eigenschaften unterschiedlich sein. Ist dies der Fall, sollte in Ihrem Code zur Laufzeit die Version der Plattform geprüft werden, auf der er ausgeführt wird. Es sollte nicht versucht werden, Features zu verwenden, die in älteren Plattformversionen nicht verfügbar sind.  
  
 Beachten Sie, dass Visual C\+\+ diese Option nicht erzwingt. Sie ist aus Gründen der Konsistenz mit anderen Sprachen wie C\# und JavaScript sowie als Leitfaden für jede Person eingefügt, die Ihr Projekt verwendet. Visual C\+\+ generiert keinen Fehler, wenn Sie ein Feature verwenden, das in der Mindestversion nicht verfügbar ist.  
  
 **Ausgabeverzeichnis**  
 Legt das Verzeichnis fest, in dem Tools wie Linker alle endgültigen Ausgabedateien ablegen, die während des Buildprozesses erstellt werden. In der Regel handelt es sich um Ausgabedateien von Tools wie Linker, Bibliothekar oder BSCMake.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory*>.  
  
 **Zwischenverzeichnis**  
 Legt das Verzeichnis fest, in dem Tools wie der Compiler alle Zwischendateien ablegt, die während des Buildprozesses erstellt werden. In der Regel handelt es sich um Ausgabedateien von Tools wie C\/C\+\+\-Compiler, MIDL und Ressourcencompiler.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory*>.  
  
 **Target Name**  
 Gibt den von diesem Projekt generierten Dateinamen an.  
  
 **Zielerweiterung**  
 Gibt die vom Projekt generierte Dateinamenerweiterung an, z. B. .exe oder .dll.  
  
 **Bei der Bereinigung zu löschende Erweiterungen**  
 Durch die Option **Bereinigen** \(Menü **Erstellen**\) werden Dateien aus dem Zwischenverzeichnis gelöscht, in dem die Projektkonfiguration erstellt wurde. Dateien mit Erweiterungen, die durch diese Eigenschaft festgelegt werden, werden gelöscht, sobald **Bereinigen** ausgeführt bzw. ein Rebuild gestartet wurde. Zusätzlich zu Dateien, die über diese Erweiterungen verfügen und sich im Zwischenverzeichnis befinden, werden vom Buildsystem alle bekannten Ausgaben \(einschließlich Zwischenausgaben wie OBJ\-Dateien\) des Builds unabhängig von ihrem Speicherort gelöscht. Sie können auch Platzhalterzeichen angeben.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean*>.  
  
 **Buildprotokolldatei**  
 Ermöglicht es Ihnen, ein vom Standardspeicherort abweichendes Verzeichnis für die Protokolldatei anzugeben, die bei jedem Erstellen eines Projekts generiert wird.  
  
 Sie können Projektmakros verwenden, um den Verzeichnispfad zu ändern. Siehe [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md).  
  
 **Plattformtoolset**  
 Ermöglicht eine Ausrichtung des Projekts auf andere Versionen der Visual C\+\+\-Bibliotheken und des Compilers.[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Projekte können entweder auf das Standardtoolset in [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] \(**v100**\) ausgerichtet werden oder auf das Toolset, das ausführbare Dateien erstellt, die auf Windows XP ausgeführt werden können.  
  
## Projektstandards  
 Die Eigenschaften im Abschnitt “Projektstandards“ stellen änderbare Standardeigenschaften dar. Die Definition für diese Eigenschaften befindet sich in den PROPS\-Dateien in "*Installationsverzeichnis*\\VC\\VCProjectDefaults".  
  
 **Konfigurationstyp**  
 Sie können aus einer Reihe unterschiedlicher Konfigurationstypen auswählen:  
  
-   **Anwendung \(.exe\)** zeigt das Linkertoolset \(C\/C\+\+\-Compiler, MIDL, Ressourcencompiler, Linker, BSCMake, XML\-Webdienst\-Proxy\-Generator, benutzerdefinierte Build\-, Prebuild\-, Prelink\- und Postbuildereignisse\) an.  
  
-   **Dynamische Bibliothek \(.dll\)** zeigt das Linkertoolset an, legt die \/DLL\-Linkeroption fest und fügt CL die \_WINDLL\-Definition hinzu.  
  
-   **Makefile** zeigt das Makefiletoolset \(NMake\) an.  
  
-   **Statische Bibliothek \(.lib\)** zeigt das Bibliothekstoolset an \(von zwei Ausnahmen abgesehen ist dieses Toolset mit dem Linkertoolset identisch: Der Linker wird durch den Bibliothekar ersetzt, und der XML\-Webdienst\-Proxy\-Generator fällt weg\).  
  
-   **Hilfsprogramm** zeigt das Hilfsprogramm\-Toolset \(MIDL, benutzerdefinierte Build\-, Prebuild\-, Postbuildereignisse\) an.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType*>.  
  
 **Verwendung von MFC**  
 Legt fest, ob das MFC\-Projekt statisch oder dynamisch mit der MFC\-DLL verknüpft wird. Für MFC\-fremde Projekte kann **Windows\-Standardbibliotheken verwenden** ausgewählt werden, um eine Verknüpfung mit verschiedenen Win32\-Bibliotheken herzustellen, die bei Verwendung von MFC einbezogen werden.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc*>.  
  
 **Verwendung von ATL**  
 Legt fest, ob das ATL\-Projekt statisch oder dynamisch mit der ATL\-DLL verknüpft wird. Wenn Sie eine andere Option als **ATL wird nicht verwendet** festlegen, wird der Eigenschaftenseite **Befehlszeile** des Compilers eine Definition hinzugefügt.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL*>.  
  
 **Zeichensatz**  
 Legt fest, ob \_UNICODE oder \_MBCS verwendet werden soll. Außerdem kann sich diese Option ggf. auf den Linkereinstiegspunkt auswirken.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet*>.  
  
 **Common Language Runtime\-Unterstützung**  
 Bewirkt, dass die [\/clr](../build/reference/clr-common-language-runtime-compilation.md)\-Compileroption verwendet wird.  
  
 Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions*>.  
  
 **Optimierung des gesamten Programms**  
 Legt die Verwendung der [\/GL](../build/reference/gl-whole-program-optimization.md)\-Compileroption und der [\/LTCG](../build/reference/ltcg-link-time-code-generation.md)\-Linkeroption fest.  
  
 **Unterstützung für Windows Store\-Apps**  
 Gibt an, ob dieses Projekt [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps unterstützt. Weitere Informationen finden Sie unter [\/ZW \(Windows\-Runtime\-Kompilierung\)](../build/reference/zw-windows-runtime-compilation.md) und im Windows Developer Center.  
  
## Siehe auch  
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)