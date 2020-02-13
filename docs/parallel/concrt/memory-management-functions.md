---
title: Speicherverwaltungsfunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: aa1951211283ddf7e4823a920d5cdf19bd6d977d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141844"
---
# <a name="memory-management-functions"></a>Speicherverwaltungsfunktionen

In diesem Dokument werden die Funktionen zur Speicherverwaltung beschrieben, die der Concurrency Runtime bereitstellt, um Ihnen die gleichzeitige Arbeitsspeicher Zuteilung und-Freigabe zu erleichtern.

> [!TIP]
> Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie bei der Feinabstimmung der Leistung Ihrer Anwendungen unterstützt, empfehlen wir Ihnen, mit der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie mit der Concurrency Runtime noch nicht vertraut sind.

Der Concurrency Runtime stellt zwei Funktionen zur Speicherverwaltung bereit, die für das gleichzeitige zuordnen und Freigeben von Speicherblöcken optimiert sind. Die [parallelcurrency:: belegc](reference/concurrency-namespace-functions.md#alloc) -Funktion ordnet einen Speicherblock unter Verwendung der angegebenen Größe zu. Die [parallelcurrency:: Free](reference/concurrency-namespace-functions.md#free) -Funktion gibt den Arbeitsspeicher frei, der von `Alloc`reserviert wurde.

> [!NOTE]
> Die Funktionen `Alloc` und `Free` basieren aufeinander. Verwenden Sie die `Free`-Funktion nur, um Arbeitsspeicher freizugeben, den Sie mit der `Alloc`-Funktion zuordnen. Wenn Sie die `Alloc`-Funktion verwenden, um Speicher zuzuweisen, verwenden Sie außerdem nur die `Free`-Funktion, um diesen Arbeitsspeicher freizugeben.

Verwenden Sie die Funktionen `Alloc` und `Free`, wenn Sie einen festgelegten Satz von Zuordnungs Größen aus verschiedenen Threads oder Tasks zuordnen und freigeben. Der Concurrency Runtime speichert den Speicher zwischen, der aus dem C-Lauf Zeit Heap zugewiesen wird. Der Concurrency Runtime enthält einen separaten Arbeitsspeicher Cache für jeden laufenden Thread. Daher verwaltet die Laufzeit den Arbeitsspeicher, ohne Sperren oder Speicherbarrieren zu verwenden. Eine Anwendung profitiert von den Funktionen `Alloc` und `Free`, wenn der Speicher Cache häufiger aufgerufen wird. Beispielsweise profitiert ein Thread, der häufig sowohl `Alloc` und `Free` aufruft, mehr als ein Thread, der primär `Alloc` oder `Free`aufruft.

> [!NOTE]
> Wenn Sie diese Speicherverwaltungsfunktionen verwenden und Ihre Anwendung viel Arbeitsspeicher beansprucht, kann die Anwendung eine Bedingung mit geringem Arbeitsspeicher früher als erwartet eingeben. Da die Speicherblöcke, die von einem Thread zwischengespeichert werden, für keinen anderen Thread verfügbar sind, ist dieser Arbeitsspeicher nicht verfügbar, wenn ein Thread viel Speicherplatz enthält.

## <a name="example"></a>Beispiel

Ein Beispiel, in dem die Funktionen `Alloc` und `Free` verwendet werden, um die Speicherleistung zu verbessern, finden Sie unter Gewusst [wie: verwenden](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)von "Zuweisung" und "kostenlos", um die

## <a name="see-also"></a>Weitere Informationen

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Vorgehensweise: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
