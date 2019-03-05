---
title: Speicherverwaltungsfunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: 9a7810267c3eaa11ad7592774440365620e7e8f4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276935"
---
# <a name="memory-management-functions"></a>Speicherverwaltungsfunktionen

Dieses Dokument beschreibt die Speicherverwaltungsfunktionen, die die Concurrency Runtime bereitstellt, mit denen Sie die Belegung und Freigabe von Arbeitsspeicher parallel.

> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner die Leistung Ihrer Anwendungen optimieren können, es wird empfohlen, zunächst die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) möchten noch nicht mit der Concurrency Runtime.

Die Concurrency Runtime stellt zwei Speicherverwaltungsfunktionen, die für das zuordnen und befreien von Speicherblöcken parallel optimiert sind. Die [Concurrency:: Alloc](reference/concurrency-namespace-functions.md#alloc) Funktion belegt einen Speicherblock mithilfe der angegebenen Größe. Die [Concurrency](reference/concurrency-namespace-functions.md#free) Funktion gibt den Arbeitsspeicher frei, der von belegt wurde `Alloc`.

> [!NOTE]
>  Die `Alloc` und `Free` Funktionen aufeinander angewiesen sind. Verwenden der `Free` Funktion nur, um Arbeitsspeicher freizugeben, die Sie mithilfe von Zuordnen der `Alloc` Funktion. Auch bei Verwendung der `Alloc` Funktion zum Zuordnen von Arbeitsspeicher verwenden Sie nur die `Free` Funktion, die diesen Speicher freizugeben.

Verwenden der `Alloc` und `Free` funktioniert, wenn die Belegung und Freigabe einen festen Satz von zuordnungsgrößen von anderen Threads oder Aufgaben. Die Concurrency Runtime wird Arbeitsspeicher, die sie aus dem Heap der C-Laufzeit weist zwischengespeichert. Die Concurrency Runtime verwaltet für jeden ausgeführten Thread einen separaten Arbeitsspeichercache; aus diesem Grund verwaltet die Laufzeit Arbeitsspeicher, ohne die Verwendung von Sperren oder Arbeitsspeicherbarrieren zu. Vorteile von eine Anwendung mehr über die `Alloc` und `Free` funktioniert, wenn auf der Arbeitsspeichercache häufiger zugegriffen wird. Z. B. ein Thread, der sowohl häufig ruft `Alloc` und `Free` Vorteile, die mehr als ein Thread, die in erster Linie aufruft `Alloc` oder `Free`.

> [!NOTE]
>  Wenn Sie diesen Speicherverwaltungsfunktionen, und Ihre Anwendung verwendet viel Arbeitsspeicher, die Anwendung möglicherweise Geben Sie ein wenig Arbeitsspeicher vorhanden ist früher als Sie erwarten. Da die Speicherblöcke, die von einem Thread zwischengespeichert werden nicht zur Verfügung keinem anderen Thread, stehen Wenn ein Thread viel Speicher enthält, ist, dass der Speicher nicht verfügbar.

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der `Alloc` und `Free` Funktionen zur Verbesserung der speicherleistung finden Sie unter [Vorgehensweise: Mithilfe von Alloc und Free Verbessern der Arbeitsspeicherleistung](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

## <a name="see-also"></a>Siehe auch

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Vorgehensweise: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
