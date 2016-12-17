---
title: "Ausw&#228;hlen einer Bereitstellungsmethode"
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
  - "Anwendungsbereitstellung [C++], Methoden"
  - "Bereitstellen von Anwendungen [C++], Methoden"
  - "DLLs [C++], Verteilen"
  - "Dynamisches Verknüpfen [C++]"
  - "Bibliotheken [C++], Anwendungsbereitstellungsprobleme"
  - "Manifeste [C++]"
  - "Verteilen von DLLs"
  - "Parallele Assemblys [C++]"
  - "Statisches Verknüpfen [C++]"
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
caps.latest.revision: 35
caps.handback.revision: "35"
ms.author: "corob"
manager: "ghogen"
---
# Ausw&#228;hlen einer Bereitstellungsmethode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es sei denn, Ihre [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Anwendung ist in sich geschlossen und kann mithilfe eines Kopierbefehls bereitgestellt werden, wird empfohlen, dass Sie zur Bereitstellung Windows Installer verwenden.  Windows Installer unterstützt die Installation, Reparatur und Deinstallation, und es unterstützt das atomische Aktualisieren von Anwendungsdateien, Abhängigkeiten und Registrierungseinträgen.  
  
> [!NOTE]
>  Obwohl die [ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md)\-Bereitstellung für systemeigene [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Anwendungen in Visual Studio möglich ist, sind dafür zusätzliche Schritte erforderlich.  Weitere Informationen finden Sie unter [ClickOnce\-Bereitstellung für Visual C\+\+\-Anwendungen](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
## Visual C\+\+\-Bibliotheken sind gemeinsam genutzte DLLs  
 Da Visual C\+\+\-Bibliotheken durch das Visual Studio\-Installationsprogramm im Verzeichnis „%windir%\\system32\\“ installiert werden, wenn Sie eine Visual C\+\+\-Anwendung entwickeln, die von ihnen abhängen, wird sie wie erwartet ausgeführt.  Um jedoch die Anwendung auf Computern bereitzustellen, die möglicherweise Visual Studio nicht haben, wird empfohlen, sich zu vergewissern, dass die Bibliotheken auf diesen Computer zusammen mit der Anwendung installiert werden.  
  
## Verteilen von Visual C\+\+\-Bibliotheken  
 In Ihren Bereitstellungen können Sie jede Version einer Visual C\+\+\-Bibliothek weiter verteilen, die für die Weiterverteilung lizenziert ist.  Hierfür gibt es drei Möglichkeiten, sie bereitzustellen:  
  
-   Zentrale Bereitstellung mithilfe von weiter verteilbaren Paketen, wobei Visual C\+\+\-Bibliotheken als freigegebene DLLs in „%windir%\\system32\\“ installiert werden. \(Die Installation in diesen Ordner erfordert Administratorrechte.\) Sie können einen Skript oder ein Setupprogramm erstellen, dass das verteilbare Paket ausführt, bevor Ihre Anwendung auf dem Zielcomputer installiert wird.  Verteilbare Pakete sind für die Plattformen x86, x64 und ARM \(VCRedist\_x86.exe, VCRedist\_x64.exe oder VCRedist\_arm.exe\) verfügbar.  Visual Studio umfasst diese Pakete in „%ProgramFiles\(x86\)%\\Microsoft Visual Studio `version`\\VC\\Redist\\`locale ID`\\“.  Sie können sie auch vom [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=132793) herunterladen. \(Suchen Sie im Download Center das „[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] Weiter verteilbare Paket *Visual Studio version and update*“, dass Ihrer Anwendung entspricht.  Wenn Sie beispielsweise Visual Studio 2012 Update 4 zum Erstellen Ihrer Anwendung verwendet haben, suchen Sie nach „Visual C\+\+ Redistributable Package 2012 update 4“.\) Weitere Informationen zur Verwendung von verteilbaren Paketen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C\+\+\-Anwendung mithilfe von Visual C\+\+ Redistributable Package](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
-   Zentrale Bereitstellung mithilfe von Mergemodulen, von denen jedes eine bestimmte Visual C\+\+\-Bibliothek als eine freigegebene DLL in „%windir%\\system32\\“ installiert. \(Die Installation in diesen Ordner erfordert Administratorrechte.\) Mergemodule werden Teil der MSI\-Installationsdatei Ihrer Anwendung.  Verteilbare Visual C\+\+\-Mergemodule sind in Visual Studio in „\\Programme \(x86\)\\Gemeinsame Dateien\\Mergemodule\\“ enthalten.  Weitere Informationen finden Sie unter [Verteilen mit Mergemodulen](../ide/redistributing-components-by-using-merge-modules.md).  
  
-   Eine lokale Bereitstellung, bei der Sie bestimmte Visual C\+\+\-DLLs aus Ihrer Visual Studio\-Installation kopieren, die sich normalerweise in „\\Programme \(x86\)\\Microsoft Visual Studio `version`\\VC\\Redist\\`platform`\\`library`\\“ befindet, und diese auf Zielcomputer im selben Ordner installieren, wie die ausführbaren Anwendungsdateien.  Sie können mithilfe dieser Bereitstellungsmethode die Installation durch Benutzer ermöglichen, die über keine Administratorrechte verfügen oder für Anwendungen, die von einer Netzwerkfreigabe aus ausgeführt werden können.  
  
 Wenn eine Bereitstellung verteilbare Mergemodule verwendet und eine Installation von einem Benutzer ausgeführt wird, der nicht über Administratorrechte verfügt, werden die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-DLLs nicht installiert, und die Anwendung wird nicht ausgeführt.  Zudem installieren Anwendungsinstallationsprogramm, die mit Mergemodulen erstellt wurden, die die Installation pro Benutzer ermöglichen, die Bibliotheken an einem freigegebenen Speicherort, was sich auf alle Benutzer des Systems auswirkt.  Sie können mithilfe einer lokalen Bereitstellung die erforderlichen [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-DLLs im Verzeichnis einer Anwendung eines bestimmten Benutzers installieren, ohne dass sich dies auf andere Benutzer auswirkt oder Administratorrechte erforderlich sind.  Weil dies zu Problemen bei der Wartbarkeit führen kann, wird die lokale Bereitstellung von verteilbaren [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-DLLs nicht empfohlen.  
  
 Die falsche Bereitstellung von Visual C\+\+\-Bibliotheken kann Laufzeitfehler während der Ausführung einer Anwendung, die diese Bibliotheken benötigt, verursachen.  Wenn das Betriebssystem die Anwendung lädt, verwendet es die in [LoadLibraryEx](http://go.microsoft.com/fwlink/?LinkId=132792) beschriebene Suchreihenfolge  
  
## Dynamisches Verknüpfen ist besser als statisches Verknüpfen  
 Es wird empfohlen, statisches Verknüpfen zu vermeiden, wenn Sie [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken weiter verteilen.  Obwohl statisches Verknüpfen die Anwendungsleistung nie deutlich verbessert, wird dadurch fast immer die Wartung teurer.  Denken Sie beispielsweise an eine Anwendung, die statisch mit einer Bibliothek verknüpft ist, die mit Sicherheitserweiterungen aktualisiert wurde – die Anwendung kann nicht davon profitieren, es sei denn, sie wird erneut kompiliert und erneut bereitgestellt.  Statt dessen empfehlen wir, dass Sie Ihre Anwendungen dynamisch mit Bibliotheken verknüpfen, von denen Sie abhängen. Auf diese Weise können die Bibliotheken überall aktualisiert werden, wo sie bereitgestellt werden.  
  
## Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Not in Build: Choosing a Deployment Strategy](assetId:///ecd632d8-063c-4028-b785-81bba045107b)   
 [Windows Installer Deployment Overview](assetId:///3ce4610a-b54f-404e-b650-42f4a55dfc3b)   
 [ClickOnce Security and Deployment](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)