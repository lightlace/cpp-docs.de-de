---
title: "Bereitstellungskonzepte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsbereitstellung [C++], Informationen über Anwendungsbereitstellung"
  - "Abhängigkeiten [C++], Anwendungsbereitstellung und"
  - "Bereitstellen von Anwendungen [C++], Informationen über das Bereitstellen von Anwendungen"
  - "Bibliotheken [C++], Anwendungsbereitstellungsprobleme"
  - "Windows Installer [C++]"
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Bereitstellungskonzepte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt werden grundlegende Überlegungen zur Bereitstellung von C\+\+\-Anwendungen erläutert.  
  
## Bereitstellung mit Windows Installer in C\+\+  
 Zur Bereitstellung für Visual C\+\+\-Projekte wird in der Regel das traditionelle Windows Installer\-Setup verwendet.  Zur Vorbereitung einer Bereitstellung mit Windows Installer packen Sie Ihre Anwendung in eine Datei mit dem Namen setup.exe und verteilen diese Datei zusammen mit einem Installationspaket \(.msi\).  Benutzer führen dann die Datei setup.exe aus, um die Anwendung zu installieren.  
  
 Zum Packen der Anwendung müssen Sie der Projektmappe ein Setup\-Projekt hinzufügen; beim Buildprozess werden dann die Setupdateien und das Installationspaket für die Verteilung an die Benutzer erstellt.  Weitere Informationen finden Sie unter [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).  
  
## Bibliotheksabhängigkeiten  
 Wenn eine C\/C\+\+\-Anwendung mit Funktionen erstellt wird, die von Visual C\+\+\-Bibliotheken bereitgestellt werden, besteht zur Laufzeit eine Abhängigkeit der Anwendung von diesen Bibliotheken.  Damit die Anwendung ausgeführt werden kann, muss sie statisch oder dynamisch mit den benötigten Visual C\+\+\-Bibliotheken verknüpft sein.  Wenn eine Anwendung dynamisch mit einer Visual C\+\+\-Bibliothek verknüpft ist, muss diese Bibliothek beim Ausführen zur Verfügung stehen, damit sie geladen werden kann.  Wenn die Anwendung jedoch statisch mit einer Visual C\+\+\-Bibliothek verknüpft ist, müssen die entsprechenden DLLs nicht auf dem Computer des Benutzers zur Verfügung stehen.  Statische Verknüpfungen haben aber auch Nachteile, da die Anwendungsdateien größer werden und eventuell schwieriger zu warten sind.  Weitere Informationen finden Sie unter [Vorteile der Verwendung von DLLs](../build/advantages-of-using-dlls.md).  
  
## Packen und Verteilen  
 Visual C\+\+\-Bibliotheken werden als DLLs gepackt, und alle für C\/C\+\+\-Anwendungen notwendigen Bibliotheken werden von Visual Studio auf dem Computer des Entwicklers installiert.  Wenn Sie die Anwendung für Benutzer bereitstellen, können Sie in den meisten Fällen jedoch nicht von allen Benutzern erwarten, dass sie zur Ausführung der Anwendung Visual Studio installieren.  Sie sollten nur die Teile von Visual C\+\+ verteilen können, die zum ordnungsgemäßen Ausführen der Anwendung erforderlich sind.  
  
 Weitere Informationen zum Packen und Verteilen erhalten Sie unter folgenden Themen:  
  
-   [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).  
  
 Bereitstellungsbeispiele und Vorschläge zu Problembehebung finden Sie unter:  
  
-   [Bereitstellungsbeispiele](../ide/deployment-examples.md).  
  
-   [Problembehandlung](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows Installer Deployment](assetId:///121be21b-b916-43e2-8f10-8b080516d2a0)