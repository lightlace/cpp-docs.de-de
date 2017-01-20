---
title: "Speicherverwaltungsfunktionen"
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
  - "Speicherverwaltungsfunktionen [Parallelitätslaufzeit]"
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
caps.latest.revision: 6
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherverwaltungsfunktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument werden die Speicherverwaltungsfunktionen der Concurrency Runtime beschrieben, die das parallele Reservieren und Freigeben von Arbeitsspeicher unterstützen.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Es ist daher nicht erforderlich, einen Planer in der Anwendung zu erstellen.  Der Taskplaner ermöglicht eine genauere Steuerung der Leistung von Anwendungen. Aus diesem Grund wird empfohlen, mit der [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie noch nicht mit der Concurrency Runtime vertraut sind.  
  
 Die Concurrency Runtime stellt zwei Speicherverwaltungsfunktionen bereit, die für das parallele Belegen und Freigeben von Speicherblöcken optimiert wurden.  Die [concurrency::Alloc](../Topic/Alloc%20Function.md)\-Funktion wird ein Speicherblock zu, indem die angegebenen Größe belegt.  Die [concurrency::Free](../Topic/Free%20Function.md)\-Funktion gibt den Arbeitsspeicher frei, der von `Alloc` zugeordnet wurde.  
  
> [!NOTE]
>  Die `Alloc`\-Funktion und die `Free`\-Funktion sind voneinander abhängig.  Verwenden Sie die `Free`\-Funktion nur zur Freigabe von Speicher, den Sie mit der `Alloc`\-Funktion belegt haben.  Und geben Sie mit der `Alloc`\-Funktion belegten Speicher nur mit der `Free`\-Funktion frei.  
  
 Verwenden Sie die `Alloc`\-Funktion und die `Free`\-Funktion zur Belegung und Freigabe einer festen Anzahl von Belegungsgrößen von unterschiedlichen Threads oder Aufgaben.  Die Concurrency Runtime verwendet Zwischenspeicherung für Speicher, der vom C\-Laufzeit\-Heap belegt wird.  Die Concurrency Runtime besitzt für jeden ausgeführten Thread einen separaten Arbeitsspeichercache. Aus diesem Grund verwaltet die Runtime Arbeitsspeicher, ohne dabei Sperren oder Arbeitsspeicherbarrieren zu verwenden.  Je häufiger auf den Arbeitsspeichercache zugegriffen wird, desto mehr profitiert eine Anwendung von den Funktionen `Alloc` und `Free`.  Beispielsweise profitiert ein Thread, der sowohl die `Alloc`\-Funktion als auch die `Free`\-Funktion häufig aufruft, mehr als ein Thread, der häufiger die `Alloc`\-Funktion oder die `Free`\-Funktion aufruft.  
  
> [!NOTE]
>  Wenn Sie diese Speicherverwaltungsfunktionen verwenden und Ihre Anwendung große Mengen an Arbeitsspeicher benötigt, tritt möglicherweise schneller als erwartet eine Speicherknappheit auf.  Die von einem Thread zwischengespeicherten Speicherblöcke sind für keinen anderen Thread verfügbar, das heißt, wenn ein Thread große Mengen an Arbeitsspeicher belegt, ist dieser Arbeitsspeicher nicht mehr verfügbar.  
  
## Beispiel  
 Ein Beispiel zur Verbesserung der Arbeitsspeicherleistung mit der `Alloc`\-Funktion und der `Free`\-Funktion finden Sie unter [Gewusst wie: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
## Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Gewusst wie: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)