---
title: "Konzepte für Bereitstellungen mit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b40865266548067e2dda3782e66802c0dbe2844e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="deployment-concepts"></a>Bereitstellungskonzepte
Dieser Abschnitt beschreibt die wichtigsten Überlegungen für die Bereitstellung von C++-Anwendungen.  
  
## <a name="windows-installer-deployment-in-c"></a>Windows Installer-Bereitstellung in C++  
 Visual C++-Projekte verwenden die herkömmliche Windows Installer-Setup in der Regel für die Bereitstellung. Um eine Windows Installer-Bereitstellung vorzubereiten, Packen Ihrer Anwendung in einer Datei setup.exe und Verteilen dieser Datei zusammen mit einem Installer-Paket (MSI-Datei). Benutzer führen Sie dann auf setup.exe zum Installieren der Anwendung aus.  
  
 Verpacken Sie die Anwendung durch Hinzufügen eines Setupprojekts zur Projektmappe; Bei erstellt, erstellt das Setup und die Installer Paketdateien, die Sie an Benutzer verteilen. Weitere Informationen finden Sie unter [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).  
  
## <a name="library-dependencies"></a>Bibliothekabhängigkeiten  
 Wenn eine C/C++-Anwendung mithilfe von Visual C++-Bibliotheken bereitgestellte Funktionalität erstellt wird, wird es von abhängt, die das Vorhandensein von diesen Bibliotheken zur Laufzeit. In der Reihenfolge für die Anwendung ausgeführt wird müssen sie, entweder statisch oder dynamisch, den erforderlichen Visual C++-Bibliotheken verknüpfen. Wenn eine Anwendung dynamisch Links in einer Visual C++-Bibliothek, und klicken Sie dann bei der Ausführung dieser Bibliothek vorhanden sein muss, damit sie geladen werden können. Andererseits, wenn die Anwendung statisch mit einer Visual C++-Bibliothek verknüpft ist, benötigt dann sie nicht die entsprechenden DLLs auf dem Computer des Benutzers vorhanden sein. Statisches verknüpfen, gibt es einige negativen Auswirkungen, z. B. das Erhöhen der Größe der Dateien der Anwendung und Wartung möglicherweise schwieriger machen. Weitere Informationen finden Sie unter [Vorteile der Verwendung von DLLs](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).  
  
## <a name="packaging-and-redistributing"></a>Packen und verteilen  
 Visual C++-Bibliotheken als DLLs verpackt sind, und alle erforderlichen Bibliotheken für C/C++-Anwendungen von Visual Studio auf dem Computer des Entwicklers installiert sind. Wenn Sie Ihre Anwendung für Benutzer bereitstellen zu können, ist es jedoch nicht möglich, in den meisten Fällen müssen sie Visual Studio zu installieren, um die Anwendung ausgeführt werden. Es ist wichtig, in der Lage, nur die Teile von Visual C++ neu verteilen, die von der Anwendung für die ordnungsgemäße Ausführung benötigt werden.  
  
 Weitere Informationen zu packen und verteilen finden Sie unter den folgenden Themen:  
  
-   [Bestimmen die zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).  
  
 Beispiele für die Bereitstellung und Vorschläge zur Problembehandlung finden Sie unter:  
  
-   [Beispiele für die Bereitstellung](../ide/deployment-examples.md).  
  
-   [Problembehandlung von C/C++-Anwendungen und Seite-an-Seite-Assemblys isoliert](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows Installer-Bereitstellung](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)