---
title: Multithreadprogramme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ece834bd6bf85daacbbaf50110e6e278da1ae099
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686931"
---
# <a name="multithread-programs"></a>Multithreadprogramme
Ein Thread ist im Grunde einen Ausführungspfad über ein Programm. Es ist auch die kleinste Ausführungseinheit Win32 plant. Ein Thread besteht aus einem Stapel, den Status der CPU-Register und einen Eintrag in der Ausführungsliste des Zeitplanungsmoduls System. Jeder Thread gibt aller Prozesse Ressourcen frei.  
  
 Ein Prozess besteht aus einem oder mehreren Threads und den Code, Daten und andere Ressourcen von einem Programm im Arbeitsspeicher. Typische Programmressourcen sind geöffneten Dateien, Semaphoren und dynamisch reservierten Speicher. Ein Programm ausgeführt wird, wenn das System Zeitplanungsmodul eines Threads ausführungssteuerung bietet. Der Planer bestimmt, welche Threads ausgeführt werden sollen und wann ausgeführt werden soll. Threads mit niedrigerer Priorität möglicherweise warten, während Threads mit höherer Priorität ihre Tasks auszuführen. Auf Computern mit mehreren Prozessoren kann der Planer einzelne Threads auf verschiedenen Prozessoren die CPU-Last zu verteilen verschieben.  
  
 Jeder Thread in einem Prozess arbeitet unabhängig. Wenn Sie diese miteinander sichtbar machen, werden Threads einzeln ausgeführt und sind keine Kenntnis von anderen Threads in einem Prozess. Threads, die gemeinsame Nutzung allgemeiner Ressourcen müssen jedoch erlaubt, ihre Arbeit zu koordinieren, mithilfe von Semaphoren oder eine andere Methode für die prozessübergreifende Kommunikation. Weitere Informationen zum Synchronisieren von Threads finden Sie unter [Schreiben von Win32-Multithreadprogrammen](../parallel/writing-a-multithreaded-win32-program.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)