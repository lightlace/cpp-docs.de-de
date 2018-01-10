---
title: Neuverteilen von Visual C++-Dateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
caps.latest.revision: "50"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 106123557c4efab5ccddf9f1292570d36b0f8313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-visual-c-files"></a>Verteilen von Visual C++-Dateien
Wenn Sie eine Anwendung bereitstellen, müssen Sie auch die Dateien bereitstellen, die zu ihrer Unterstützung erforderlich sind. Wenn eine dieser Dateien von Microsoft zur Verfügung gestellt wird, überprüfen Sie, ob Sie sie weiterverteilen dürfen. Um die Visual Studio-Lizenzbedingungen zu überprüfen, finden Sie unter den Link in das Dialogfeld zu Microsoft Visual Studio in der IDE Lizenz sowie den download der [Microsoft Software License Terms](http://go.microsoft.com/fwlink/p/?LinkId=831114) Datei. Die "REDIST-Liste", die im Abschnitt "Verteilbarer Code" der Microsoft Software-Lizenzbedingungen für bestimmte Editionen von Visual Studio verwiesen wird, finden Sie unter [verteilbarer Code für Microsoft Visual Studio 2017 und Microsoft Visual Studio 2017 SDK (enthält Dienstprogramme und BuildServer-Dateien)](http://go.microsoft.com/fwlink/p/?LinkId=823098), oder für Visual Studio 2015 finden Sie unter [verteilbarer Code für Microsoft Visual Studio 2015 und Microsoft Visual Studio 2015 SDK](http://go.microsoft.com/fwlink/p/?LinkId=523763). Weitere Informationen zu neu verteilbaren Dateien finden Sie unter [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md) und [Bereitstellungsbeispiele](../ide/deployment-examples.md).  
  
 Verteilbare Visual C++-Dateien bereitstellen möchten, können Sie die Visual C++ Redistributable Packages (VCRedist\_x86.exe VCRedist\_x64.exe oder VCRedist\_arm.exe) in Visual Studio enthalten sind. In Visual Studio 2017 diese Dateien befinden sich in den Programmdateien [(x86)]\\Microsoft Visual Studio\\2017\\_Edition_\\VC\\Redist\\ MSVC\\_Lib-Version_ Ordner, in dem _Edition_ ist die Visual Studio-Edition installiert haben, und _Lib-Version_ ist die Version der Bibliotheken zu verteilen. In Visual Studio 2015 wird diese Dateien finden Sie unter Ihrem Visual Studio-Installationsverzeichnis in Programme [(x 86) \Microsoft Visual Studio *Version*\VC\redist\\*Gebietsschema* \\. Eine andere Möglichkeit ist die Verwendung von verteilbare Mergemodule (MSM-Dateien), die sich in Visual Studio 2017 der Programmdateien [(x 86)]\\Microsoft Visual Studio\\2017\\_Edition_ \\ VC\\Redist\\MSVC\\_Lib-Version_\\MergeModules\\ Ordner. In Visual Studio 2015 diese finden Sie unter Programme [(x 86)] \Common Files\Merge Module\\. Es ist auch möglich, verteilbare Visual C++-DLLs in direkt Installieren der *lokalen Anwendungsordner*, also in den Ordner, der die ausführbare Anwendungsdatei enthält. Aus Wartungsgründen empfehlen wir, diesen Speicherort nicht für die Installation zu verwenden.  
  
 Die weiterverteilbaren Visual C++-Pakete installieren und registrieren alle Visual C++-Bibliotheken. Wenn Sie eines von ihnen verwenden, müssen Sie es so konfigurieren, dass es auf dem Zielsystem als erforderliche Komponente für die Installation Ihrer Anwendung ausgeführt wird. Es wird empfohlen, dass Sie diese Pakete für die Bereitstellungen verwenden, da Sie die automatische Aktualisierung von Visual C++-Bibliotheken ermöglichen. Ein Beispiel zur Verwendung dieser Pakete finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe der Visual C++ Redistributable Package](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
 Jedes Visual C++ Redistributable Package überprüft das Vorhandensein einer aktuelleren Version auf dem Computer. Wenn eine neuere Version gefunden wird, wird das Paket nicht installiert. Ab Visual Studio 2015 zeigen verteilbare Pakete eine Fehlermeldung an, die darauf hinweist, dass ein Fehler beim Setup aufgetreten ist. Wenn ein Paket, mithilfe ausgeführt wird der **/quiet** Flag keine Fehlermeldung wird angezeigt. In beiden Fällen wird ein Fehler im Microsoft Installer protokolliert und ein Fehlerergebnis wird an den Aufrufenden zurückgegeben. Ab Visual Studio 2015-Pakete, können Sie diesen Fehler vermeiden, überprüfen Sie die Registrierung, um festzustellen, ob eine neuere Version installiert ist. Die derzeit installierte Version befindet sich in der HKEY_LOCAL_MACHINE\SOFTWARE [\Wow6432Node] \Microsoft\VisualStudio\\_Vs-Version_\VC\Runtimes\\{X86 | X64 | ARM}-Schlüssel, auf dem _Vs-Version_ ist die Versionsnummer für Visual Studio (14.0 für Visual Studio 2015 und Visual Studio 2017, da die aktualisierte 2017 redistributable mit der Version 2015 binärkompatibel ist), und, in dem der Schlüssel ist ARM, x 86- oder X64 je nach den installierten Vcredist Versionen für die Plattform. (Sie müssen nicht unter dem Unterschlüssel Wow6432Node zu überprüfen, es sei denn, Sie RegEdit verwenden werden, um die Version des installierten X86 anzuzeigen Paket auf ein X64 Plattform.) Die Versionsnummer wird gespeichert, in den REG_SZ-Zeichenfolgenwert **Version** und auch in der Menge der **wichtigen**, **kleinere**, **Bld**, und **Rbld** REG_DWORD-Werte. Zur Vermeidung eines Fehlers während der Installation müssen Sie die Installation des weitervertreibbaren Pakets überspringen, wenn die derzeit installierte Version aktuell ist.  
  
 Wenn Sie ein Mergemodul verwenden, das eine Visual C++-DLL enthält, müssen Sie es in das Windows Installer-Paket einschließen (oder in ein ähnliches Installationspaket), mit dem Sie die Anwendung bereitstellen. Weitere Informationen finden Sie unter [Neuverteilen von Komponenten von mithilfe von Mergemodulen](../ide/redistributing-components-by-using-merge-modules.md). Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md), die zeigt außerdem das InstallShield Limited Edition verwenden, um ein Installationspaket zu erstellen.  
  
## <a name="potential-run-time-errors"></a>Potenzielle Laufzeitfehler  
 Wenn eine Visual C++-Bibliotheks-DLL nicht erreichbar ist ist und Windows nicht für die Anwendung geladen, kann die folgende Meldung angezeigt werden: **dieser Anwendung konnte nicht gestartet werden, da MSVCR\<Versionsnummer > DLL wurde nicht gefunden. Neuinstallation der Anwendung könnte das Problem beheben.**  
  
 Um diese Art von Fehler zu beheben, müssen Sie sicherstellen, dass die Anwendung richtig erstellt wird und dass die Visual C++-Bibliotheken auf dem Zielsystem ordnungsgemäß bereitgestellt werden. Weitere Informationen finden Sie unter [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Verteilen mit Mergemodulen](../ide/redistributing-components-by-using-merge-modules.md)|Beschreibt, wie verteilbare Visual C++-Mergemodule zum Installieren der Visual C++-Laufzeitbibliotheken als freigegebene DLLs im Ordner "%windir%\system32\".|  
|[Neuverteilen von Visual C++ ActiveX-Steuerelementen](../ide/redistributing-visual-cpp-activex-controls.md)|Beschreibt, wie eine Anwendung, die ActiveX-Steuerelemente verwendet, verteilt wird.|  
|[Neuverteilen von Datenbankunterstützungsdateien](../ide/redistributing-database-support-files.md)|Erläutert, wie Unterstützungsdateien für Datenzugriffsobjekte (DAO) und die Datenbanktechnologien im Microsoft Data Access SDK weiterverteilt werden.|  
|[Neuverteilen der MFC-Bibliothek](../ide/redistributing-the-mfc-library.md)|Beschreibt, wie eine Anwendung, die MFC verwendet, verteilt wird.|  
|[Neuverteilen von ATL-Anwendungen](../ide/redistributing-an-atl-application.md)|Beschreibt, wie eine Anwendung, die ATL verwendet, neu verteilt wird. Ab Visual Studio 2012 ist keine verteilbare Bibliothek für ATL erforderlich.|  
|[Bereitstellungsbeispiele](../ide/deployment-examples.md)|Links zu Beispielen, die veranschaulichen, wie Visual C++-Anwendungen bereitgestellt werden.|  
|[Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)|Bietet eine Einführung in Visual C++-Bereitstellungskonzepte und -technologien.|