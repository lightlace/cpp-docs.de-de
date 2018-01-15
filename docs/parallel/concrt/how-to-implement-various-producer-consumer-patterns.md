---
title: 'Vorgehensweise: Implementieren verschiedener Producer-Consumer-Muster | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0efafe17cd524c241e709d3c3c59233a130cdf95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>Gewusst wie: Implementieren verschiedener Producer-Consumer-Muster
In diesem Thema wird die Implementierung des Producer-Consumer-Musters in der Anwendung beschrieben. Bei diesem Muster sendet der *Producer* Nachrichten an einen Nachrichtenblock, während der *Consumer* Nachrichten aus diesem Block ausliest.  
  
 In diesem Thema werden zwei Szenarien beschrieben. Im ersten Szenario muss der Consumer alle Nachrichten empfangen, die der Producer sendet. Im zweiten Szenario ruft der Consumer in regelmäßigen Abständen Daten ab und muss daher nicht jede Nachricht empfangen.  
  
 In beiden Beispielen in diesem Thema werden Nachrichten mithilfe von Agents, Nachrichtenblöcken und Nachrichtenübergabefunktionen vom Producer an den Consumer übertragen. Der Producer-Agent verwendet die [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion zum Schreiben von Nachrichten an eine [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) Objekt. Der Consumer-Agent verwendet die [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) Funktion zum Lesen von Nachrichten ein [Concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) Objekt. Beide Agents enthalten einen Sentinelwert, um das Ende der Verarbeitung zu koordinieren.  
  
 Weitere Informationen zu asynchronen Agents finden Sie unter [asynchrone Agents](../../parallel/concrt/asynchronous-agents.md). Weitere Informationen zu der Meldungsblöcke und Meldungsübergabefunktionen, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md) und [Message Passing Functions](../../parallel/concrt/message-passing-functions.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel sendet der Producer-Agent eine Reihe von Zahlen an den Consumer-Agent. Diese werden vom Consumer empfangen und ihr Durchschnitt wird berechnet. Anschließend wird der Durchschnitt in die Konsole geschrieben.  
  
 Dieses Beispiel verwendet eine [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) Objekt, das der Producer Nachrichten in eine Warteschlange zu aktivieren. Die `unbounded_buffer`-Klasse implementiert `ITarget` und `ISource`, damit Producer und Consumer Nachrichten über einen gemeinsamen Puffer senden und empfangen können. Die Funktionen `send` und `receive` koordinieren die Aufgabe, die Daten vom Producer an den Consumer weiterzugeben.  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
The average is 50.  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel sendet der Producer-Agent eine Reihe von Aktienkursen an den Consumer-Agent. Der Consumer-Agent liest den aktuellen Kurs in regelmäßigen Abständen und gibt ihn an der Konsole aus.  
  
 Dieses Beispiel ähnelt der vorherigen Ansicht identisch, jedoch verwendet eine [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) Objekt, das Aktivieren der Producer eine Nachricht mit dem Consumer gemeinsam nutzen. Wie im vorherigen Beispiel implementiert die `overwrite_buffer`-Klasse `ITarget` und `ISource`, sodass Producer und Consumer einen gemeinsamen Nachrichtenpuffer nutzen können.  
  
 [!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
```Output  
Current quote is 24.44.  
Current quote is 24.44.  
Current quote is 24.65.  
Current quote is 24.99.  
Current quote is 23.76.  
Current quote is 22.30.  
Current quote is 25.89.  
```  
  
 Anders als bei einem `unbounded_buffer`-Objekt entfernt die `receive`-Funktion die Nachricht nicht aus dem `overwrite_buffer`-Objekt. Wenn der Consumer den Nachrichtenpuffer mehr als einmal ausliest, bevor der Producer diese Nachricht überschreibt, erhält der Empfänger jedes Mal dieselbe Nachricht.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `producer-consumer.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / Producer-consumer.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)
