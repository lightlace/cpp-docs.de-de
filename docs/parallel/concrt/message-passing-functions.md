---
title: Funktionen zum Übergeben von Nachrichten
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 4e1052a59f355c4ad5a7c6b57724268c24a209b4
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143299"
---
# <a name="message-passing-functions"></a>Funktionen zum Übergeben von Nachrichten

Die Bibliothek für asynchrone Agents bietet verschiedene Funktionen, mit denen Sie Nachrichten zwischen Komponenten übergeben können.

Diese Nachrichten Übergabe Funktionen werden mit den verschiedenen Nachrichtenblock Typen verwendet. Weitere Informationen zu den Nachrichtenblock Typen, die vom Concurrency Runtime definiert werden, finden Sie unter [asynchrone Nachrichten Blöcke](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="top"></a> Abschnitte

In diesem Thema werden die folgenden Nachrichten Übergabe Funktionen beschrieben:

- [Senden und Asend](#send)

- [empfangen und Try_receive](#receive)

- [Beispiele](#examples)

## <a name="send"></a>Senden und Asend

Die Funktion " [parallelcurrency:: Send](reference/concurrency-namespace-functions.md#send) " sendet synchron eine Nachricht an das angegebene Ziel, und die Funktion " [parallelcurrency:: Asend](reference/concurrency-namespace-functions.md#asend) " sendet eine Nachricht asynchron an das angegebene Ziel. Die Funktionen `send` und `asend` warten, bis das Ziel anzeigt, dass die Nachricht letztendlich akzeptiert oder abgelehnt wird.

Die `send` Funktion wartet, bis das Ziel die Nachricht annimmt oder ablehnt, bevor Sie zurückkehrt. Die `send`-Funktion gibt **true** zurück, wenn die Nachricht übermittelt wurde, und andernfalls **false** . Da die `send`-Funktion synchron funktioniert, wartet die `send`-Funktion, bis das Ziel die Nachricht empfängt, bevor Sie zurückgegeben wird.

Umgekehrt wartet die `asend` Funktion nicht darauf, dass das Ziel die Nachricht annimmt oder ablehnt, bevor Sie zurückkehrt. Stattdessen gibt die `asend`-Funktion " **true** " zurück, wenn das Ziel die Nachricht annimmt und Sie letztendlich übernimmt. Andernfalls gibt `asend` **false** zurück, um anzugeben, dass das Ziel die Nachricht abgelehnt hat oder die Entscheidung über die Übernahme der Nachricht verschoben hat.

[[Nach oben](#top)]

## <a name="receive"></a>empfangen und Try_receive

Die Funktionen " [parallelcurrency:: Receive](reference/concurrency-namespace-functions.md#receive) " und " [parallelcurrency:: Try_receive](reference/concurrency-namespace-functions.md#try_receive) " lesen Daten aus einer bestimmten Quelle. Die `receive`-Funktion wartet auf die Verfügbarkeit von Daten, während die `try_receive`-Funktion sofort zurückgegeben wird.

Verwenden Sie die `receive`-Funktion, wenn Sie die Daten benötigen, um fortzufahren. Verwenden Sie die `try_receive`-Funktion, wenn Sie den aktuellen Kontext nicht blockieren dürfen oder wenn die Daten nicht fortgesetzt werden müssen.

[[Nach oben](#top)]

## <a name="examples"></a> Beispiele

Beispiele für die Verwendung der Funktionen `send` und `asend`sowie `receive` finden Sie in den folgenden Themen:

- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)

- [Vorgehensweise: Implementieren verschiedener Producer-Consumer-Muster](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die call- und transformer-Klassen](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Vorgehensweise: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Vorgehensweise: Auswählen von abgeschlossenen Aufgaben](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Vorgehensweise: Senden einer Nachricht in regelmäßigen Intervallen](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Vorgehensweise: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[Nach oben](#top)]

## <a name="see-also"></a>Weitere Informationen

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Send-Funktion](reference/concurrency-namespace-functions.md#send)<br/>
[ASend-Funktion](reference/concurrency-namespace-functions.md#asend)<br/>
[Receive-Funktion](reference/concurrency-namespace-functions.md#receive)<br/>
[Try_receive-Funktion](reference/concurrency-namespace-functions.md#try_receive)
