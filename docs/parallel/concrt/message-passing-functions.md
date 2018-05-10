---
title: Funktionen zum Übergeben von Nachrichten | Microsoft Docs
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
ms.openlocfilehash: 9eecb7d2a45079ff14740167a192eafaab268150
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="message-passing-functions"></a>Funktionen zum Übergeben von Meldungen
Die Asynchronous Agents Library stellt mehrere Funktionen, mit denen Sie Nachrichten zwischen Komponenten übergeben.  
  
 Diese Meldungsübergabefunktionen werden mit den verschiedenen Nachrichtenblocktypen verwendet. Weitere Informationen zu den Nachrichtenblocktypen, die von der Concurrency Runtime definiert sind, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
##  <a name="top"></a> Abschnitte  
 In diesem Thema werden die folgenden Meldungsübergabefunktionen beschrieben:  
  
-   [Sende- und asend](#send)  
  
-   [empfangen und Try_receive](#receive)  
  
-   [Beispiele](#examples)  
  
##  <a name="send"></a> Sende- und asend  

 Die [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion sendet eine Nachricht synchron an das angegebene Ziel und die [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) -Funktion sendet eine Nachricht asynchron an das angegebene Ziel. Sowohl die `send` und `asend` Funktionen warten, bis das Ziel angibt, wird es schließlich akzeptieren oder ablehnen.  
  
 Die `send` Funktion wartet, bis das Ziel akzeptiert oder die Nachricht ablehnt vor dem zurückgeben. Die `send` -Funktion gibt `true` , wenn die Nachricht übermittelt wurde und `false` andernfalls. Da die `send` -Funktion synchron, funktioniert die `send` Funktion wartet, bis das Ziel zum Empfangen der Nachricht vor dem zurückgeben.  
  
 Im Gegensatz dazu die `asend` Funktion wartet nicht auf das Ziel annehmen oder Ablehnen der Nachrichteninhalts vor dem zurückgeben. Stattdessen die `asend` -Funktion gibt `true` , wenn das Ziel die Nachricht annimmt und schließlich. Andernfalls `asend` gibt `false` um anzugeben, dass das Ziel die Nachricht abgelehnt oder die Entscheidung, ob die Nachricht verschoben.  
  
 [[Nach oben](#top)]  
  
##  <a name="receive"></a> empfangen und Try_receive  

 Die [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) und [Concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive) Funktionen Lesen von Daten aus einer bestimmten Quelle stammt. Die `receive` Funktion wartet, bis Daten verfügbar sind, während die `try_receive` Funktion wird sofort zurückgegeben.  
  
 Verwenden der `receive` -Funktion, wenn Sie die Daten weiterhin benötigen. Verwenden der `try_receive` funktioniert, wenn müssen Sie den aktuellen Kontext nicht blockieren, oder Sie nicht haben die Daten um den Vorgang fortzusetzen.  
  
 [[Nach oben](#top)]  
  
##  <a name="examples"></a> Beispiele  
 Für Beispiele, in denen die `send` und `asend`, und `receive` -Funktionen finden Sie unter den folgenden Themen:  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Vorgehensweise: Implementieren verschiedener Producer-Consumer-Muster](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [Vorgehensweise: Bereitstellen von Arbeitsfunktionen für die call- und transformer-Klassen](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [Vorgehensweise: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [Vorgehensweise: Auswählen von abgeschlossenen Aufgaben](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [Vorgehensweise: Senden einer Nachricht in regelmäßigen Intervallen](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [Vorgehensweise: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 [[Nach oben](#top)]  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Send-Funktion](reference/concurrency-namespace-functions.md#send)   
 [Asend-Funktion](reference/concurrency-namespace-functions.md#asend)   
 [Receive-Funktion](reference/concurrency-namespace-functions.md#receive)   
 [Try_receive-Funktion](reference/concurrency-namespace-functions.md#try_receive)


