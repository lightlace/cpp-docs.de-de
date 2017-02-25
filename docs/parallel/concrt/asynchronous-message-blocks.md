---
title: "Asynchrone Nachrichtenbl&#246;cke | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Nicht gieriger Join [Concurrency Runtime]"
  - "Asynchrone Nachrichtenblöcke"
  - "Gieriger Join [Concurrency Runtime]"
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# Asynchrone Nachrichtenbl&#246;cke
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Agents Library stellt mehrere Nachrichtenblocktypen bereit, mit deren Hilfe Nachrichten threadsicher zwischen Anwendungskomponenten weitergegeben werden können. Diese Nachrichtenblocktypen werden häufig mit den verschiedenen Nachrichtenübergaberoutinen wie z. B. [Concurrency:: Send](../Topic/send%20Function.md), [Concurrency:: asend](../Topic/asend%20Function.md), [Concurrency:: Receive](../Topic/receive%20Function.md), und [Concurrency:: try_receive](../Topic/try_receive%20Function.md). Weitere Informationen zu den Nachrichtenübergaberoutinen, die von der Agents Library definiert sind, finden Sie unter [Message Passing Functions](../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> Abschnitte  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Quellen und Ziele](#sources_and_targets)  
  
- [Nachrichtenweitergabe](#propagation)  
  
- [Übersicht über Nachrichtenblocktypen](#overview)  
  
- [Unbounded_buffer-Klasse](#unbounded_buffer)  
  
- [Overwrite_buffer-Klasse](#overwrite_buffer)  
  
- [Single_assignment-Klasse](#single_assignment)  
  
- [Call-Klasse](#call)  
  
- [Transformer-Klasse](#transformer)  
  
- [Choice-Klasse](#choice)  
  
- [Join- und Multitype_join-Klasse](#join)  
  
- [Timer-Klasse](#timer)  
  
- [Filtern von Nachrichten](#filtering)  
  
- [Nachrichtenreservierung](#reservation)  
  
##  <a name="a-namesourcesandtargetsa-sources-and-targets"></a><a name="sources_and_targets"></a> Quellen und Ziele  
 Quelle und Ziel sind zwei wichtige Beteiligte bei der Nachrichtenübergabe. Ein *Quelle* ein Kommunikationsendpunkt, der Nachrichten sendet. Ein *Ziel* ein Kommunikationsendpunkt, der Nachrichten empfängt. Sie können sich eine Quelle als Endpunkt vorstellen, von dem gelesen wird, und ein Ziel als Endpunkt, in den geschrieben wird. Anwendungen verbinden Quellen und Ziele Formular *-Netzwerken*.  
  
 Die Agents Library verwendet zwei abstrakte Klassen zur Darstellung von Quellen und Ziele: [Concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) und [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md). Nachrichtenblocktypen, die als Quelle dienen, werden von der `ISource`-Klasse abgeleitet, während Nachrichtenblocktypen, die als Ziel dienen, von der `ITarget`-Klasse abgeleitet werden. Nachrichtenblocktypen, die als Quelle und Ziel dienen, werden von der `ISource`-Klasse und der `ITarget`-Klasse abgeleitet.  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namepropagationa-message-propagation"></a><a name="propagation"></a> Nachrichtenweitergabe  
 *Die Weitergabe* ist das Senden einer Nachricht von einer Komponente zu einem anderen. Wenn eine Nachricht für einen Nachrichtenblock bereitgestellt wird, kann er diese Nachricht akzeptieren, ablehnen oder verschieben. Jeder Nachrichtenblocktyp speichert und überträgt Nachrichten auf unterschiedliche Weise. Beispielsweise speichert die `unbounded_buffer`-Klasse eine unendliche Anzahl von Nachrichten, die `overwrite_buffer`-Klasse speichert jeweils nur eine Nachricht, und die Transformatorklasse speichert eine geänderte Version jeder Nachricht. Diese Nachrichtenblocktypen werden im Folgenden ausführlicher beschrieben.  
  
 Wenn ein Nachrichtenblock eine Meldung akzeptiert, können optionale Arbeiten durchgeführt werden, und wenn es sich bei dem Nachrichtenblock um eine Quelle handelt, kann die resultierende Nachricht an einen anderen Member im Netzwerk weitergegeben werden. Mithilfe einer Filterfunktion können Nachrichtenblöcke einzelne Nachrichten ablehnen, die nicht empfangen werden sollen. Filter werden ausführlich weiter unten in diesem Thema im Abschnitt [Nachrichtenfilter](#filtering). Ein Nachrichtenblock, der eine Meldung verschiebt, kann sie reservieren und später verarbeiten. Reservierung von Nachrichten wird weiter unten in diesem Thema im Abschnitt ausführlicher beschrieben [Nachrichtenreservierung](#reservation).  
  
 Mit der Agents Library können Nachrichten von Nachrichtenblöcken synchron oder asynchron übergeben werden. Wenn Sie eine Nachricht synchron an einen Nachrichtenblock übergeben, z. B. mit der `send`-Funktion, wird der aktuelle Kontext von der Laufzeit blockiert, bis die Nachricht vom Zielblock akzeptiert oder abgelehnt wird. Wenn Sie eine Nachricht asynchron an einen Nachrichtenblock übergeben, z. B. mit der `asend`-Funktion, wird die Nachricht von der Laufzeit für das Ziel bereitgestellt, und wenn die Nachricht vom Ziel akzeptiert wird, wird von der Laufzeit eine asynchrone Aufgabe geplant, um die Nachricht an den Empfänger weiterzugeben. Die Laufzeit verwendet einfache Aufgaben, um Nachrichten auf kooperative Weise weiterzugeben. Weitere Informationen zu einfachen Aufgaben finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 Anwendungen verbinden Quellen und Ziele, und bilden so Messagingnetzwerke. Normalerweise verknüpfen Sie das Netzwerk, und rufen `send` oder `asend` auf, um Daten an das Netzwerk zu übergeben. Um einen Quellnachrichtenblock mit einem Ziel zu verknüpfen, rufen die [Concurrency::ISource::link_target](../Topic/ISource::link_target%20Method.md) Methode. Um ein Ziel Quellnachrichtenblocks, rufen Sie die [Concurrency::ISource::unlink_target](../Topic/ISource::unlink_target%20Method.md) Methode. Um ein Quellblock von allen Zielen zu trennen, rufen Sie die [Concurrency::ISource::unlink_targets](../Topic/ISource::unlink_targets%20Method.md) Methode. Wenn sich einer der vordefinierten Nachrichtenblocktypen nicht mehr im Bereich befindet oder zerstört wird, werden die Verknüpfungen mit den Zielblöcken automatisch aufgehoben. Bei einigen Nachrichtenblocktypen ist die maximale Anzahl der Ziele eingeschränkt, in die geschrieben werden kann. Im folgenden Abschnitt werden die Einschränkungen beschrieben, die für die vordefinierten Nachrichtenblocktypen gelten.  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameoverviewa-overview-of-message-block-types"></a><a name="overview"></a> Übersicht über Nachrichtenblocktypen  
 In der folgenden Tabelle wird die Rolle der wichtigen Nachrichtenblocktypen kurz beschrieben.  
  
 [unbounded_buffer](#unbounded_buffer)  
 Speichert eine Nachrichtenwarteschlange.  
  
 [overwrite_buffer](#overwrite_buffer)  
 Speichert eine Nachricht, die mehrmals geschrieben und gelesen werden kann.  
  
 [single_assignment](#single_assignment)  
 Speichert eine Nachricht, die ein Mal geschrieben und gelesen werden kann.  
  
 [Rufen Sie](#call)  
 Führt beim Empfang einer Nachricht Arbeiten aus.  
  
 [Transformer](#transformer)  
 Führt Arbeiten aus, wenn Daten empfangen werden, und sendet das Ergebnis dieser Arbeiten an einen anderen Zielblock. Die `transformer`-Klasse kann für unterschiedliche Eingabe- und Ausgabetypen verwendet werden.  
  
 [Auswahl](#choice)  
 Wählt aus einer Gruppe Quellen die erste verfügbare Nachricht aus.  
  
 [Join und multitype join](#join)  
 Warten, bis alle Nachrichten, die von einer Gruppe Quellen empfangen werden sollen, empfangen wurden, und setzen die Nachrichten zu einer Nachricht für einen anderen Nachrichtenblock zusammen.  
  
 [Zeitgeber](#timer)  
 Sendet eine Nachricht in regelmäßigen Intervallen an einen Zielblock.  
  
 Diese Nachrichtenblocktypen haben unterschiedliche Eigenschaften, sodass sie für unterschiedliche Situationen nützlich sind. Zu diesen Eigenschaften zählen folgende:  
  
- *Weitergabetyp*: Gibt an, ob der Nachrichtenblock als Datenquelle, als Datenempfänger oder beides dient.  
  
- *Die Nachrichtenreihenfolge*: Gibt an, ob die Nachrichtenblock die ursprüngliche Reihenfolge beibehält, in dem Nachrichten gesendet oder empfangen werden. Vordefinierte Nachrichtenblocktypen behalten die ursprüngliche Reihenfolge bei, in der Nachrichten gesendet oder empfangen werden.  
  
- *Quellenanzahl*: die maximale Anzahl von Quellen, die der Nachrichtenblock lesen kann.  
  
- *Zielanzahl*: die maximale Anzahl von Zielen, die der Nachrichtenblock schreiben kann.  
  
 In der folgenden Tabelle wird der Bezug dieser Eigenschaften auf die verschiedenen Nachrichtenblocktypen beschrieben.  
  
|Nachrichtenblocktyp|Weitergabetyp (Quelle, Ziel oder beides)|Nachrichtenreihenfolge (sortiert oder nicht sortiert)|Quellenanzahl|Zielanzahl|  
|------------------------|--------------------------------------------------|-----------------------------------------------|------------------|------------------|  
|`unbounded_buffer`|Beides|Testreihe|Unbegrenzt|Unbegrenzt|  
|`overwrite_buffer`|Beides|Testreihe|Unbegrenzt|Unbegrenzt|  
|`single_assignment`|Beides|Testreihe|Unbegrenzt|Unbegrenzt|  
|`call`|Ziel|Testreihe|Unbegrenzt|Nicht zutreffend|  
|`transformer`|Beides|Testreihe|Unbegrenzt|1|  
|`choice`|Beides|Testreihe|10|1|  
|`join`|Beides|Testreihe|Unbegrenzt|1|  
|`multitype_join`|Beides|Testreihe|10|1|  
|`timer`|Quelle|Nicht zutreffend|Nicht zutreffend|1|  
  
 In den folgenden Abschnitten werden die Nachrichtenblocktypen ausführlicher beschrieben.  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameunboundedbuffera-unboundedbuffer-class"></a><a name="unbounded_buffer"></a> Unbounded_buffer-Klasse  
 Die [Concurrency:: unbounded_buffer](../Topic/unbounded_buffer%20Class.md) -Klasse stellt eine allgemeine Struktur des asynchronen messaging dar. Diese Klasse speichert eine FIFO-Nachrichtenwarteschlange (First In, First Out), in die mehrere Quellen Nachrichten schreiben oder aus der mehrere Ziele Nachrichten auslesen können. Wenn ein Ziel eine Nachricht von einem `unbounded_buffer`-Objekt empfängt, wird diese Nachricht aus der Nachrichtenwarteschlange entfernt. Daher können die einzelnen Nachrichten nur von einem Ziel empfangen werden, obwohl ein `unbounded_buffer`-Objekt mehrere Ziele haben kann. Die `unbounded_buffer`-Klasse ist hilfreich, wenn Sie mehrere Nachrichten an eine andere Komponente übergeben möchten und diese Komponente alle Nachrichten empfangen muss.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `unbounded_buffer`-Klasse veranschaulicht. In diesem Beispiel werden drei Werte an ein `unbounded_buffer`-Objekt gesendet und wieder von diesem Objekt zurückgegeben.  
  
 [!CODE [concrt-unbounded_buffer-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-unbounded_buffer-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
334455  
```  
  
 Ein vollständiges Beispiel, das zeigt, wie Sie die `unbounded_buffer` Klasse, finden Sie unter [Gewusst wie: Implementieren verschiedener Producer-Consumer-Muster](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nameoverwritebuffera-overwritebuffer-class"></a><a name="overwrite_buffer"></a> Overwrite_buffer-Klasse  
 Die [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) -Klasse ähnelt der `unbounded_buffer` Klasse, außer dass ein `overwrite_buffer` -Objekt nur eine Nachricht speichert. Wenn ein Ziel eine Nachricht von einem `overwrite_buffer`-Objekt empfängt, wird diese Nachricht darüber hinaus auch nicht aus dem Puffer entfernt. Daher empfangen mehrere Ziele eine Kopie der Nachricht.  
  
 Die `overwrite_buffer`-Klasse ist hilfreich, wenn Sie mehrere Nachrichten an eine andere Komponente übergeben möchten, diese Komponente jedoch nur den letzten Wert benötigt. Diese Klasse ist darüber hinaus auch hilfreich, wenn Sie eine Nachricht an mehreren Komponenten übertragen möchten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `overwrite_buffer`-Klasse veranschaulicht. In diesem Beispiel werden drei Werte an ein `overwrite _buffer`-Objekt gesendet, und der aktuelle Wert wird dreimal aus dem gleichen Objekt gelesen. Dieses Beispiel ähnelt dem Beispiel für die `unbounded_buffer`-Klasse. Allerdings speichert die `overwrite_buffer`-Klasse nur eine Nachricht. Darüber hinaus wird die Nachricht von der Laufzeit nicht aus einem `overwrite_buffer`-Objekt entfernt, nachdem sie gelesen wurde.  
  
 [!CODE [concrt-overwrite_buffer-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-overwrite_buffer-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
555555  
```  
  
 Ein vollständiges Beispiel, das zeigt, wie Sie die `overwrite_buffer` Klasse, finden Sie unter [Gewusst wie: Implementieren verschiedener Producer-Consumer-Muster](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namesingleassignmenta-singleassignment-class"></a><a name="single_assignment"></a> Single_assignment-Klasse  
 Die [Concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) -Klasse ähnelt der `overwrite_buffer` Klasse, außer dass ein `single_assignment` -Objekt nur einmal geschrieben werden kann. Wenn ein Ziel eine Nachricht von einem `overwrite_buffer`-Objekt empfängt, wird diese Nachricht wie bei der `single_assignment`-Klasse nicht aus diesem Objekt entfernt. Daher empfangen mehrere Ziele eine Kopie der Nachricht. Die `single_assignment`-Klasse ist hilfreich, wenn Sie eine Nachricht an mehrere Komponenten übertragen möchten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `single_assignment`-Klasse veranschaulicht. In diesem Beispiel werden drei Werte an ein `single_assignment`-Objekt gesendet, und der aktuelle Wert wird dreimal aus dem gleichen Objekt gelesen. Dieses Beispiel ähnelt dem Beispiel für die `overwrite_buffer`-Klasse. Die `overwrite_buffer`-Klasse und die `single_assignment`-Klasse speichern jeweils eine einzelne Nachricht, in die `single_assignment`-Klasse kann jedoch nur einmal geschrieben werden.  
  
 [!CODE [concrt-single_assignment-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-single_assignment-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
333333  
```  
  
 Ein vollständiges Beispiel, das zeigt, wie Sie die `single_assignment` Klasse, finden Sie unter [Exemplarische Vorgehensweise: Implementieren von Futures](../../parallel/concrt/walkthrough-implementing-futures.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namecalla-call-class"></a><a name="call"></a> Call-Klasse  
 Die [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) -Klasse dient als Nachrichtenempfänger, der beim Empfang von Daten eine Arbeitsfunktion ausführt. Bei dieser Arbeitsfunktion kann es sich um einen Lambdaausdruck, ein Funktionsobjekt oder einen Funktionszeiger handeln. Ein `call`-Objekt verhält sich anders als ein gewöhnlicher Funktionsaufruf, da es parallel zu anderen Komponenten agiert, die Nachrichten an das Objekt senden. Wenn ein `call`-Objekt beim Empfang einer Nachricht Arbeiten ausführt, fügt es die empfangene Nachricht einer Warteschlange hinzu. Jedes `call`-Objekt verarbeitet Nachrichten in der Warteschlange in der Reihenfolge, in der sie empfangen werden.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `call`-Klasse veranschaulicht. In diesem Beispiel wird ein `call`-Objekt erstellt, das jeden empfangenen Wert an der Konsole ausgibt. Anschließend werden im Beispiel drei Werte an das `call`-Objekt gesendet. Da die `call` -Objekt verarbeitet Nachrichten in einem separaten Thread, in diesem Beispiel verwendet auch eine Zählervariable und ein [Ereignis](../../parallel/concrt/reference/event-class.md) Objekt, um sicherzustellen, dass die `call` -Objekt verarbeitet alle Nachrichten, bevor die `wmain` -Funktion zurückgegeben wird.  
  
 [!CODE [concrt-call-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-call-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
334455  
```  
  
 Ein vollständiges Beispiel, das zeigt, wie Sie die `call` Klasse, finden Sie unter [Gewusst wie: Bereitstellen von Arbeitsfunktionen für die Call- und Transformer-Klassen](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nametransformera-transformer-class"></a><a name="transformer"></a> Transformer-Klasse  
 Die [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) -Klasse dient sowohl als Nachrichtenempfänger als auch als Nachrichtensender. Die `transformer`-Klasse ist gleicht der `call`-Klasse, da sie beim Empfang von Daten eine benutzerdefinierte Arbeitsfunktion ausführt. Die `transformer`-Klasse sendet jedoch auch das Ergebnis der Arbeitsfunktion an Empfängerobjekte. Wie ein `call`-Objekt agiert ein `transformer`-Objekt parallel zu anderen Komponenten, die Nachrichten an das Objekt senden. Wenn ein `transformer`-Objekt beim Empfang einer Nachricht Arbeiten ausführt, fügt es die empfangene Nachricht einer Warteschlange hinzu. Jedes `transformer`-Objekt verarbeitet die eigenen Nachrichten in der Warteschlange in der Reihenfolge, in der sie empfangen werden.  
  
 Die `transformer`-Klasse sendet die eigene Nachricht an ein Ziel. Wenn Sie festlegen, den `_PTarget` -Parameter im Konstruktor auf `NULL`, können Sie das Ziel später angeben, durch Aufrufen der [Concurrency:: link_target](../Topic/source_block::link_target%20Method.md) Methode.  
  
 Im Gegensatz zu allen anderen asynchronen Nachrichtenblocktypen, die von der Agents Library bereitgestellt werden, kann die `transformer`-Klasse für unterschiedliche Eingabe- und Ausgabetypen verwendet werden. Aufgrund dieser Fähigkeit, Daten von einem Typ in einen anderen transformieren zu können, ist die `transformer`-Klasse in vielen parallelen Netzwerken eine wichtige Komponente. Zudem können Sie differenziertere Parallelitätsfunktionen in die Arbeitsfunktion eines `transformer`-Objekts integrieren.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `transformer`-Klasse veranschaulicht. In diesem Beispiel wird ein `transformer`-Objekt erstellt, mit dem jeder `int`-Eingabewert mit 0.33 multipliziert wird, um einen `double`-Wert als Ausgabe zu generieren. Anschließend werden im Beispiel transformierten Werte vom selben `transformer`-Objekt empfangen und an der Konsole ausgegeben.  
  
 [!CODE [concrt-transformer-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-transformer-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
10.8914.5218.15  
```  
  
 Ein vollständiges Beispiel, das zeigt, wie Sie die `transformer` Klasse, finden Sie unter [Gewusst wie: Verwenden von Transformer in einer Datenpipeline](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namechoicea-choice-class"></a><a name="choice"></a> Choice-Klasse  
 Die [Choice](../../parallel/concrt/reference/choice-class.md) -Klasse wählt die erste verfügbare Nachricht aus einer Gruppe von Quellen. Die `choice` -Klasse stellt eine Datenflussmechanismus, sondern einen Ablaufsteuerungsmechanismus dar (das Thema [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) beschreibt die Unterschiede zwischen Datenfluss und ablaufsteuerung).  
  
 Der Lesevorgang bei einem choice-Objekt gleicht dem Aufruf der API-Funktion `WaitForMultipleObjects` von Windows, wenn der `bWaitAll`-Parameter auf `FALSE` festgelegt ist. Die `choice`-Klasse bindet Daten jedoch nicht an ein externes Synchronisierungsobjekt, sondern an das Ereignis selbst.  
  
 Normalerweise verwenden Sie die `choice` -Klasse zusammen mit der [Concurrency:: Receive](../Topic/receive%20Function.md) Funktion, um die ablaufsteuerung in Ihrer Anwendung zu fördern. Verwenden Sie die `choice`-Klasse, wenn Sie unter Nachrichtenpuffern auswählen müssen, die andere Typen aufweisen. Verwenden Sie die `single_assignment`-Klasse, wenn Sie unter Nachrichtenpuffern auswählen müssen, die denselben Typ aufweisen.  
  
 Es ist wichtig, in welcher Reihenfolge Quellen mit einem `choice`-Objekt verknüpft werden, da die Reihenfolge bestimmen kann, welche Nachricht ausgewählt wird. Stellen Sie sich beispielsweise den Fall vor, dass mehrere Nachrichtenpuffer, die bereits eine Nachricht enthalten, mit einem `choice`-Objekt verknüpft werden. Das `choice`-Objekt wählt die Nachricht aus der ersten Quelle aus, mit der es verknüpft wird. Nach der Verknüpfung aller Quellen behält das `choice`-Objekt die Reihenfolge, in der die einzelnen Quellen eine Nachricht empfangen, bei.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `choice`-Klasse veranschaulicht. Dieses Beispiel verwendet die [make_choice](../Topic/make_choice%20Function.md) -Funktion zum Erstellen einer `choice` -Objekt, das den drei Nachrichtenblöcken. Anschließend werden im Beispiel verschiedene Fibonacci-Zahlen berechnet, und jedes Ergebnis wird in einem anderen Nachrichtenblock gespeichert. Im Beispiel wird dann in der Konsole eine Meldung angezeigt, die auf dem Vorgang basiert, der zuerst beendet wurde.  
  
 [!CODE [concrt-choice-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-choice-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
fib35 received its value first. Result = 9227465  
```  
  
 Da die Aufgabe zur der 35<sup>te</sup> Fibonacci-Zahl nicht unbedingt als erste abgeschlossen, kann die Ausgabe diese Beispiels variieren.  
  
 Dieses Beispiel verwendet die [Concurrency:: parallel_invoke](../Topic/parallel_invoke%20Function.md) -Algorithmus die Fibonacci-Zahlen parallel berechnet. Weitere Informationen zu `parallel_invoke`, finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
 Ein vollständiges Beispiel, das zeigt, wie Sie die `choice` Klasse, finden Sie unter [How to: Select Among Completed Tasks](../../parallel/concrt/how-to-select-among-completed-tasks.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namejoina-join-and-multitypejoin-classes"></a><a name="join"></a> Join- und Multitype_join-Klasse  
 Die [Concurrency:: Join](../../parallel/concrt/reference/join-class.md) und [multitype_join](../../parallel/concrt/reference/multitype-join-class.md) Klassen können für jedes Mitglied einer Gruppe von Quellen eine Nachricht empfangen hat. Die `join`-Klasse wird für Quellobjekte verwendet, die einen allgemeinen Nachrichtentyp aufweisen. Die `multitype_join`-Klasse wird für Quellobjekte verwendet, die andere Nachrichtentypen aufweisen können.  
  
 Der Lesevorgang bei einem `join` oder einem `multitype_join`-Objekt ähnelt dem Aufrufen der API-Funktion `WaitForMultipleObjects` von Windows, wenn der `bWaitAll`-Parameter auf `TRUE` festgelegt ist. Ähnlich wie ein `choice`-Objekt verwenden das `join`- und das  `multitype_join`-Objekt einen Ereignismechanismus, der Daten nicht an ein externes Synchronisierungsobjekt, sondern an das Ereignis selbst bindet.  
  
 Lesen aus einem `join` Objekt erzeugt eine std::[Vektor](vector%20Class.md) Objekt. Lesen aus einem `multitype_join` Objekt erzeugt eine std::[Tupel](../../standard-library/tuple-class.md) Objekt. Elemente treten in diesen Objekten in der Reihenfolge auf, in der die entsprechenden Quellpuffer mit dem `join`-Objekt oder mit dem `multitype_join`-Objekt verknüpft werden. Da die Reihenfolge, in der Quellpuffer mit einem `join`-Objekt oder einem `multitype_join`-Objekt verknüpft werden, von der Reihenfolge der Elemente im resultierenden `vector`-Objekt oder `tuple`-Objekt abhängig ist, wird empfohlen, die Verknüpfung zwischen einem vorhandenen Quellpuffer und einem Join nicht aufzuheben. Andernfalls ist das daraus folgende Verhalten möglicherweise undefiniert.  
  
### <a name="greedy-versus-non-greedy-joins"></a>Gierige und nicht gierige Joins  
 Die `join`-Klasse und die `multitype_join`-Klasse unterstützen das Konzept gieriger und nicht gieriger Joins. Ein *gierigen Join* von allen zugehörigen Quellen eine Nachricht akzeptiert, wenn Nachrichten verfügbar werden, bis alle Nachrichten verfügbar sind. Ein *nicht gierigen Joins* Nachrichten in zwei Phasen empfangen. Zunächst wartet ein nicht gieriger Join, bis eine Nachricht aus eine der Quelle bereitgestellt wird. Nachdem alle Quellmeldungen verfügbar sind, versucht ein nicht gieriger Join dann, diese Nachrichten zu reservieren. Wenn alle Nachrichten reserviert werden können, werden die einzelnen Nachrichten verarbeitet und an das Ziel weitergegeben. Wenn dies nicht der Fall ist, werden die Nachrichtenreservierungen freigegeben oder abgebrochen und es wird gewartet, bis die einzelnen Quellen eine Nachricht empfangen.  
  
 Gierige Joins erzielen im Vergleich zu nicht gierigen Joins eine bessere Leistung, da sie Nachrichten sofort empfangen. In seltenen Fällen können gierige Joins jedoch zu Deadlocks führen. Verwenden Sie einen nicht gierigen Join, wenn Sie mehrere Joins haben, die ein oder mehrere gemeinsame Quellobjekte enthalten.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `join`-Klasse veranschaulicht. Dieses Beispiel verwendet die [Concurrency:: make_join](../Topic/make_join%20Function.md) -Funktion zum Erstellen einer `join` -Objekt, das aus drei empfängt `single_assignment` Objekte. In diesem Beispiel werden verschiedene Fibonacci-Zahlen berechnet, das jeweilige Ergebnis wird in einem eigenen `single_assignment`-Objekt gespeichert, und die einzelnen Ergebnisse im `join`-Objekt werden an der Konsole ausgegeben. Dieses Beispiel ähnelt dem Beispiel für die `choice`-Klasse; im Unterschied dazu wartet die `join`-Klasse jedoch, bis alle Nachrichtenblöcke eine Nachricht empfangen haben.  
  
 [!CODE [concrt-join-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-join-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008  
```  
  
 Dieses Beispiel verwendet die [Concurrency:: parallel_invoke](../Topic/parallel_invoke%20Function.md) -Algorithmus die Fibonacci-Zahlen parallel berechnet. Weitere Informationen zu `parallel_invoke`, finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
 Vollständige Beispiele, die zeigen, wie Sie für die `join` Klasse, finden Sie unter [How to: Select Among Completed Tasks](../../parallel/concrt/how-to-select-among-completed-tasks.md) und [Exemplarische Vorgehensweise: Verhindern von Deadlocks mit Join](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-nametimera-timer-class"></a><a name="timer"></a> Timer-Klasse  
 Die Concurrency::[Timer-Klasse](../../parallel/concrt/reference/timer-class.md) fungiert als Nachrichtenquelle. Ein `timer`-Objekt sendet nach Ablauf einer angegebenen Zeitdauer eine Nachricht an ein Ziel. Die `timer`-Klasse ist hilfreich, wenn der Versand einer Nachricht verzögert werden muss oder wenn eine Nachricht in regelmäßigen Intervallen gesendet werden muss.  
  
 Die `timer`-Klasse sendet die eigene Nachricht an nur ein Ziel. Wenn Sie festlegen, den `_PTarget` -Parameter im Konstruktor auf `NULL`, können Sie das Ziel später angeben, durch Aufrufen der [Concurrency::ISource::link_target](../Topic/source_block::link_target%20Method.md) Methode.  
  
 Ein `timer`-Objekt kann ein sich wiederholendes oder ein sich nicht wiederholendes Objekt sein. Um ein sich wiederholendes timer-Objekt zu erstellen, übergeben Sie beim Aufruf des Konstruktors für den `true`-Parameter das `_Repeating`-Argument. Andernfalls übergeben Sie für den `false`-Parameter das `_Repeating`-Argument, um ein sich nicht wiederholendes timer-Objekt zu erstellen. Wenn das timer-Objekt ein sich wiederholendes Objekt ist, wird dieselbe Nachricht nach jedem Intervall an das entsprechende Ziel gesendet.  
  
 Die Agents Library erstellt `timer`-Objekte im nicht gestarteten Zustand. Um ein Timer-Objekt zu starten, rufen die [Concurrency::timer::start](../Topic/timer::start%20Method.md) Methode. So beenden Sie ein `timer` Objekt, das Objekt zerstört oder Aufruf der [Concurrency::timer::stop](../Topic/timer::stop%20Method.md) Methode. Um einen sich wiederholenden Timer anzuhalten, rufen Sie die [Concurrency::timer::pause](../Topic/timer::pause%20Method.md) Methode.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die grundlegende Struktur für die Verwendung der `timer`-Klasse veranschaulicht. Im Beispiel wird mit dem `timer`-Objekt und dem `call`-Objekt der Status eines längeren Vorgangs angegeben.  
  
 [!CODE [concrt-timer-structure#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-timer-structure#1)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe:  
  
```Output  
Computing fib(42)..................................................result is 267914296  
```  
  
 Ein vollständiges Beispiel, das zeigt, wie Sie die `timer` Klasse, finden Sie unter [Gewusst wie: Senden einer Nachricht in regelmäßigen Intervallen](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namefilteringa-message-filtering"></a><a name="filtering"></a> Filtern von Nachrichten  
 Wenn Sie ein Nachrichtenblockobjekt erstellen, können Sie angeben einer *filter-Funktion* die bestimmt, ob die Nachrichtenblock Meldung akzeptiert oder eine zurückweist. Eine Filterfunktion ist eine hilfreiche Möglichkeit, um sicherzustellen, dass nur bestimmte Werte von einem Nachrichtenblock empfangen werden.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein `unbounded_buffer`-Objekt erstellt wird, das eine Filterfunktion verwendet, um nur gerade Zahlen zu akzeptieren. Ungerade Zahlen werden vom `unbounded_buffer`-Objekt zurückgewiesen, sodass ungerade Zahlen nicht an die Zielblöcke weitergegeben werden.  
  
 [!CODE [concrt-filter-function#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-filter-function#1)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```Output  
0 2 4 6 8  
```  
  
 Eine Filterfunktion kann eine Lambda-Funktion, ein Funktionsobjekt oder ein Funktionszeiger sein. Jede Filterfunktion nimmt eines der folgenden Formate an.  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 Um das unnötige Kopieren von Daten zu vermeiden, verwenden Sie das zweite Format bei einem aggregierten Typ, der anhand des Werts weitergegeben wird.  
  
 Nachrichtenfilterung unterstützt das *Datenfluss* Programmiermodell, in dem Komponenten beim Empfang von Daten Berechnungen. Beispiele mit Filterfunktionen zum Steuern des Datenflusses in einem Netzwerk der Nachricht übergeben, finden Sie unter [Gewusst wie: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md), [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agents](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md), und [Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="a-namereservationa-message-reservation"></a><a name="reservation"></a> Nachrichtenreservierung  
 *Nachrichtenreservierung* ermöglicht ein Nachrichtenblock eine Nachricht für die spätere Verwendung zu reservieren. In aller Regel wird die Nachrichtenreservierung nicht direkt verwendet. Kenntnisse der Nachrichtenreservierung helfen Ihnen jedoch möglicherweise, das Verhalten vordefinierter Nachrichtenblocktypen besser zu verstehen.  
  
 Beispiel: gierige und nicht gierige Joins. Beide Jointypen verwenden die Nachrichtenreservierung, um Meldungen für die spätere Verwendung zu reservieren. Wie bereits beschrieben, werden Nachrichten bei nicht gierigen Joins in zwei Phasen empfangen. In der ersten Phase wartet ein nicht gieriges `join`-Objekt, bis von den einzelnen Quellen eine Nachricht empfangen wurde. Ein nicht gieriger Join versucht anschließend, jede dieser Nachrichten zu reservieren. Wenn alle Nachrichten reserviert werden können, werden die einzelnen Nachrichten verarbeitet und an das Ziel weitergegeben. Wenn dies nicht der Fall ist, werden die Nachrichtenreservierungen freigegeben oder abgebrochen und es wird gewartet, bis die einzelnen Quellen eine Nachricht empfangen.  
  
 Bei einem gierigen Join, der auch Eingabenachrichten aus einer Reihe von Quellen liest, werden mithilfe der Nachrichtenreservierung weitere Nachrichten gelesen, während darauf gewartet wird, dass eine Nachricht von jeder Quelle empfangen wird. Angenommen, ein gieriger Join empfängt Nachrichten vom Nachrichtenblock `A` und vom Nachrichtenblock `B`. Wenn der gierige Join zwei Nachrichten von B empfängt, jedoch noch keine Nachrichten von `A` erhalten hat, wird die eindeutige Nachrichten-ID für die zweite Nachrichten von `B` vom gierigen Join gespeichert. Nachdem der gierige Join eine Meldung von `A` empfangen hat und diese Nachrichten weitergibt, wird anhand dieser Nachrichten-ID ermittelt, ob die zweite Nachricht von `B` weiterhin verfügbar ist.  
  
 Sie können die Nachrichtenreservierung verwenden, wenn Sie eigene Nachrichtenblocktypen implementieren. Ein Beispiel dazu, wie einen benutzerdefinierter Nachrichtenblocktyp erstellen, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Nachrichtenblocks](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md).  
  
 [[Nach oben](#top)]  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)

