---
title: "Bereitstellen von systemeigenen Desktopanwendungen (Visual C++)"
ms.custom: na
ms.date: "12/15/2016"
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
  - "Bereitstellen von Anwendungen [C++]"
  - "Anwendungsbereitstellung [C++]"
  - "Visual C++, Anwendungsbereitstellung"
  - "Anwendungsbereitstellung [C++], Informationen zur Anwendungsbereitstellung"
  - "Bereitstellen von Anwendungen [C++], Informationen zum Bereitstellen von Anwendungen"
  - "Verteilen von Anwendungen [C++]"
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
caps.latest.revision: 28
caps.handback.revision: "28"
ms.author: "mblome"
manager: "ghogen"
---
# Bereitstellen von systemeigenen Desktopanwendungen (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Verteilung einer fertigen Anwendung oder Komponente zur Installation auf anderen Computern wird als Bereitstellung bezeichnet. Die Bereitstellungsplanung beginnt, wenn eine Anwendung auf dem Computer eines Entwicklers erstellt wird. Die Bereitstellung endet, wenn die Anwendung installiert wurde und auf dem Computer eines Benutzers ausgeführt werden kann.  
  
 Visual Studio bietet verschiedene Technologien für die Bereitstellung von Windows\-Anwendungen. Dazu zählen die [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)]\-Bereitstellung und die Windows Installer\-Bereitstellung.  
  
-   Mithilfe von [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] können C\+\+\-Anwendungen bereitgestellt werden, die auf die Common Language Runtime \(CLR\) ausgerichtet sind – gemischte, reine und überprüfbare Assemblys. Obwohl Sie mit Windows Installer eine verwaltete Anwendung bereitstellen können, wird empfohlen, dass Sie [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] verwenden, da es .NET Framework\-Sicherheitsfeatures verwendet, z. B. das Signieren von Manifesten.[!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] unterstützt keine Bereitstellung von systemeigenen C\+\+\-Anwendungen. Weitere Informationen finden Sie unter [ClickOnce\-Bereitstellung für Visual C\+\+\-Anwendungen](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
-   Mithilfe der Windows Installer\-Technologie können systemeigene C\+\+\-Anwendungen oder C\+\+\-Anwendungen bereitgestellt werden, die auf die Common Language Runtime \(CLR\) ausgerichtet sind.  
  
 In den Artikeln dieses Abschnitts der Dokumentation wird erläutert, wie sichergestellt werden kann, dass eine systemeigene Visual C\+\+\-Anwendung auf jedem Computer ausgeführt werden kann, der eine unterstützte Zielplattform bietet. Zudem werden die in ein Installationspaket einzubeziehenden Dateien und die empfohlenen Methoden zum Verteilen von Komponenten beschrieben, von denen die Anwendung abhängt.  
  
## In diesem Abschnitt  
 [Bereitstellung in Visual C\+\+](../ide/deployment-in-visual-cpp.md)  
  
 [Bereitstellungskonzepte](../ide/deployment-concepts.md)  
  
 [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)  
  
 [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md)  
  
 [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md)  
  
 [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md)  
  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)  
  
 [Neuverteilen von Webclientanwendungen](../ide/redistributing-web-client-applications.md)  
  
 [ClickOnce\-Bereitstellung für Visual C\+\+\-Anwendungen](../ide/clickonce-deployment-for-visual-cpp-applications.md)  
  
 [Ausführen einer C\+\+ \/clr\-Anwendung unter einer früheren Laufzeitversion](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)  
  
## Verwandte Abschnitte  
 [Erstellen von isolierten Anwendungen und parallelen Assemblys \(C\/C\+\+\)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
 [Bereitstellung](../Topic/Deploying%20the%20.NET%20Framework%20and%20Applications.md)  
  
 [Problembehandlung](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)