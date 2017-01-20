---
title: "Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Isolierte Anwendungen [C++]"
  - "WinSxS [C++]"
  - "Systemeigener Assemblycache [C++]"
  - "Builds [C++], isolierte Anwendungen"
  - "Parallele Anwendungen [C++]"
  - "Builds [C++], parallele Assemblys"
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
caps.latest.revision: 20
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ unterstützt ein Bereitstellungsmodell für Windows\-Clientanwendungen, das auf der Idee von [isolierten Anwendungen](http://msdn.microsoft.com/library/aa375190) und [parallelen Assemblys](_win32_side_by_side_assemblies) basiert. Standardmäßig erstellt Visual C\+\+ alle nativen C\/C\+\+\-Anwendungen als isolierte Anwendungen, die [Manifeste](http://msdn.microsoft.com/library/aa375365) verwenden, um ihre Abhängigkeiten von Visual C\+\+\-Bibliotheken zu beschreiben.  
  
 Das Erstellen von C\/C\+\+\-Programmen als isolierte Anwendungen bietet eine Reihe von Vorteilen. Eine isolierte Anwendung ist beispielsweise nicht betroffen, wenn andere C\/C\+\+\-Anwendungen Visual C\+\+\-Bibliotheken installieren oder deinstallieren. Visual C\+\+\-Bibliotheken, die von isolierten Anwendungen verwendet werden, können trotzdem entweder in den lokalen Ordner der Anwendung oder durch Installation in den nativen Assemblycache \(WinSxS\) neu verteilt werden. Dennoch kann die Wartung von Visual C\+\+\-Bibliotheken für bereits bereitgestellte Anwendungen durch die Verwendung einer [Herausgeberkonfigurationsdatei](http://msdn.microsoft.com/library/aa375680) vereinfacht werden. Mit dem isolierten Anwendungsbereitstellungsmodell können Sie einfacher sicherstellen, dass C\/C\+\+\-Anwendungen, die auf einem bestimmten Computer ausgeführt werden, die neueste Version der Visual C\+\+\-Bibliotheken verwenden, aber gleichzeitig die Möglichkeit offenhalten, dass Systemadministratoren und Anwendungsentwickler die explizite Versionsbindung von Anwendungen an ihre abhängigen DLLs steuern können.  
  
 In diesem Abschnitt wird erläutert, wie Sie eine C\/C\+\+\-Anwendung als isolierte Anwendung erstellen und sicherstellen können, dass sie über ein Manifest an Visual C\+\+\-Bibliotheken gebunden ist. Die Informationen in diesem Abschnitt gelten primäre für systemeigene, oder nicht verwaltete, Visual C\+\+\-Anwendungen. Informationen zur Bereitstellung mit Visual C\+\+ erstellter nativer Anwendungen finden Sie unter [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
## In diesem Abschnitt  
 [Konzept der isolierten Anwendungen und der parallelen Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)  
  
 [Erstellen isolierter C\/C\+\+\-Anwendungen](../build/building-c-cpp-isolated-applications.md)  
  
 [Erstellen von parallelen C\/C\+\+\-Assemblys](../build/building-c-cpp-side-by-side-assemblies.md)  
  
 [Gewusst wie: Erstellen von COM\-Komponenten ohne Registrierung](../build/how-to-build-registration-free-com-components.md)  
  
 [Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM\-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
 [Manifestgenerierung für C\/C\+\+\-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)  
  
 [Problembehandlung](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
## Verwandte Abschnitte  
 [Isolierte Anwendungen und parallele Assemblys](http://msdn.microsoft.com/library/dd408052)  
  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)