---
title: Multithreadprogramme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ff73b4d3a1c8ee6971fbd3f88f491c2a5c76311
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="multithread-programs"></a>Multithreadprogramme
Ein Thread ist im Grunde einen Ausführungspfad über ein Programm. Es ist auch die kleinste Ausführungseinheit Win32 plant. Ein Thread besteht aus einem Stapel, den Status der CPU-Register und einen Eintrag in der Ausführungsliste des Zeitplanungsmoduls System. Jeder Thread gibt aller Prozesse Ressourcen frei.  
  
 Ein Prozess besteht aus einem oder mehreren Threads und den Code, Daten und andere Ressourcen von einem Programm im Arbeitsspeicher. Typische Programmressourcen sind geöffneten Dateien, Semaphoren und dynamisch reservierten Speicher. Ein Programm ausgeführt wird, wenn das System Zeitplanungsmodul eines Threads ausführungssteuerung bietet. Der Planer bestimmt, welche Threads ausgeführt werden sollen und wann ausgeführt werden soll. Threads mit niedrigerer Priorität möglicherweise warten, während Threads mit höherer Priorität ihre Tasks auszuführen. Auf Computern mit mehreren Prozessoren kann der Planer einzelne Threads auf verschiedenen Prozessoren die CPU-Last zu verteilen verschieben.  
  
 Jeder Thread in einem Prozess arbeitet unabhängig. Wenn Sie diese miteinander sichtbar machen, werden Threads einzeln ausgeführt und sind keine Kenntnis von anderen Threads in einem Prozess. Threads, die gemeinsame Nutzung allgemeiner Ressourcen müssen jedoch erlaubt, ihre Arbeit zu koordinieren, mithilfe von Semaphoren oder eine andere Methode für die prozessübergreifende Kommunikation. Weitere Informationen zum Synchronisieren von Threads finden Sie unter [Schreiben von Win32-Multithreadprogrammen](../parallel/writing-a-multithreaded-win32-program.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)