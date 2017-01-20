---
title: "Verteilen von Visual&#160;C++-Dateien"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsbereitstellung [C++], Dateiverteilung"
  - "Bereitstellen von Anwendungen [C++], Dateiverteilung"
  - "Dateiverteilung [C++]"
  - "Verteilen von Anwendungen [C++]"
  - "Verteilen von Anwendungen [C++], Informationen über das Verteilen von Anwendungen"
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
caps.latest.revision: 50
caps.handback.revision: "48"
ms.author: "corob"
manager: "ghogen"
---
# Verteilen von Visual&#160;C++-Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine Anwendung bereitstellen, müssen Sie auch die Dateien bereitstellen, die zu ihrer Unterstützung erforderlich sind.  Wenn eine dieser Dateien von Microsoft zur Verfügung gestellt wird, überprüfen Sie, ob Sie sie weiterverteilen dürfen.  Um die Microsoft\-Softwarelizenzbedingungen anzuzeigen, öffnen Sie die Datei "License.htm" in dem Verzeichnis, in dem Visual Studio installiert ist, oder auf den Visual Studio\-Installationsmedien.  Informationen zum Anzeigen der „REDIST\-Liste“, auf die im Abschnitt „Verteilbarer Code“ der Microsoft\-Softwarelizenzbedingungen für bestimmte Editionen von Visual Studio verwiesen wird, finden Sie unter [Verteilbarer Code für Microsoft Visual Studio 2013 und Microsoft Visual Studio 2013 SDK \(enthält Dienstprogramme und BuildServer\-Dateien\)](http://go.microsoft.com/fwlink/p/?LinkId=313603) auf der Microsoft\-Website.  Weitere Informationen zu neu verteilbaren Dateien finden Sie unter [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md) und [Bereitstellungsbeispiele](../ide/deployment-examples.md).  
  
 Zum Bereitstellen von verteilbaren Visual C\+\+\-Dateien können Sie die Visual C\+\+ Redistributable Packages \(VCRedist\_x86.exe, VCRedist\_x64.exe oder VCRedist\_arm.exe\) verwenden, die in Visual Studio enthalten sind.  Diese Dateien befinden sich im Visual Studio\-Installationsverzeichnis unter Programme \[\(x 86\)\]\\Microsoft Visual Studio*Version*\\VC\\redist\\*Gebietsschema*\\.  Eine weitere Option sind verteilbare Mergemodule \(MSM\-Dateien\), die Sie unter Programme \[\(x 86\)\]\\Gemeinsame Dateien\\Merge Modules\\ finden.  Es ist auch möglich, verteilbare Visual C\+\+\-DLLs direkt in den *lokalen Anwendungsordner* zu installieren. Dabei handelt es sich um den Ordner, der die ausführbare Anwendungsdatei enthält.  Aus Wartungsgründen empfehlen wir, diesen Speicherort nicht für die Installation zu verwenden.  
  
 Die weiterverteilbaren Visual C\+\+\-Pakete installieren und registrieren alle Visual C\+\+\-Bibliotheken.  Wenn Sie eines von ihnen verwenden, müssen Sie es so konfigurieren, dass es auf dem Zielsystem als erforderliche Komponente für die Installation Ihrer Anwendung ausgeführt wird.  Es wird empfohlen, dass Sie diese Pakete für die Bereitstellungen verwenden, da Sie die automatische Aktualisierung von Visual C\+\+\-Bibliotheken ermöglichen.  Ein Beispiel zum Verwenden dieser Pakete finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C\+\+\-Anwendung mithilfe von Visual C\+\+ Redistributable Package](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
 Jedes Visual C\+\+ Redistributable Package überprüft das Vorhandensein einer aktuelleren Version auf dem Computer.  Wenn eine neuere Version gefunden wird, wird das Paket nicht installiert.  Ab Visual Studio 2015 zeigen verteilbare Pakete eine Fehlermeldung an, die darauf hinweist, dass ein Fehler beim Setup aufgetreten ist.  Wenn ein Paket mit dem Flag **\/quiet** ausgeführt wird, wird keine Fehlermeldung angezeigt.  In beiden Fällen wird ein Fehler im Microsoft Installer protokolliert und ein Fehlerergebnis wird an den Aufrufenden zurückgegeben.  Mit Paketen ab Visual Studio 2015 können Sie einen Registrierungswert überprüfen, um herauszufinden, ob eine neuere Version installiert ist.  Die derzeit installierte Version wird als REG\_SZ\-Wert im Versionsschlüssel HKEY\_LOCAL\_MACHINE\\SOFTWARE\[\\Wow6432Node\]\\Microsoft\\DevDiv\\vc\\Servicing\\14.0\\RuntimeMinimum gespeichert.  Sie müssen das verteilbare Paket nicht installieren, wenn die derzeit installierte Version aktueller ist.  
  
 Wenn Sie ein Mergemodul verwenden, das eine Visual C\+\+\-DLL enthält, müssen Sie es in das Windows Installer\-Paket einschließen \(oder in ein ähnliches Installationspaket\), mit dem Sie die Anwendung bereitstellen.  Weitere Informationen finden Sie unter [Verteilen mit Mergemodulen](../ide/redistributing-components-by-using-merge-modules.md).  Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C\+\+\-Anwendung mithilfe eines Setup\-Projekts](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md). Dort wird außerdem gezeigt, wie Sie InstallShield Limited Edition verwenden, um ein Installationspaket zu erstellen.  
  
## Potenzielle Laufzeitfehler  
 Wenn eine Visual C\+\+\-Bibliotheks\-DLL nicht erreichbar ist und sie von Windows für Ihre Anwendung nicht geladen werden kann, wird die folgende Meldung angezeigt: **Diese Anwendung konnte nicht gestartet werden, da MSVCR\<version number\>.dll nicht gefunden wurde. Neuinstallation der Anwendung könnte das Problem beheben.**  
  
 Um diese Art von Fehler zu beheben, müssen Sie sicherstellen, dass die Anwendung richtig erstellt wird und dass die Visual C\+\+\-Bibliotheken auf dem Zielsystem ordnungsgemäß bereitgestellt werden.  Weitere Informationen finden Sie unter [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Verteilen mit Mergemodulen](../ide/redistributing-components-by-using-merge-modules.md)|Beschreibt die Verwendung von weiterverteilbaren Mergemodulen in [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] zur Installation der Visual C\+\+\-Laufzeitbibliotheken als freigegebene DLLs im Ordner „%windir%\\system32\\“.|  
|[Neuverteilen von Visual C\+\+ ActiveX\-Steuerelementen](../ide/redistributing-visual-cpp-activex-controls.md)|Beschreibt, wie eine Anwendung, die ActiveX\-Steuerelemente verwendet, verteilt wird.|  
|[Neuverteilen von Datenbankunterstützungsdateien](../ide/redistributing-database-support-files.md)|Erläutert, wie Unterstützungsdateien für Datenzugriffsobjekte \(DAO\) und die Datenbanktechnologien im Microsoft Data Access SDK weiterverteilt werden.|  
|[Verteilen der MFC\-Bibliothek](../ide/redistributing-the-mfc-library.md)|Beschreibt, wie eine Anwendung, die MFC verwendet, verteilt wird.|  
|[Verteilen von ATL\-Anwendungen](../ide/redistributing-an-atl-application.md)|Beschreibt, wie eine Anwendung, die ATL verwendet, neu verteilt wird.  Ab Visual Studio 2012 ist keine verteilbare Bibliothek für ATL erforderlich.|  
|[Bereitstellungsbeispiele](../ide/deployment-examples.md)|Links zu Beispielen, die veranschaulichen, wie Visual C\+\+\-Anwendungen bereitgestellt werden.|  
|[Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)|Bietet eine Einführung in Visual C\+\+\-Bereitstellungskonzepte und \-technologien.|