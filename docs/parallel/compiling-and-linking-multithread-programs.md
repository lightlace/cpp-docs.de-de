---
title: Kompilieren und Binden von Multithreadprogrammen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0145c480d74cb1978c1b6caef65489eae96501c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiling-and-linking-multithread-programs"></a>Kompilieren und Binden von Multithreadprogrammen
Das Programm Bounce.c hypervisorbasierte [Beispiel C-Multithreadprogramm](../parallel/sample-multithread-c-program.md).  
  
 Programme kompiliert werden standardmäßig mit Multithreading.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Kompilieren und verknüpfen das Multithreadprogramm Bounce.c aus in der Entwicklungsumgebung  
  
1.  Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.  
  
2.  In der **Projekttypen** Bereich, klicken Sie auf **Win32**.  
  
3.  In der **Vorlagen** Bereich, klicken Sie auf **Win32-Konsolenanwendung**, und nennen Sie das Projekt.  
  
4.  Fügen Sie die Datei mit der C-Quellcode zum Projekt hinzu.  
  
5.  Auf der **erstellen** Menüs, erstellen Sie das Projekt, indem Sie auf die **erstellen** Befehl.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Kompilieren und verknüpfen das Multithreadprogramm Bounce.c über die Befehlszeile  
  
1.  Kompilieren Sie und verknüpfen Sie das Programm:  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)