---
title: "Vorbereiten eines Testcomputers zum Ausf&#252;hren einer ausf&#252;hrbaren Debugdatei | Microsoft Docs"
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
  - "Ausführbare Debugdatei, Vorbereiten eines Testcomputers zum Ausführen"
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Vorbereiten eines Testcomputers zum Ausf&#252;hren einer ausf&#252;hrbaren Debugdatei
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um einen Computer zum Testen der Debugversion einer Anwendung vorzubereiten, die in Visual C\+\+ erstellt wurde, müssen Sie Debugversionen der Visual C\+\+\-Bibliothek\-DLLs bereitstellen, die für die Anwendung erforderlich sind.  Wenn Sie wissen möchten, welche DLLs bereitgestellt werden müssen, führen Sie die Schritte unter [Grundlegendes zu den Abhängigkeiten einer Visual C\+\+\-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) aus.  Die Namen der Debugversionen der DLLs für Visual C\+\+\-Bibliotheken enden in der Regel auf "d". Beispielsweise hat die Debugversion der "msvcr100.dll" den Namen "msvcr100d.dll".  
  
> [!NOTE]
>  Beachten Sie, dass weder die Debugversionen einer Anwendung noch die Debugversionen der DLLs \(Dynamic Link Libraries\) von Visual C\+\+\-Bibliothek verteilt werden dürfen.  Sie dürfen Debugversionen von Anwendungen und Visual C\+\+\-DLLs nur auf den anderen Computern, nur für den Zweck, eine Anwendung zu debuggen und zu testen auf einem Computer ohne Visual Studio bereitstellen.  Weitere Informationen finden Sie unter [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
 Es gibt drei Möglichkeiten, Debugversionen von DLLs für Visual C\+\+\-Bibliotheken zusammen mit der Debugversion einer Anwendung bereitzustellen.  
  
-   Verwenden Sie zum Installieren der Debugversion einer bestimmten Visual C\+\+\-DLL im %windir%\\system32\\\-Verzeichnis eine zentrale Bereitstellung, indem Sie ein Setup\-Projekt mit Mergemodulen für die richtige Bibliotheksversion und Architektur der Anwendung verwenden.  Mergemodule befinden sich im Verzeichnis "Programme" oder "Programme\(x86\)" unter "\\Gemeinsame Dateien\\Merge\\".  Bei der Debugversion eines Mergemoduls ist "Debug" Bestandteil des Namens, z. B. Microsoft\_VC110\_DebugCRT\_x86.msm.  Ein Beispiel für diese Bereitstellung finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C\+\+\-Anwendung mithilfe eines Setup\-Projekts](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Verwenden Sie eine lokale Bereitstellung, um die Debugversion einer bestimmten Visual C\+\+\-DLL im Installationsverzeichnis der Anwendung zu installieren, indem Sie die im Verzeichnis "Programme" oder "Programme\(x86\)" unter "\\Microsoft Visual Studio \<Version\>\\VC\\redist\\Debug\_NonRedist\\" bereitgestellten Dateien verwenden.  
  
    > [!NOTE]
    >  Um eine mithilfe von Visual C\+\+ 2005 oder Visual C\+\+ 2008 erstellte Anwendung remote auf einem anderen Computer zu debuggen, müssen Sie Debugversionen der Visual C\+\+\-Bibliotheks\-DLLs als freigegebene parallele Assemblys bereitstellen.  Sie können ein Setup\-Projekt oder Windows Installer zum Installieren von entsprechenden Mergemodulen verwenden.  
  
-   Verwenden Sie in Visual Studio die Option **Bereitstellen** im Dialogfeld **Konfigurations\-Manager**, um die Projektausgabe und andere Dateien zum Remotecomputer zu kopieren.  Ein Beispiel für diese Bereitstellung finden Sie unter [Einrichten des Remotedebuggens für ein Visual Studio\-Projekt](../Topic/Set%20Up%20Remote%20Debugging%20for%20a%20Visual%20Studio%20Project.md).  
  
 Nach der Installation von Visual C\+\+\-DLLs können Sie einen Remotedebugger auf dem Remotecomputer ausführen.  Weitere Informationen zum Remotedebuggen finden Sie unter [Einrichten der Remotetools auf dem Gerät](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md).  
  
## Siehe auch  
 [Einrichten der Remotetools auf dem Gerät](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)   
 [Bereitstellung in Visual C\+\+](../ide/deployment-in-visual-cpp.md)   
 [Befehlszeilenoptionen bei Windows Installer](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)