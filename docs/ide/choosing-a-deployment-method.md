---
title: "Auswählen einer Bereitstellungsmethode | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- redistributing DLLs
- manifests [C++]
- DLLs [C++], redistributing
- side-by-side assemblies [C++]
- dynamic linking [C++]
- application deployment [C++], methods
- deploying applications [C++], methods
- static linking [C++]
- libraries [C++], application deployment issues
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b30bea93163549373759ea8980650717d49bbac
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="choosing-a-deployment-method"></a>Auswählen einer Bereitstellungsmethode
Es sei denn, die Visual C++-Anwendung eigenständig und kann mithilfe eines Kopierbefehls bereitgestellt werden, wird empfohlen, dass Sie Windows Installer für die Bereitstellung verwenden. Windows Installer unterstützt die Installation, Reparatur und Deinstallation, und es unterstützt das atomische Aktualisieren von Anwendungsdateien, Abhängigkeiten und Registrierungseinträgen.  
  
> [!NOTE]
>  Obwohl [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) Bereitstellung für systemeigene Anwendungen Visual C++ in Visual Studio möglich ist, es sind zusätzliche Schritte erforderlich. Weitere Informationen finden Sie unter [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++-Bibliotheken sind gemeinsam genutzte DLLs  
 Da Visual C++-Bibliotheken durch das Visual Studio-Installationsprogramm im Verzeichnis „%windir%\system32\“ installiert werden, wenn Sie eine Visual C++-Anwendung entwickeln, die von ihnen abhängen, wird sie wie erwartet ausgeführt. Um jedoch die Anwendung auf Computern bereitzustellen, die möglicherweise Visual Studio nicht haben, wird empfohlen, sich zu vergewissern, dass die Bibliotheken auf diesen Computer zusammen mit der Anwendung installiert werden.  
  
## <a name="redistributing-visual-c-libraries"></a>Verteilen von Visual C++-Bibliotheken  
 In Ihren Bereitstellungen können Sie jede Version einer Visual C++-Bibliothek weiter verteilen, die für die Weiterverteilung lizenziert ist. Hierfür gibt es drei Möglichkeiten, sie bereitzustellen:  
  
-   Zentrale Bereitstellung mithilfe von weiter verteilbaren Paketen, die Visual C++-Bibliotheken als freigegebene DLLs im %windir%\system32 installiert\\. (Die Installation in diesen Ordner erfordert Administratorrechte.) Sie können einen Skript oder ein Setupprogramm erstellen, dass das verteilbare Paket ausführt, bevor Ihre Anwendung auf dem Zielcomputer installiert wird. Verteilbare Pakete sind für die Plattformen x86, x64 und ARM (VCRedist_x86.exe, VCRedist_x64.exe oder VCRedist_arm.exe) verfügbar. Visual Studio umfasst diese Pakete in % ProgramFiles% (x86) %\Microsoft Visual Studio `version`\VC\Redist\\`locale ID`\\. Sie können auch herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=132793). (Verwenden Sie das Suchfeld im Download Center für die Suche nach der "Visual C++ Redistributable Package *Visual Studio-Version und Update*", die mit die Anwendung übereinstimmt. Deutet an, wenn Sie Visual Studio 2015 Update 3 verwendet, um die Anwendung zu erstellen, suchen Sie nach "Visual C++ Redistributable Package 2015 Update 3".) Informationen zur Verwendung von verteilbares Paket finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe der Visual C++ Redistributable Package](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
-   Zentrale Bereitstellung mithilfe von Mergemodulen, von denen jedes eine bestimmte Visual C++-Bibliothek als eine freigegebene DLL in %windir%\system32 installiert\\. (Die Installation in diesen Ordner erfordert Administratorrechte.) Mergemodule werden Teil der MSI-Installationsdatei Ihrer Anwendung. Visual C++ redistributable-Mergemodule sind in Visual Studio in \Programme (x86) \Common Files\Merge Module enthalten\\. Weitere Informationen finden Sie unter [Neuverteilen von Komponenten von mithilfe von Mergemodulen](../ide/redistributing-components-by-using-merge-modules.md).  
  
-   Lokale Bereitstellung, in dem Sie bestimmte Visual C++-DLLs aus Ihrer Visual Studio-Installation kopieren, in der Regel im \Programme (x86) \Microsoft Visual Studio `version`\VC\Redist\\`platform`\\`library`\—and Installieren Sie diese auf Zielcomputer im gleichen Ordner wie die ausführbare Datei der Anwendung. Sie können mithilfe dieser Bereitstellungsmethode die Installation durch Benutzer ermöglichen, die über keine Administratorrechte verfügen oder für Anwendungen, die von einer Netzwerkfreigabe aus ausgeführt werden können.  
  
 Wenn eine Bereitstellung verteilbare Mergemodule verwendet und eine Installation ausgeführt wird, von einem Benutzer, die nicht über Administratorrechte verfügt, Visual C++-DLLs nicht installiert sind, und die Anwendung wird nicht ausgeführt. Zudem installieren Anwendungsinstallationsprogramm, die mit Mergemodulen erstellt wurden, die die Installation pro Benutzer ermöglichen, die Bibliotheken an einem freigegebenen Speicherort, was sich auf alle Benutzer des Systems auswirkt. Lokale Bereitstellung können Sie die erforderlichen Visual C++-DLLs im Verzeichnis der Anwendung eines bestimmten Benutzers installieren, ohne Auswirkungen auf andere Benutzer oder Administratorrechte erforderlich sind. Da dies Wartungsfreundlichkeit Probleme erstellen kann, empfehlen wir nicht lokale Bereitstellung von verteilbaren Visual C++-DLLs.  
  
 Die falsche Bereitstellung von Visual C++-Bibliotheken kann Laufzeitfehler während der Ausführung einer Anwendung, die diese Bibliotheken benötigt, verursachen. Wenn das Betriebssystem die Anwendung geladen wird, verwendet es die in beschriebenen Suchreihenfolge [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?linkid=132792)  
  
## <a name="dynamic-linking-is-better-than-static-linking"></a>Dynamisches Verknüpfen ist besser als statisches Verknüpfen  
 Es wird empfohlen, dass beim Verteilen von Visual C++-Bibliotheken statisches verknüpfen zu vermeiden. Obwohl statisches Verknüpfen die Anwendungsleistung nie deutlich verbessert, wird dadurch fast immer die Wartung teurer. Denken Sie beispielsweise an eine Anwendung, die statisch mit einer Bibliothek verknüpft ist, die mit Sicherheitserweiterungen aktualisiert wurde – die Anwendung kann nicht davon profitieren, es sei denn, sie wird erneut kompiliert und erneut bereitgestellt. Statt dessen empfehlen wir, dass Sie Ihre Anwendungen dynamisch mit Bibliotheken verknüpfen, von denen Sie abhängen. Auf diese Weise können die Bibliotheken überall aktualisiert werden, wo sie bereitgestellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)