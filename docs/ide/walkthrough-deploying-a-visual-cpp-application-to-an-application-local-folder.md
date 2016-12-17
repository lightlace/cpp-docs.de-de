---
title: "Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung in einem lokalen Anwendungsordner"
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
  - "Bereitstellen von Visual C++-Anwendungen"
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung in einem lokalen Anwendungsordner
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt, wie eine Visual C\+\+\-Anwendung durch Kopieren von Dateien in einem Ordner bereitgestellt wird.  
  
## Vorbereitungsmaßnahmen  
  
-   Ein Computer, der Visual Studio installiert ist.  
  
-   Ein anderer Computer, der die Visual C\+\+\-Bibliotheken nicht vorhanden sind.  
  
### So stellen Sie eine Anwendung in einem lokalen Anwendungsordner bereit  
  
1.  Erstellen Sie eine MFC\-Anwendung auf, indem Sie die Schritte in [Exemplarische Vorgehensweise: Bereitstellen einer Visual C\+\+\-Anwendung mithilfe eines Setup\-Projekts](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md) folgen.  
  
2.  Kopieren Sie die erforderlichen MFC\- und die Bibliothek der C\-Laufzeit \(CRT\) Datei – z. B. für eine x86\-Zielplattform und eine Unicode\-Unterstützung, msvcr100.dll und msvcr100.dll von \\Programme\\Microsoft Visual Studio 10.0\\VC\\redist\\x86\\ – und fügen Sie sie in im Ordner \\Release\\ des MFC\-Projekts ein.  Weitere Informationen zu anderen Dateien, die Sie möglicherweise kopieren müssen, finden Sie unter [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Führen Sie die MFC\-Anwendung auf einem zweiten Computer aus, der die Visual C\+\+\-Bibliotheken nicht vorhanden sind.  
  
    1.  Kopieren Sie den Inhalt des Ordners \\Release\\ und fügen Sie sie im Anwendungsordner auf dem zweiten Computer ein.  
  
    2.  Führen Sie die Anwendung auf dem zweiten Computer aus.  
  
     Die Anwendung wird erfolgreich ausgeführt, da die Visual C\+\+\-Bibliotheken im lokalen Anwendungsordner verfügbar sind.  
  
## Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)