---
title: "Gewusst wie: Implementieren verschiedener Producer-Consumer-Muster"
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
  - "Producer-Consumer-Muster, Implementieren [Concurrency Runtime]"
  - "Implementieren von Producer-Consumer-Mustern [Concurrency Runtime]"
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
caps.latest.revision: 17
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Implementieren verschiedener Producer-Consumer-Muster
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird die Implementierung des Producer\-Consumer\-Musters in der Anwendung beschrieben.  Bei diesem Muster sendet der *Producer* Nachrichten an einen Nachrichtenblock, während der *Consumer* Nachrichten aus diesem Block ausliest.  
  
 In diesem Thema werden zwei Szenarien beschrieben.  Im ersten Szenario muss der Consumer alle Nachrichten empfangen, die der Producer sendet.  Im zweiten Szenario ruft der Consumer in regelmäßigen Abständen Daten ab und muss daher nicht jede Nachricht empfangen.  
  
 In beiden Beispielen in diesem Thema werden Nachrichten mithilfe von Agents, Nachrichtenblöcken und Nachrichtenübergabefunktionen vom Producer an den Consumer übertragen.  Der Producer\-Agent schreibt Nachrichten mit der [concurrency::send](../Topic/send%20Function.md)\-Funktion in ein [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md)\-Objekt.  Der Consumer\-Agent liest Nachrichten mit der [concurrency::receive](../Topic/receive%20Function.md)\-Funktion aus einem [concurrency::ISource](../../parallel/concrt/reference/isource-class.md)\-Objekt.  Beide Agents enthalten einen Sentinelwert, um das Ende der Verarbeitung zu koordinieren.  
  
 Weitere Informationen zu asynchronen Agents finden Sie unter [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md).  Weitere Informationen zu Nachrichtenblöcken und Nachrichtenübergabefunktionen finden Sie unter [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md) und unter [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md).  
  
## Beispiel  
 In diesem Beispiel sendet der Producer\-Agent eine Reihe von Zahlen an den Consumer\-Agent.  Diese werden vom Consumer empfangen und ihr Durchschnitt wird berechnet.  Anschließend wird der Durchschnitt in die Konsole geschrieben.  
  
 Bei diesem Beispiel kann der Producer mithilfe eines [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)\-Objekts Nachrichten in eine Warteschlange stellen.  Die `unbounded_buffer`\-Klasse implementiert `ITarget` und `ISource`, damit Producer und Consumer Nachrichten über einen gemeinsamen Puffer senden und empfangen können.  Die Funktionen `send` und `receive` koordinieren die Aufgabe, die Daten vom Producer an den Consumer weiterzugeben.  
  
 [!CODE [concrt-producer-consumer-average#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-producer-consumer-average#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **The average is 50.**   
## Beispiel  
 In diesem Beispiel sendet der Producer\-Agent eine Reihe von Aktienkursen an den Consumer\-Agent.  Der Consumer\-Agent liest den aktuellen Kurs in regelmäßigen Abständen und gibt ihn an der Konsole aus.  
  
 Dieses Beispiel gleicht dem vorherigen, wobei hier jedoch der Producer mithilfe eines [concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)\-Objekts eine Nachricht mit dem Consumer gemeinsam verwenden kann.  Wie im vorherigen Beispiel implementiert die `overwrite_buffer`\-Klasse `ITarget` und `ISource`, sodass Producer und Consumer einen gemeinsamen Nachrichtenpuffer nutzen können.  
  
 [!CODE [concrt-producer-consumer-quotes#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-producer-consumer-quotes#1)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
  **Current quote is 24.44.**  
**Current quote is 24.44.**  
**Current quote is 24.65.**  
**Current quote is 24.99.**  
**Current quote is 23.76.**  
**Current quote is 22.30.**  
**Current quote is 25.89.** Anders als bei einem `unbounded_buffer`\-Objekt entfernt die `receive`\-Funktion die Nachricht nicht aus dem `overwrite_buffer`\-Objekt.  Wenn der Consumer den Nachrichtenpuffer mehr als einmal ausliest, bevor der Producer diese Nachricht überschreibt, erhält der Empfänger jedes Mal dieselbe Nachricht.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `producer-consumer.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc producer\-consumer.cpp**  
  
## Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)