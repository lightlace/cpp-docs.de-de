---
title: "Grundlegendes zu den Abh&#228;ngigkeiten einer Visual C++-Anwendung"
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
  - "Anwendungsbereitstellung [C++], Abhängigkeiten"
  - "Abhängigkeiten [C++], Anwendungsbereitstellung und"
  - "Dependency Walker"
  - "depends.exe"
  - "Bereitstellen von Anwendungen [C++], Abhängigkeiten"
  - "DLLs [C++], Abhängigkeiten"
  - "DUMPBIN-Dienstprogramm"
  - "Bibliotheken [C++], Anwendungsbereitstellungsprobleme"
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# Grundlegendes zu den Abh&#228;ngigkeiten einer Visual C++-Anwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um zu bestimmen, von welchen [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken eine Anwendung abhängt, können Sie die Projekteigenschaften anzeigen.  \(Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften**, um das Dialogfeld **Eigenschaftenseiten** zu öffnen.\) Sie können auch den Dependency Walker \(depends.exe\) verwenden, der ein umfassenderes Bild der Abhängigkeiten verschafft.  
  
 Im Dialogfeld **Eigenschaftenseiten** können Sie verschiedene Seiten unter **Konfigurationseigenschaften** überprüfen, um die Abhängigkeiten zu verstehen.  Wenn im Projekt beispielsweise die MFC\-Bibliotheken verwendet werden und Sie **Verwendung von MFC** und **MFC in einer gemeinsam genutzten DLL verwenden** in den **Konfigurationseigenschaften** auf der Seite **Allgemein** wählen, ist Ihre Anwendung zur Laufzeit von MFC\-DLLs abhängig, z. B. „mfc\<version\>.dll“.  Wenn die Anwendung MFC nicht verwendet, kann sie dennoch von der CRT\-Bibliothek abhängig sein, wenn Sie einen **Laufzeitbibliothek**\-Wert von **Multithreaded\-Debug\-DLL \(\/MDd\)** oder **Multithreaded\-DLL \(\/MD\)** in den **Konfigurationseigenschaften**, **C\/C\+\+**, Seite **Codegenerierung**, wählen.  
  
 Sie können umfassender bestimmen, von welchen DLLs eine Anwendung abhängt, indem Sie die Anwendung mit Dependency Walker \(depends.exe\) öffnen.  Sie können das Tool von der [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640)\-Website herunterladen.  
  
 Wenn Sie „depends.exe“ verwenden, können Sie eine Liste mit DLLs überprüfen, die zur Ladezeit mit der Anwendung verknüpft sind, sowie eine Liste mit den verzögert geladenen DLLs.  Wenn Sie eine vollständige Liste mit DLLs erhalten möchten, die zur Laufzeit dynamisch geladen werden, können Sie die Profilerstellungsfunktion in „depends.exe“ verwenden. Hiermit können Sie die Anwendung testen, bis Sie sicher sind, dass alle Codepfade ausgeführt wurden.  Nach Abschluss der Profilerstellungssitzung zeigt „depends.exe“ an, welche DLLs zur Laufzeit dynamisch geladen wurden.  
  
 Bedenken Sie bei Verwendung von depends.exe, dass eine DLL von einer anderen DLL oder einer bestimmten Version einer DLL abhängig sein kann.  Sie können depends.exe sowohl auf dem Entwicklungscomputer als auch auf einem Zielcomputer verwenden.  Auf dem Entwicklungscomputer gibt depends.exe die DLLs zurück, die zur Unterstützung einer Anwendung erforderlich sind.  Wenn Sie Schwierigkeiten dabei haben, eine Anwendung auf einem Zielcomputer auszuführen, können Sie depends.exe dorthin kopieren und die Anwendung dann im Tool öffnen, sodass Sie bestimmen können, ob irgendwelche DLLs fehlen oder falsch sind.  
  
 Wenn Sie wissen, von welchen DLLs die Anwendung abhängt, können Sie bestimmen, welche davon Sie bei einer Bereitstellung auf einem anderen Computer gemeinsam mit der Anwendung verteilen müssen.  System\-DLLs müssen in den meisten Fällen nicht verteilt werden, eventuell aber DLLs für [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken.  Weitere Informationen finden Sie unter [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md).  
  
## Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)