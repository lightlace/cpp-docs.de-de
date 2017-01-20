---
title: "Ermitteln der neu zu verteilenden DLLs"
ms.custom: na
ms.date: "12/13/2016"
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
  - "Anwendungsbereitstellung [C++], DLL-Verteilung"
  - "Abhängigkeiten [C++], Anwendungsbereitstellung und"
  - "Bereitstellen von Anwendungen [C++], DLL-Verteilung"
  - "DLLs [C++], Verteilen"
  - "Verteilen von DLLs"
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: 31
caps.handback.revision: "31"
ms.author: "corob"
manager: "ghogen"
---
# Ermitteln der neu zu verteilenden DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Erstellen einer Anwendung, die von Visual Studio bereitgestellte DLLs verwendet, müssen Benutzer der Anwendung auch diese DLLs auf ihren Computern haben, damit die Anwendung ausgeführt werden kann.  Da die meisten Benutzer wahrscheinlich nicht Visual Studio installiert haben, müssen Sie diese DLLs für sie bereitstellen.  Visual Studio stellt diese DLLs als verteilbare Bibliotheken zur Verfügung, die Sie in das Installationsprogramm der Anwendung einschließen können.  
  
 Die verteilbaren DLLs sind Teil der Installation von Visual Studio.  Standardmäßig werden sie im Ordner "Programme \(X 86\)\\Microsoft Visual Studio\-Version\\VC\\Redist" installiert.  Um das Einschließen in den Installer zu erleichtern, sind sie auch als eigenständige verteilbare Pakete über das Microsoft Download Center verfügbar.  Hierbei handelt es sich um ausführbare Dateien, die die verteilbaren Dateien auf dem Computer eines Benutzers installieren.  Die Version des verteilbaren Pakets muss der Version des Visual Studio\-Toolsets entsprechen, das zum Erstellen der Anwendung verwendet wird.  Um ein passendes verteilbares Paket zu finden, suchen Sie im [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?LinkId=158431) nach "Visual C\+\+ Redistributable Packages".  
  
 Um zu bestimmen, welche DLLs mit der Anwendung verteilt werden müssen, sammeln Sie eine Liste der DLLs, von denen die Anwendung abhängig ist.  Eine Methode zum Sammeln der Liste ist die Ausführung von Dependency Walker \(depends.exe\), wie in [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) beschrieben.  
  
 Liegt die Liste der Abhängigkeiten vor, vergleichen Sie sie mit der Liste in einer Redist.txt\-Datei im Microsoft Visual Studio\-Installationsverzeichnis oder mit der "REDIST\-Liste" verteilbarer DLLs, auf die im Abschnitt "Verteilbarer Code" der Microsoft\-Softwarelizenzbedingungen für Ihre Version von Visual Studio verwiesen wird.  Für Visual Studio 2013 finden Sie die die Liste online unter [Verteilbarer Code für Microsoft Visual Studio 2013 und Microsoft Visual Studio 2013 SDK](http://go.microsoft.com/fwlink/p/?LinkId=313603).  Sie können nicht alle Dateien weiterverteilen, die in Visual Studio enthalten sind. Sie sind nur zur Weiterverteilung der Dateien berechtigt, die in "Redist.txt" oder in der "REDIST\-Liste" online angegeben sind. Debugversionen von Anwendungen und die verschiedenen Visual C\+\+\-Debug\-DLLs sind nicht weiterverteilbar.  Weitere Informationen finden Sie unter [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).  
  
 In der folgenden Tabelle werden einige der Visual C\+\+\-DLLs beschrieben, von denen Ihre Anwendung möglicherweise abhängig ist.  
  
|Visual C\+\+\-Bibliothek|Beschreibung|Betrifft|  
|------------------------------|------------------|--------------|  
|msvcr*Version*.dll|C\-Laufzeitbibliothek \(CRT\) für systemeigenen Code.|Anwendungen, die die [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md) verwenden.|  
|msvcp*Version*.dll|C\+\+\-Standardbibliothek für systemeigenen Code.|Anwendungen, die die [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md) verwenden.|  
|mfc*Version*.dll|Microsoft Foundation Class\-Bibliothek \(MFC\-Bibliothek\).|Anwendungen, die die [MFC\-Bibliothek](../mfc/mfc-desktop-applications.md) verwenden.|  
|mfc*Version*u.dll|MFC\-Bibliothek mit Unicode\-Unterstützung.|Anwendungen, die die [MFC\-Bibliothek](../mfc/mfc-desktop-applications.md) verwenden und Unicode\-Unterstützung erfordern.|  
|mfcmifc80.dll|MFC\-Bibliothek für verwaltete Schnittstellen.|Anwendungen, die die [MFC\-Bibliothek](../mfc/mfc-desktop-applications.md) und [Windows Forms\-Steuerelemente](../Topic/Windows%20Forms%20Controls.md) verwenden.|  
|mfcm*Version*.dll|Verwaltete MFC\-Bibliothek.|Anwendungen, die die [MFC\-Bibliothek](../mfc/mfc-desktop-applications.md) und [Windows Forms\-Steuerelemente](../Topic/Windows%20Forms%20Controls.md) verwenden.|  
|mfcm*Version*u.dll|Verwaltete MFC\-Bibliothek mit Unicode\-Unterstützung.|Anwendungen, die die [MFC\-Bibliothek](../mfc/mfc-desktop-applications.md) und [Windows Forms\-Steuerelemente](../Topic/Windows%20Forms%20Controls.md) sowie Unicode\-Unterstützung erfordern.|  
  
> [!NOTE]
>  Sie müssen nicht mehr die Active Template Library als eine separate DLL weiterverteilen.  Die Funktionalität wurde in Header und eine statische Bibliothek verschoben.  
  
 Weitere Informationen zur Weiterverteilung dieser DLLs mit der Anwendung finden Sie unter [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md).  Beispiele finden Sie in [Bereitstellungsbeispiele](../ide/deployment-examples.md).  
  
 In der Regel müssen Sie keinen System\-DLLs zu verteilen, da sie Teil des Betriebssystems sind.  Allerdings gelten möglicherweise Ausnahmen, z. B., wenn die Anwendung auf mehreren Versionen von Microsoft\-Betriebssystemen ausgeführt wird.  In diesem Fall müssen Sie die entsprechenden Lizenzbedingungen lesen.  Versuchen Sie außerdem, die System\-DLLs entweder mittels Windows Update, Service Packs oder verteilbarer Pakete von Microsoft zu aktualisieren.  Verfügbare Pakete finden Sie möglicherweise auf der [Microsoft Support](http://support.microsoft.com/)\-Website oder im [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?LinkId=158431).  
  
## Siehe auch  
 [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md)   
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)