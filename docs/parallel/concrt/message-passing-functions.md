---
title: Funktionen zum Übergeben von Nachrichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7435bdbc4d5959771a1f80e2ad12f038a8157bae
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162281"
---
# <a name="message-passing-functions"></a>Funktionen zum Übergeben von Meldungen

Die Asynchronous Agents Library stellt mehrere Funktionen, mit denen Sie Nachrichten zwischen Komponenten übergeben.

Diese Nachrichtenaustausch-Funktionen werden mit den verschiedenen Nachrichtenblocktypen verwendet. Weitere Informationen zu den Nachrichtenblocktypen, die von der Concurrency Runtime definiert sind, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).

##  <a name="top"></a> Abschnitte

In diesem Thema werden die folgenden Nachrichtenaustausch-Funktionen beschrieben:

- [Senden und asend](#send)

- [empfangen und Try_receive](#receive)

- [Beispiele](#examples)

##  <a name="send"></a> Senden und asend

Die [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion sendet eine Nachricht synchron an das angegebene Ziel und die [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) -Funktion sendet eine Nachricht asynchron an das angegebene Ziel. Sowohl die `send` und `asend` Funktionen warten, bis das Ziel angibt, dass es schließlich akzeptieren oder ablehnen wird.

Die `send` Funktion wartet, bis das Ziel akzeptiert, oder die Nachricht ablehnt, bevor sie zurückkehrt. Die `send` -Funktion zurückgegeben **"true"** , wenn die Nachricht übermittelt wurde und **"false"** andernfalls. Da die `send` Funktion funktioniert synchron, die `send` Funktion wartet, bis das Ziel die Nachricht empfangen, bevor sie zurückkehrt.

Im Gegensatz dazu die `asend` Funktion wartet nicht das Ziel zum annehmen oder Ablehnen der Nachricht, bevor sie zurückkehrt. Stattdessen die `asend` -Funktion zurückgegeben **"true"** Wenn das Ziel die Nachricht annimmt und schließlich. Andernfalls `asend` gibt **"false"** um anzugeben, dass das Ziel die Meldung abgelehnt hat oder die Entscheidung, ob die Meldung zurückgestellt.

[[Nach oben](#top)]

##  <a name="receive"></a> empfangen und Try_receive

Die [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) und [Concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive) Funktionen Lesen von Daten aus einer angegebenen Quelle. Die `receive` Funktion wartet, bis Daten verfügbar sind, während die `try_receive` Funktion wird sofort zurückgegeben.

Verwenden der `receive` funktionieren, wenn Sie die Daten weiterhin benötigen. Verwenden der `try_receive` ausgeführt werden, wenn Sie den aktuellen Kontext nicht blockieren dürfen oder Sie haben keinen damit die Daten, um den Vorgang fortzusetzen.

[[Nach oben](#top)]

##  <a name="examples"></a> Beispiele

Beispiele für die Verwendung der `send` und `asend`, und `receive` -Funktionen finden Sie unter den folgenden Themen:

- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)

- [Vorgehensweise: Implementieren verschiedener Producer-Consumer-Muster](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die call- und transformer-Klassen](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Vorgehensweise: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Vorgehensweise: Auswählen von abgeschlossenen Aufgaben](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Vorgehensweise: Senden einer Nachricht in regelmäßigen Intervallen](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Vorgehensweise: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[Nach oben](#top)]

## <a name="see-also"></a>Siehe auch

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Send-Funktion](reference/concurrency-namespace-functions.md#send)<br/>
[Asend-Funktion](reference/concurrency-namespace-functions.md#asend)<br/>
[Receive-Funktion](reference/concurrency-namespace-functions.md#receive)<br/>
[Try_receive-Funktion](reference/concurrency-namespace-functions.md#try_receive)

