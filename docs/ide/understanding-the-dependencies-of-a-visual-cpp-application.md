---
title: Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application deployment [C++], dependencies
- Dependency Walker
- dependencies [C++], application deployment and
- deploying applications [C++], dependencies
- DUMPBIN utility
- DLLs [C++], dependencies
- depends.exe
- libraries [C++], application deployment issues
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da2aadeba69a8be29627650ba6ef24516098a8e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung
Um die Visual C++-Bibliotheken zu ermitteln, eine Anwendung abhängig ist, können Sie die Projekteigenschaften anzeigen. (Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** So öffnen die **Eigenschaftenseiten** (Dialogfeld).) Sie können auch den Dependency Walker (depends.exe) verwenden, der ein umfassenderes Bild der Abhängigkeiten verschafft.  
  
 In der **Eigenschaftenseiten** (Dialogfeld), können Sie verschiedene Seiten unter untersuchen **Konfigurationseigenschaften** , die Abhängigkeiten zu verstehen. Wenn Ihr Projekt verwendet die MFC-Bibliotheken, und wählen Sie z. B. **Verwendung von MFC**, **MFC in einer gemeinsam genutzten DLL verwenden** auf die **Konfigurationseigenschaften**, **Allgemein**  Seite, die Anwendung zur Laufzeit auf die MFC-DLLs abhängt, wie Mfc\<Version > .dll. Wenn Ihre Anwendung MFC nicht verwendet, es möglicherweise richten sich nach der CRT-Bibliothek auf Wunsch eine **-Laufzeitbibliothek** Wert **Multithreaded-Debug-DLL (/ MDd)** oder **Multithreaded-DLL (/ MD)** auf die **Konfigurationseigenschaften**, **C/C++-**, **Codegenerierung** Seite.  
  
 Sie können umfassender bestimmen, von welchen DLLs eine Anwendung abhängt, indem Sie die Anwendung mit Dependency Walker (depends.exe) öffnen. Sie können das Tool aus dem [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640) Website.  
  
 Wenn Sie „depends.exe“ verwenden, können Sie eine Liste mit DLLs überprüfen, die zur Ladezeit mit der Anwendung verknüpft sind, sowie eine Liste mit den verzögert geladenen DLLs. Wenn Sie eine vollständige Liste mit DLLs erhalten möchten, die zur Laufzeit dynamisch geladen werden, können Sie die Profilerstellungsfunktion in „depends.exe“ verwenden. Hiermit können Sie die Anwendung testen, bis Sie sicher sind, dass alle Codepfade ausgeführt wurden. Nach Abschluss der Profilerstellungssitzung zeigt „depends.exe“ an, welche DLLs zur Laufzeit dynamisch geladen wurden.  
  
 Bedenken Sie bei Verwendung von depends.exe, dass eine DLL von einer anderen DLL oder einer bestimmten Version einer DLL abhängig sein kann. Sie können depends.exe sowohl auf dem Entwicklungscomputer als auch auf einem Zielcomputer verwenden. Auf dem Entwicklungscomputer gibt depends.exe die DLLs zurück, die zur Unterstützung einer Anwendung erforderlich sind. Wenn Sie Schwierigkeiten dabei haben, eine Anwendung auf einem Zielcomputer auszuführen, können Sie depends.exe dorthin kopieren und die Anwendung dann im Tool öffnen, sodass Sie bestimmen können, ob irgendwelche DLLs fehlen oder falsch sind.  
  
 Wenn Sie wissen, von welchen DLLs die Anwendung abhängt, können Sie bestimmen, welche davon Sie bei einer Bereitstellung auf einem anderen Computer gemeinsam mit der Anwendung verteilen müssen. In den meisten Fällen müssen Sie nicht-System-DLLs verteilen, aber möglicherweise müssen Sie die DLLs für Visual C++-Bibliotheken zu verteilen. Weitere Informationen finden Sie unter [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)