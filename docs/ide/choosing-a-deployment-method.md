---
title: Auswählen einer Bereitstellungsmethode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdf024f75f03b55465ccd15670c47d3c761e56e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338665"
---
# <a name="choosing-a-deployment-method"></a>Auswählen einer Bereitstellungsmethode
Wenn Ihre Visual C++-Anwendung in sich geschlossen ist und mithilfe eines Kopierbefehls bereitgestellt werden kann, wird empfohlen, dass Sie zur Bereitstellung Windows Installer verwenden. Windows Installer unterstützt die Installation, Reparatur und Deinstallation, und es unterstützt das atomische Aktualisieren von Anwendungsdateien, Abhängigkeiten und Registrierungseinträgen.  
  
> [!NOTE]
>  Obwohl die [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)-Bereitstellung für native Visual C++-Anwendungen in Visual Studio möglich ist, sind dafür zusätzliche Schritte erforderlich. Weitere Informationen finden Sie unter [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++-Bibliotheken sind gemeinsam genutzte DLLs  
 Da Visual C++-Bibliotheken durch das Visual Studio-Installationsprogramm im Verzeichnis „%windir%\system32\“ installiert werden, wenn Sie eine Visual C++-Anwendung entwickeln, die von ihnen abhängen, wird sie wie erwartet ausgeführt. Um jedoch die Anwendung auf Computern bereitzustellen, die möglicherweise Visual Studio nicht haben, wird empfohlen, sich zu vergewissern, dass die Bibliotheken auf diesen Computer zusammen mit der Anwendung installiert werden.  
  
## <a name="redistributing-visual-c-libraries"></a>Verteilen von Visual C++-Bibliotheken  
 In Ihren Bereitstellungen können Sie jede Version einer Visual C++-Bibliothek weiter verteilen, die für die Weiterverteilung lizenziert ist. Hierfür gibt es drei Möglichkeiten, sie bereitzustellen:  
  
-   Zentrale Bereitstellung mithilfe von verteilbaren Paketen, wobei Visual C++-Bibliotheken als freigegebene DLLs in %windir%\system32\\ installiert werden. (Die Installation in diesen Ordner erfordert Administratorrechte.) Sie können einen Skript oder ein Setupprogramm erstellen, dass das verteilbare Paket ausführt, bevor Ihre Anwendung auf dem Zielcomputer installiert wird. Verteilbare Pakete sind für die Plattformen x86, x64 und ARM (VCRedist_x86.exe, VCRedist_x64.exe oder VCRedist_arm.exe) verfügbar. Visual Studio umfasst diese Pakete in %Programme (x86)%\Microsoft Visual Studio `version`\VC\Redist\\`locale ID`\\. Sie können sie auch vom [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=132793) herunterladen. (Verwenden Sie das Suchfeld im Download Center, um nach dem „Visual C++ Redistributable Package *Visual Studio-Version und Update*“ zu suchen, das mit Ihrer Anwendung übereinstimmt. Wenn Sie beispielsweise Visual Studio 2015 Update 3 zum Erstellen Ihrer Anwendung verwendet haben, suchen Sie nach „Visual C++ Redistributable Package 2015 Update 3“.) Informationen zum Verwenden verteilbarer Pakete finden Sie unter [Walkthrough: Deploying a Visual C++ Application By Using the Visual C++ Redistributable Package (Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe von Visual C++ Redistributable Package)](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
-   Zentrale Bereitstellung mithilfe von Mergemodulen, von denen jedes eine bestimmte Visual C++-Bibliothek als eine freigegebene DLL in %windir%\system32\\ installiert. (Die Installation in diesen Ordner erfordert Administratorrechte.) Mergemodule werden Teil der MSI-Installationsdatei Ihrer Anwendung. Verteilbare Visual C++-Mergemodule sind in Visual Studio unter \Program Files (x86)\Common Files\Merge Modules\\ enthalten. Weitere Informationen finden Sie unter [Redistributing By Using Merge Modules (Verteilen von Komponenten mithilfe von Mergemodulen)](../ide/redistributing-components-by-using-merge-modules.md).  
  
-   Eine lokale Bereitstellung, bei der Sie bestimmte Visual C++-DLLs aus Ihrer Visual Studio-Installation kopieren, die sich normalerweise unter \Programme (x86)\Microsoft Visual Studio `version`\VC\Redist\\`platform`\\`library`\ befindet, und diese auf Zielcomputer im selben Ordner wie die ausführbaren Anwendungsdateien installieren. Sie können mithilfe dieser Bereitstellungsmethode die Installation durch Benutzer ermöglichen, die über keine Administratorrechte verfügen oder für Anwendungen, die von einer Netzwerkfreigabe aus ausgeführt werden können.  
  
 Wenn eine Bereitstellung verteilbare Mergemodule verwendet und eine Installation von einem Benutzer ausgeführt wird, der nicht über Administratorrechte verfügt, werden die Visual C++-DLLs nicht installiert, und die Anwendung wird nicht ausgeführt. Zudem installieren Anwendungsinstallationsprogramm, die mit Mergemodulen erstellt wurden, die die Installation pro Benutzer ermöglichen, die Bibliotheken an einem freigegebenen Speicherort, was sich auf alle Benutzer des Systems auswirkt. Sie können mithilfe einer lokalen Bereitstellung die erforderlichen Visual C++-DLLs im Verzeichnis einer Anwendung eines bestimmten Benutzers installieren, ohne dass sich dies auf andere Benutzer auswirkt oder Administratorrechte erforderlich sind. Weil dies zu Problemen bei der Wartbarkeit führen kann, wird die lokale Bereitstellung von verteilbaren Visual C++-DLLs nicht empfohlen.  
  
 Die falsche Bereitstellung von Visual C++-Bibliotheken kann Laufzeitfehler während der Ausführung einer Anwendung, die diese Bibliotheken benötigt, verursachen. Wenn das Betriebssystem die Anwendung lädt, verwendet es die in [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?linkid=132792) beschriebene Suchreihenfolge.  
  
## <a name="dynamic-linking-is-better-than-static-linking"></a>Dynamisches Verknüpfen ist besser als statisches Verknüpfen  
 Es wird empfohlen, statisches Verknüpfen zu vermeiden, wenn Sie Visual C++-Bibliotheken verteilen. Obwohl statisches Verknüpfen die Anwendungsleistung nie deutlich verbessert, wird dadurch fast immer die Wartung teurer. Denken Sie beispielsweise an eine Anwendung, die statisch mit einer Bibliothek verknüpft ist, die mit Sicherheitserweiterungen aktualisiert wurde – die Anwendung kann nicht davon profitieren, es sei denn, sie wird erneut kompiliert und erneut bereitgestellt. Statt dessen empfehlen wir, dass Sie Ihre Anwendungen dynamisch mit Bibliotheken verknüpfen, von denen Sie abhängen. Auf diese Weise können die Bibliotheken überall aktualisiert werden, wo sie bereitgestellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)