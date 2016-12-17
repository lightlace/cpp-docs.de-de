---
title: "Funktionen zum &#220;bergeben von Meldungen"
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
  - "Funktionen zum Übergeben von Meldungen"
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
caps.latest.revision: 23
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionen zum &#220;bergeben von Meldungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Asynchronous Agents Library stellt mehrere Funktionen bereit, mit denen Sie Meldungen zwischen Komponenten übergeben können.  
  
 Diese Meldungsübergabefunktionen werden mit den verschiedenen Meldungsblocktypen verwendet.  Weitere Informationen zu den Meldungsblocktypen, die von der Concurrency Runtime definiert werden, finden Sie unter [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
##  <a name="top"></a> Abschnitte  
 In diesem Thema werden die folgenden Meldungsübergabefunktionen beschrieben:  
  
-   [send und asend](#send)  
  
-   [receive und try\_receive](#receive)  
  
-   [Beispiele](#examples)  
  
##  <a name="send"></a> send und asend  
 Die [concurrency::send](../Topic/send%20Function.md)\-Funktion sendet eine Meldung synchron an das angegebene Ziel und die [concurrency::asend](../Topic/asend%20Function.md)\-Funktion sendet eine Meldung asynchron an das angegebene Ziel.  Die Funktionen `asend` und die Funktion `send` warten, bis das Ziel angibt, dass es eine schließlich Meldung akzeptiert oder ablehnt wird.  
  
 Die `send`\-Funktion wartet, bis das Ziel die Meldung akzeptiert oder ablehnt, bevor eine Rückgabe erfolgt.  Die `send`\-Funktion gibt `true` zurück, wenn die Meldung zugestellt wurde, andernfalls gibt sie `false` zurück.  Da die `send`\-Funktion synchron funktioniert, wartet die `send`\-Funktion, bis das Ziel die Meldung empfängt, bevor eine Rückgabe erfolgt.  
  
 Die `asend`\-Funktion wartet hingegen nicht, bis das Ziel die Meldung akzeptiert oder abgelehnt hat, bevor eine Rückgabe erfolgt.  Die `asend`\-Funktion gibt stattdessen `true` zurück, wenn das Ziel die Meldung schließlich akzeptiert.  Andernfalls gibt `asend` `false` zurück, um anzugeben, dass das Ziel die Meldung entweder abgelehnt hat oder die Entscheidung, ob die Meldung angenommen wird, aufgeschoben hat.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="receive"></a> receive und try\_receive  
 Die Funktionen [concurrency::receive](../Topic/receive%20Function.md) und [concurrency::try\_receive](../Topic/try_receive%20Function.md) lesen Daten aus einer angegebenen Quelle.  Die `receive`\-Funktion wartet, bis die Daten verfügbar sind, wohingegen die `try_receive`\-Funktion sofort eine Rückgabe liefert.  
  
 Verwenden Sie die `receive`\-Funktion, wenn Sie die Daten benötigen, um fortfahren zu können.  Verwenden Sie die `try_receive`\-Funktion, wenn Sie den aktuellen Kontext nicht blockieren dürfen oder die Daten nicht benötigen, um fortfahren zu können.  
  
 \[[Nach oben](#top)\]  
  
##  <a name="examples"></a> Beispiele  
 Beispiele für die Verwendung der Funktionen `send`, `asend` und `receive` finden Sie in den folgenden Themen:  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Gewusst wie: Implementieren verschiedener Producer\-Consumer\-Muster](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [Gewusst wie: Bereitstellen von Arbeitsfunktionen für die call\- und transformer\-Klassen](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [Gewusst wie: Verwenden von transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [Gewusst wie: Auswählen von abgeschlossenen Aufgaben](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [Gewusst wie: Senden einer Nachricht in regelmäßigen Intervallen](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [Gewusst wie: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 \[[Nach oben](#top)\]  
  
## Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send\-Funktion](../Topic/send%20Function.md)   
 [asend\-Funktion](../Topic/asend%20Function.md)   
 [receive\-Funktion](../Topic/receive%20Function.md)   
 [try\_receive\-Funktion](../Topic/try_receive%20Function.md)