---
title: "PCH-Dateien im Erstellungsvorgang | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch-Dateien, Buildprozess"
  - "Makefiles, PCH-Dateien im Buildprozess"
  - "PCH-Dateien, Buildprozess"
ms.assetid: ebb4b368-8a11-4009-b347-01e79af02fbc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# PCH-Dateien im Erstellungsvorgang
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die CodeBase eines Softwareprojekts ist gewöhnlich in mehreren Quelldateien, Objektdateien, Bibliotheken und Headerdateien für C oder C\+\+ enthalten.  In der Regel koordiniert ein Makefile diese kombinierten Elemente im Rahmen einer ausführbaren Datei.  In der folgenden Abbildung wird die Struktur eines Makefiles dargestellt, das eine vorkompilierte Headerdatei verwendet.  Die **NMAKE**\-Makronamen und die Dateinamen in diesem Diagramm stimmen mit denen im Beispielcode unter [Beispielmakefile für PCH](../../build/reference/sample-makefile-for-pch.md) und [Beispielcode für PCH](../../build/reference/example-code-for-pch.md) überein.  
  
 In der nachstehenden Abbildung werden drei Diagrammelemente verwendet, um den Ablauf des Erstellungsvorgangs zu verdeutlichen.  Jede Datei bzw. jedes Makro wird durch ein benanntes Rechteck dargestellt, und die drei Makros stehen für eine oder mehrere Dateien.  Schattierte Bereiche stellen den jeweiligen Kompilierungs\- oder Verknüpfungsvorgang dar.  Die Pfeile zeigen an, welche Dateien und Makros während der Kompilierung oder des Verknüpfungsvorgangs miteinander kombiniert werden.  
  
 ![Makefile mit vorkompilierter Headerdatei](../../build/reference/media/vc30ow1.png "vc30OW1")  
Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet  
  
 Am Anfang des Diagramms befinden sich die beiden **NMAKE**\-Makros **STABLEHDRS** und **BOUNDRY**. In diesen Makros werden Dateien aufgelistet, die wahrscheinlich keine Rekompilierung erfordern.  Diese Dateien werden mit folgender Befehlszeichenfolge kompiliert:  
  
```  
CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp  
```  
  
 Dies geschieht nur, wenn die vorkompilierte Headerdatei \(**STABLE.pch**\) nicht vorhanden ist oder wenn Sie Änderungen an den in den beiden Makros aufgeführten Dateien vornehmen.  In beiden Fällen enthält die vorkompilierte Headerdatei ausschließlich Code aus den Dateien, die im **STABLEHDRS**\-Makro aufgelistet sind.  Führen Sie die letzte Datei, die vorkompiliert werden soll, im **BOUNDRY**\-Makro auf.  
  
 Die in diesen Makros aufgelisteten Dateien können entweder Headerdateien oder C\- bzw. C\+\+\-Quelldateien sein. \(Eine einzelne PCH\-Datei kann nicht für C\- und C\+\+\-Module zugleich verwendet werden.\) Beachten Sie, dass Sie das **hdrstop**\-Makro verwenden können, um die Vorkompilierung an einem bestimmten Punkt innerhalb der **BOUNDRY**\-Datei anzuhalten.  Weitere Informationen finden Sie unter [\/hdrstop](../../preprocessor/hdrstop.md).  
  
 Im weiteren Verlauf des Diagramms stellt **APPLIB.obj** den unterstützenden Code für die endgültige Anwendung dar.  Die Datei wird aus **APPLIB.cpp**, den im **UNSTABLEHDRS**\-Makro aufgelisteten Dateien und vorkompiliertem Code aus dem vorkompilierten Header erstellt.  
  
 **MYAPP.obj** ist die endgültige Anwendung.  Sie wird aus **MYAPP.cpp**, den im **UNSTABLEHDRS**\-Makro aufgelisteten Dateien und vorkompiliertem Code aus dem vorkompilierten Header erstellt.  
  
 Abschließend wird die ausführbare Datei **MYAPP.EXE** erstellt, indem die im **OBJS**\-Makro aufgelisteten Dateien \(**APPLIB.obj** und **MYAPP.obj**\) verknüpft werden.  
  
 Eine ausführlichere Beschreibung der Abbildung finden Sie unter:  
  
-   [Beispielmakefile für PCH](../../build/reference/sample-makefile-for-pch.md)  
  
-   [Beispielcode für PCH](../../build/reference/example-code-for-pch.md)  
  
## Siehe auch  
 [Verwenden von vorkompilierten Headern in einem Projekt](../../build/reference/using-precompiled-headers-in-a-project.md)