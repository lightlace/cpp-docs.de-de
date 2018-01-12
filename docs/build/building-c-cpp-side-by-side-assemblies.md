---
title: Erstellen von C/C++-Seite-an-Seite-Assemblys | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c54f0e3b8bceff3daa92ecb3e0ee46d7fbeb666
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-side-by-side-assemblies"></a>Erstellen von parallelen C/C++-Assemblys
Ein [Side-by-Side Assembly](http://msdn.microsoft.com/library/windows/desktop/ff951640) ist eine Sammlung von Ressourcen – eine Gruppe von DLLs, Windows-Klassen, COM-Servern, Typbibliotheken oder Schnittstellen – eine Anwendung zur Verwendung zur Laufzeit zur Verfügung. Der wichtigste Vorteil von erneutes Packen DLLs in Assemblys ist, dass mehrere Versionen der Assemblys von Anwendungen gleichzeitig verwendet werden können, und es möglich, Service, die zurzeit installierte Assemblys im Falle einer Update-Version ist.  
  
 Eine Visual C++-Anwendung kann eine oder mehrere DLLs in verschiedenen Teilen der Anwendung verwenden. Zur Laufzeit werden die DLLs in den main-Prozess geladen, und der erforderliche Code ausgeführt wird. Die Anwendung basiert auf dem Betriebssystem um die angeforderten DLLs suchen, zu erfahren, habe andere abhängige DLLs geladen werden, und Laden sie dann zusammen mit der angeforderten DLL. Auf Windows-Betriebssystemen sucht vor Windows XP, Windows Server 2003 und Windows Vista vom Ladeprogramm des Betriebssystems abhängigen DLLs im lokalen Ordner der Anwendung oder einen anderen Ordner auf dem Systempfad angegeben. Unter Windows XP, Windows Server 2003 und Windows Vista, kann vom Ladeprogramm des Betriebssystems auch nach abhängigen DLLs mit suchen eine [manifest](http://msdn.microsoft.com/library/windows/desktop/aa375365) Datei und suchen Sie nach Seite-an-Seite-Assemblys, die diese DLLs enthalten.  
  
 Standardmäßig, wenn eine DLL mit Visual Studio erstellt werden kann ein [Anwendungsmanifest](http://msdn.microsoft.com/library/windows/desktop/aa374191) eingebettet als RT_MANIFEST-Ressource mit der ID gleich 2. So wie für eine ausführbare Datei beschreibt dieses Manifest Abhängigkeiten dieser DLL von anderen Assemblys. Dies setzt voraus, dass die DLL nicht Teil einer Seite-an-Seite-Assembly ist und Anwendungen, die diese DLL abhängig sind nicht verwenden ein Anwendungsmanifest zu laden, sondern stattdessen abhängig vom Ladeprogramm Betriebssystems diese DLL auf dem Systempfad gefunden.  
  
> [!NOTE]
>  Es ist wichtig für eine DLL, die ein Anwendungsmanifest verwendet wird, um das Manifest als Ressource mit der ID gleich 2 eingebettet wurden. Wenn die DLL zur Laufzeit dynamisch geladen wird (z. B. die [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175) Funktion), vom Ladeprogramm des Betriebssystems lädt abhängige Assemblys, die in der DLL-Manifest angegeben. Ein externes Anwendungsmanifest für DLLs nicht aktiviert ist, während eine `LoadLibrary` aufrufen. Wenn das Manifest nicht eingebettet werden, das Ladeprogramm möglicherweise falsche Versionen der Assemblys laden oder Fehler beim abhängigen Assemblys finden.  
  
 Eine oder mehrere bezogene DLLs können neu gepackt werden, in eine Seite-an-Seite-Assembly mit einem entsprechenden [Assemblymanifest](http://msdn.microsoft.com/library/windows/desktop/aa374219), das beschreibt, welche Dateien der Assembly als auch die Abhängigkeit der Assembly auf der anderen Seite-an-Seite bilden Assemblys.  
  
> [!NOTE]
>  Wenn eine Assembly eine DLL enthält, wird empfohlen, das Manifest als Ressource mit ID gleich 1 in dieser DLL einbetten, und weisen der privaten Assembly denselben Namen wie die DLL. Z. B., wenn der Name der DLL mylibrary.dll ist, der Wert des Namensattributs verwendet die \<AssemblyIdentity >-Element des Manifests möglicherweise Mylibrary. In einigen Fällen, wenn eine Bibliothek mit eine anderen Erweiterung als DLL aufweist (z. B. für ein MFC-ActiveX-Steuerelemente-Projekt erstellt eine ".ocx"-Bibliothek) kann ein externe Assembly-Manifest erstellt werden. In diesem Fall muss der Name der Assembly und das Manifest der Name der DLL (z. B. MyAssembly, MyAssembly.manifest und mylibrary.ocx) abweichen. Es wird jedoch immer noch empfohlen, benennen Sie diese Bibliotheken aus, um die Erweiterung.dll zu verleihen und das Manifest als Ressource zur Reduzierung der Wartungskosten künftige dieser Assembly einzubetten. Weitere Informationen darüber, wie das Betriebssystem nach privaten Assemblys sucht, finden Sie unter [Assemblysuchsequenz](http://msdn.microsoft.com/library/windows/desktop/aa374224).  
  
 Diese Änderung kann die Bereitstellung der entsprechenden DLLs als eine [private Assembly](http://msdn.microsoft.com/library/windows/desktop/aa370850) in einen lokalen Ordner der Anwendung oder als eine [freigegebene Assembly](http://msdn.microsoft.com/library/windows/desktop/aa371839) im WinSxS Assemblycache. Es müssen verschiedene Schritte befolgt werden, um richtige Laufzeitverhalten dieser neuen Assembly zu erzielen. Diese werden beschrieben [Richtlinien zum Erstellen von Seite-an-Seite-Assemblys](http://msdn.microsoft.com/library/windows/desktop/aa375155). Nachdem eine Assembly richtig erstellt wurde kann sie bereitgestellt als entweder freigegeben oder privat Assembly zusammen mit einer Anwendung, die von ihm abhängig ist. Bei der Installation von Seite-an-Seite-Assemblys als freigegebene Assembly können Sie entweder die Richtlinien folgen in [Installieren von Win32-Assemblys für die Seite-an-Seite-Freigabe unter Windows XP](http://msdn.microsoft.com/library/windows/desktop/aa369532) oder [Mergemodule](http://msdn.microsoft.com/library/windows/desktop/aa369820). Bei der Installation von Seite-an-Seite-Assemblys als private Assembly können Sie einfach kopieren die entsprechende DLL, Ressourcen und das Assemblymanifest im Rahmen des Installationsvorgangs auf den lokalen Ordner der Anwendung auf dem Zielcomputer sicherstellen, dass diese Assembly werden können durch das Ladeprogramm zur Laufzeit gefunden (siehe [Assemblysuchsequenz](http://msdn.microsoft.com/library/windows/desktop/aa374224)). Eine andere Möglichkeit ist die Verwendung [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688) und befolgen Sie die Richtlinien unter [Installieren von Win32-Assemblys für die Private Nutzung einer Anwendung unter Windows XP](http://msdn.microsoft.com/library/windows/desktop/aa369534).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiele für die Bereitstellung](../ide/deployment-examples.md)   
 [Erstellen von C/C++-Anwendungen isolierten](../build/building-c-cpp-isolated-applications.md)   
 [Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)