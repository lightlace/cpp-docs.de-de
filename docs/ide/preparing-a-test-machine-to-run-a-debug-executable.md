---
title: "Vorbereiten eines Testcomputers zum Ausführen einer ausführbaren Debugdatei | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 344f413eb2325156996700b6975826600ab997f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Vorbereiten eines Testcomputers zum Ausführen einer ausführbaren Debugdatei
Um einen Computer zum Testen der Debugversion einer Anwendung vorzubereiten, die in Visual C++ erstellt wurde, müssen Sie Debugversionen der Visual C++-Bibliothek-DLLs bereitstellen, die für die Anwendung erforderlich sind. Um zu ermitteln, die DLLs bereitgestellt werden müssen, führen Sie die Schritte im [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Die Namen der Debugversionen der DLLs für Visual C++-Bibliotheken enden in der Regel auf "d". Beispielsweise hat die Debugversion der "msvcr100.dll" den Namen "msvcr100d.dll".  
  
> [!NOTE]
>  Beachten Sie, dass weder die Debugversionen einer Anwendung noch die Debugversionen der DLLs (Dynamic Link Libraries) von Visual C++-Bibliothek verteilt werden dürfen. Sie dürfen Debugversionen von Anwendungen und Visual C++-DLLs nur auf den anderen Computern, nur für den Zweck, eine Anwendung zu debuggen und zu testen auf einem Computer ohne Visual Studio bereitstellen. Weitere Informationen finden Sie unter [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).  
  
 Es gibt drei Möglichkeiten, Debugversionen von DLLs für Visual C++-Bibliotheken zusammen mit der Debugversion einer Anwendung bereitzustellen.  
  
-   Verwenden Sie zum Installieren der Debugversion einer bestimmten Visual C++-DLL im %windir%\system32\-Verzeichnis eine zentrale Bereitstellung, indem Sie ein Setup-Projekt mit Mergemodulen für die richtige Bibliotheksversion und Architektur der Anwendung verwenden. Mergemodule befinden sich in der Programmdateien oder (x86) Programmdateiverzeichnis in \Common Files\Merge Module\\. Bei der Debugversion eines Mergemoduls ist „Debug“ Bestandteil des Namens, z. B. Microsoft_VC110_DebugCRT_x86.msm. Ein Beispiel für diese Bereitstellung finden Sie ggf. unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Installieren der Debugversion einer bestimmten Visual C++-DLL im Installationsverzeichnis der Anwendung mithilfe von Dateien, die in der Programmdateien oder (x86) Programmdateiverzeichnis in \Microsoft Visual Studio bereitgestellt werden mithilfe einer lokalen Bereitstellung \<Version > \VC\redist\Debug_NonRedist\\.  
  
    > [!NOTE]
    >  Um eine mithilfe von Visual C++ 2005 oder Visual C++ 2008 erstellte Anwendung remote auf einem anderen Computer zu debuggen, müssen Sie Debugversionen der Visual C++-Bibliotheks-DLLs als freigegebene parallele Assemblys bereitstellen. Sie können ein Setup-Projekt oder Windows Installer zum Installieren von entsprechenden Mergemodulen verwenden.  
  
-   Verwenden Sie die Projektausgabe**bereitstellen** -Option in der **Configuration Manager** Dialogfeld in Visual Studio, um die Projektausgabe und andere Dateien auf dem Remotecomputer zu kopieren. 
  
 Nach der Installation von Visual C++-DLLs können Sie einen Remotedebugger auf dem Remotecomputer ausführen. Weitere Informationen zum Remotedebuggen finden Sie unter [Remotedebuggen](/visualstudio/debugger/remote-debugging.md).  
  
## <a name="see-also"></a>Siehe auch  
 
 [Bereitstellung in Visual C++](../ide/deployment-in-visual-cpp.md)   
 [Befehlszeilenoptionen für Windows Installer-Befehl](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [Beispiele für die Bereitstellung](../ide/deployment-examples.md) [des Remotedebuggens](/visualstudio/debugger/remote-debugging.md)