---
title: Speicherverwaltungsfunktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0a298c7fb9e50bb17d37224b69ce342c54115d7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687295"
---
# <a name="memory-management-functions"></a>Speicherverwaltungsfunktionen
Dieses Dokument beschreibt die Speicherverwaltungsfunktionen, die die Concurrency Runtime bereitstellt, mit denen Sie reservieren und Freigeben von Arbeitsspeicher parallel.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie beim Optimieren der Leistung Ihrer Anwendungen unterstützt, empfiehlt es sich, dass die zu Beginn der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) Domänenmodus noch nicht mit der Concurrency Runtime.  
  
 Die Concurrency Runtime stellt zwei Speicherverwaltungsfunktionen, die für das zuordnen und befreien von Speicherblöcken parallel optimiert sind. Die [Concurrency:: Alloc](reference/concurrency-namespace-functions.md#alloc) Funktion belegt einen Speicherblock mit der angegebenen Größe. Die [Free](reference/concurrency-namespace-functions.md#free) Funktion gibt den Arbeitsspeicher frei, die vom zugeordnet wurde `Alloc`.  
  
> [!NOTE]
>  Die `Alloc` und `Free` Funktionen von voneinander abhängig. Verwenden der `Free` Funktion nur für das Freigeben des Speichers, der zugewiesen werden mithilfe der `Alloc` Funktion. Auch bei Verwendung der `Alloc` Funktion nur verwenden, um Arbeitsspeicher die `Free` Funktion um, dass der Arbeitsspeicher freizugeben.  
  
 Verwenden der `Alloc` und `Free` -Funktion bei der Belegung und Freigabe einen festen Satz von zuordnungsgrößen aus verschiedenen Threads oder Aufgaben. Die Concurrency Runtime zwischenspeichert, Arbeitsspeicher, ihn aus dem C-Laufzeit-Heap belegt. Die Concurrency Runtime verwaltet für jeden ausgeführten Thread einen separaten Arbeitsspeichercache; aus diesem Grund verwaltet die Laufzeit Arbeitsspeicher, ohne die Verwendung von Sperren oder Arbeitsspeicherbarrieren zu. Eine Anwendung Vorteile erbringt Weitere Artikel aus der `Alloc` und `Free` -Funktion bei der Arbeitsspeichercache häufiger zugegriffen wird. Angenommen, ein Thread, der häufig aufruft `Alloc` und `Free` Vorteile, die mehr als ein Thread, in erster Linie aufruft `Alloc` oder `Free`.  
  
> [!NOTE]
>  Wenn Sie verwenden diese Speicherverwaltungsfunktionen, und Ihre Anwendung verwendet viel Speicher, die Anwendung möglicherweise Geben Sie eine Bedingung Speichermangel früher als Sie erwarten. Da die Speicherblöcke, die von einem Thread zwischengespeichert werden nicht zu keinem anderen Thread verfügbar werden, wenn ein Thread viel Speicher enthält, ist, dass der Arbeitsspeicher nicht verfügbar.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel, verwendet der `Alloc` und `Free` Funktionen zur Verbesserung der Leistung von Speicher finden Sie unter [Vorgehensweise: verwenden Alloc und Free zum Verbessern der Arbeitsspeicherleistung](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Vorgehensweise: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)

