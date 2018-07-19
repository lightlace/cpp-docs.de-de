---
title: 'Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Nachrichtenblocks | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa70cf40851815ff92f01405d47015afd2e3e444
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694676"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Nachrichtenblocks
In diesem Dokument wird beschrieben, wie ein benutzerdefinierter Nachrichtenblocktyp erstellt wird, um eingehende Nachrichten nach Priorität zu sortieren.  
  
 Obwohl die integrierten Nachrichtenblocktypen eine breite Palette von Funktionen bereitstellen, können Sie auch eigene Nachrichtenblocktypen erstellen und anpassen, um die Anforderungen Ihrer Anwendung zu erfüllen. Eine Beschreibung der integrierten Nachrichtenblocktypen, die von der Asynchronous Agents Library bereitgestellt werden, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Lesen Sie die folgenden Dokumente, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)  
  
##  <a name="top"></a> Abschnitte  
 Diese exemplarische Vorgehensweise enthält folgende Abschnitte:  
  
- [Entwerfen eines benutzerdefinierten Nachrichtenblocks](#design)  
  
- [Definieren der Priority_buffer-Klasse](#class)  
  
- [Vollständiges Beispiel](#complete)  
  
##  <a name="design"></a> Entwerfen eines benutzerdefinierten Nachrichtenblocks  
 Nachrichtenblöcke sind am Senden und Empfangen von Nachrichten beteiligt. Ein Nachrichtenblock, der Nachrichten sendet, wird als bezeichnet eine *Quellblock*. Ein Nachrichtenblock, der Nachrichten empfängt, wird als bezeichnet eine *Zielblock*. Ein Nachrichtenblock, der sowohl sendet und Nachrichten empfängt wird als bezeichnet eine *Weitergabeblock*. Die Agents Library verwendet die abstrakte Klasse [Concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) zum Darstellen von Quellblöcke und der abstrakten Klasse [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) um Zielblöcke darzustellen. Nachrichtenblocktypen, die als Quelle dienen, werden von der `ISource`-Klasse abgeleitet, während Nachrichtenblocktypen, die als Ziel dienen, von der `ITarget`-Klasse abgeleitet werden.  
  
 Der Nachrichtenblocktyp kann prinzipiell unmittelbar von `ISource` und `ITarget` abgeleitet werden. Die Agents Library definiert jedoch drei Basisklassen, deren Funktionalität weitestgehend der aller Nachrichtenblocktypen entspricht. Beispiel: parallelitätssicheres Behandeln von Fehlern und parallelitätssicheres Verbinden von Nachrichtenblöcken. Die [Concurrency:: source_block](../../parallel/concrt/reference/source-block-class.md) Klasse leitet sich von `ISource` und sendet Nachrichten an andere Blöcke. Die [Concurrency:: target_block](../../parallel/concrt/reference/target-block-class.md) Klasse leitet sich von `ITarget` und empfängt Nachrichten von anderen Blöcken. Die [Concurrency:: propagator_block](../../parallel/concrt/reference/propagator-block-class.md) Klasse abgeleitet `ISource` und `ITarget` und sendet Nachrichten an andere Blöcke und empfängt Nachrichten von anderen Blöcken. Es wird empfohlen, Infrastrukturdetails mit diesen drei Basisklassen zu behandeln, sodass Sie sich auf das Verhalten des Nachrichtenblocks konzentrieren können.  
  
 Die Klassen `source_block`, `target_block` und `propagator_block` sind Vorlagen, die auf der Grundlage eines Typs parametrisiert werden, der die Verbindungen oder Links zwischen Quell- und Zielblöcken verwaltet, sowie auf Grundlage eines Typs, der die Verarbeitung von Nachrichten verwaltet. Die Agents Library definiert zwei Typen, die linkverwaltung [Concurrency:: single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) und [Concurrency:: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). Die `single_link_registry`-Klasse ermöglicht das Verknüpfen eines Nachrichtenblocks mit einer Quelle oder einem Ziel. Die `multi_link_registry`-Klasse ermöglicht das Verknüpfen eines Nachrichtenblocks mit mehreren Quellen oder mehreren Zielen. Die Agents Library definiert eine Klasse, die Verwaltung von Nachrichten [Concurrency:: ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). Die `ordered_message_processor`-Klasse ermöglicht Nachrichtenblöcken die Verarbeitung von Nachrichten in der Reihenfolge ihres Empfangs.  
  
 Im folgenden Beispiel wird die Beziehung zwischen Nachrichtenblöcken sowie Quellen und Zielen veranschaulicht. Dieses Beispiel zeigt die Deklaration der [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) Klasse.  
  
 [!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]  
  
 Die `transformer`-Klasse wird von `propagator_block` abgeleitet und fungiert daher als Quell- sowie als Zielblock. Sie akzeptiert Nachrichten vom Typ `_Input` und sendet Nachrichten vom Typ `_Output`. Die `transformer`-Klasse gibt `single_link_registry` als Link-Manager für alle Zielblöcke und `multi_link_registry` als Link-Manager für alle Quellblöcke an. Aus diesem Grund kann ein `transformer`-Objekt ein Ziel sowie eine unbegrenzte Anzahl von Quellen haben.  
  

 Eine Klasse, die abgeleitet `source_block` muss sechs Methoden implementieren: [Propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [Accept_message](reference/source-block-class.md#accept_message), [Reserve_message](reference/source-block-class.md#reserve_message), [ Consume_message](reference/source-block-class.md#consume_message), [Release_message](reference/source-block-class.md#release_message), und [Resume_propagation](reference/source-block-class.md#resume_propagation). Eine Klasse, die abgeleitet `target_block` implementieren müssen die [Propagate_message](reference/propagator-block-class.md#propagate_message) Methode und kann optional implementieren die [Send_message](reference/propagator-block-class.md#send_message) Methode. Ableitungen von `propagator_block` sowie von `source_block` und `target_block` sind funktional äquivalent.  


  
 Die `propagate_to_any_targets`-Methode wird von der Laufzeit aufgerufen, um alle eingehenden Nachrichten synchron oder asynchron zu verarbeiten und alle ausgehenden Nachrichten weiterzugeben. Die `accept_message`-Methode wird von Zielblöcken aufgerufen, um Nachrichten zu akzeptieren. Viele Nachrichtenblocktypen wie `unbounded_buffer` senden Nachrichten nur an das erste Ziel, das diese empfangen würde. Daher wird der Besitz der Nachricht auf das Ziel übertragen. Andere Nachrichtenblocktypen wie z. B. [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), bieten Nachrichten für alle entsprechenden Zielblöcke. `overwrite_buffer` erstellt daher eine Kopie der Nachricht für alle diesbezüglichen Ziele.  
  
 Mit den Methoden `reserve_message`, `consume_message`, `release_message` und `resume_propagation` können Nachrichtenblöcke an der Reservierung von Nachrichten teilnehmen. Zielblöcke rufen die `reserve_message`-Methode auf, wenn eine Nachricht für sie bereitgestellt wird, die zur späteren Verwendung reserviert werden muss. Nach dem Reservieren einer Nachricht durch den Zielblock kann dieser die `consume_message`-Methode aufrufen, um die Nachricht zu verarbeiten, oder die `release_message`-Methode, um die Reservierung abzubrechen. Analog zur `accept_message`-Methode kann die Implementierung von `consume_message` den Besitz der Nachricht übertragen oder eine Kopie der Nachricht zurückgeben. Nachdem eine reservierte Nachricht von einem Zielblock verarbeitet oder freigegeben wurde, wird die `resume_propagation`-Methode von der Laufzeit aufgerufen. Diese Methode setzt die Nachrichtenweitergabe i. d. R. mit der nächsten Nachricht in der Warteschlange fort.  
  
 Die `propagate_message`-Methode wird von der Laufzeit aufgerufen, um eine Nachricht asynchron von einem anderen Block zum aktuellen zu übertragen. Die `send_message`-Methode ähnelt der `propagate_message`-Methode, sendet die Nachrichten im Unterschied zu dieser jedoch synchron an die Zielblöcke. Die Standardimplementierung von `send_message` weist alle eingehenden Nachrichten zurück. Die Laufzeit ruft keine der Methoden auf, wenn von der Nachricht nicht die optionale Filterfunktion übergeben wird, die dem Zielblock zugeordnet ist. Weitere Informationen zu Nachrichtenfilter, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 [[Nach oben](#top)]  
  
##  <a name="class"></a> Definieren der Priority_buffer-Klasse  
 Die `priority_buffer`-Klasse ist ein benutzerdefinierter Nachrichtenblocktyp, der eingehende Meldungen zunächst nach der Priorität und anschließend nach der Reihenfolge ihres Empfangs sortiert. Die `priority_buffer` -Klasse ähnelt der [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) Klasse, da sie eine Warteschlange mit Nachrichten enthält und auch daran, dass es als Quelle und als Zielnachrichtenblock fungiert und mehreren Quellen und mehrere aufweisen Ziele. `unbounded_buffer` legt als Kriterium für die Weitergabe von Nachrichten jedoch nur die Reihenfolge ihres Empfangs aus den Quellen zugrunde.  
  
 Die `priority_buffer` -Klasse empfängt Nachrichten vom Typ std::[Tupel](../../standard-library/tuple-class.md) enthalten `PriorityType` und `Type` Elemente. `PriorityType` verweist auf den Typ, der die Priorität einer Nachricht angibt; `Type` verweist auf den Datenteil der Nachricht. Die `priority_buffer`-Klasse sendet Nachrichten vom Typ `Type`. Die `priority_buffer` -Klasse verwaltet auch zwei Nachrichtenwarteschlangen: ein [Std:: priority_queue](../../standard-library/priority-queue-class.md) -Objekt für eingehende Nachrichten und eine std::[Warteschlange](../../standard-library/queue-class.md) Objekt für ausgehende Nachrichten. Das Sortieren von Nachrichten nach der Priorität ist hilfreich, wenn ein `priority_buffer`-Objekt mehrere Nachrichten gleichzeitig oder bevor diese von Consumern gelesen werden empfängt.  
  
 Zusätzlich zu den sieben Methoden, die von einer Klasse implementiert werden müssen, die von `propagator_block` abgeleitet wird, überschreibt die `priority_buffer`-Klasse die noch die `link_target_notification`-Methode und die `send_message`-Methode. Die `priority_buffer`-Klasse definiert außerdem zwei öffentliche Hilfsmethoden (, `enqueue` und `dequeue`) sowie eine private Hilfsmethode ( `propagate_priority_order`).  
  
 Im folgenden Verfahren wird beschrieben, wie die `priority_buffer`-Klasse implementiert wird.  
  
#### <a name="to-define-the-prioritybuffer-class"></a>So definieren Sie die priority_buffer-Klasse  
  
1.  Erstellen Sie eine C++-Header-Datei, und nennen Sie sie `priority_buffer.h`. Sie können auch eine bestehende Headerdatei verwenden, die Teil Ihres Projekts ist.  
  
2.  In `priority_buffer.h`, fügen Sie den folgenden Code hinzu.  
  
 [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]  
  
3.  In der `std` -Namespace definieren spezialisierungen von [Std:: less](../../standard-library/less-struct.md) und [Std:: Greater](../../standard-library/greater-struct.md) , fungieren, auf die Concurrency::[Nachricht](../../parallel/concrt/reference/message-class.md) Objekte.  
  
 [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]  
  
     Die `priority_buffer`-Klasse speichert `message`-Objekte in einem `priority_queue`-Objekt. Mit diesen Typspezialisierungen können die Nachrichten von der Prioritätswarteschlange anhand ihrer Priorität sortiert werden. Die Priorität ist das erste Element des `tuple`-Objekts.  
  
4.  Deklarieren Sie die `concurrencyex`-Klasse im `priority_buffer`-Namespace.  
  
 [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]  
  
     Die `priority_buffer`-Klasse wird von `propagator_block` abgeleitet. Sie kann daher Meldungen senden und empfangen. Die `priority_buffer`-Klasse mehrere Ziele aufweisen, die Nachrichten vom Typ `Type` empfangen. Sie kann außerdem mehrere Quellen aufweisen, die Nachrichten vom Typ `tuple<PriorityType, Type>` senden.  
  
5.  Fügen Sie im `private`-Abschnitt der `priority_buffer`-Klasse die folgenden Membervariablen hinzu.  
  
 [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]  
  
     Das `priority_queue`-Objekt enthält eingehende Nachrichten, das `queue`-Objekt enthält ausgehende Nachrichten. Ein `priority_buffer`-Objekt kann mehrere Nachrichten gleichzeitig empfangen. Das `critical_section`-Objekt synchronisiert den Zugriff auf die Warteschlange für eingehende Nachrichten.  
  
6.  Definieren Sie den Kopierkonstruktor und den Zuweisungsoperator im Abschnitt `private`. Dadurch wird verhindert, dass `priority_queue`-Objekte zugewiesen werden können.  
  
 [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]  
  
7.  Definieren Sie im `public`-Abschnitt die Konstruktoren, die in zahlreichen Nachrichtenblocktypen verwendet werden. Definieren Sie auch den Destruktor.  
  
 [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]  
  
8.  Definieren Sie im `public`-Abschnitt die `enqueue`-Methode und die `dequeue`-Methode. Diese Hilfsmethoden bieten eine alternative Möglichkeit, Nachrichten an ein `priority_buffer`-Objekt zu senden und von diesem zu empfangen.  
  
 [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]  
  
9. Definieren Sie die `protected`-Methode im `propagate_to_any_targets`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]  
  
     Die `propagate_to_any_targets`-Methode überträgt die Nachricht, die sich in der Eingabewarteschlange an erster Stelle befindet, an die Ausgabewarteschlange, und gibt alle Nachrichten an die Ausgabewarteschlange weiter.  
  
10. Definieren Sie die `protected`-Methode im `accept_message`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]  
  
     Wenn die `accept_message`-Methode von einem Zielblock aufgerufen wird, wird der Besitz der Nachricht von der `priority_buffer`-Klasse auf den ersten Zielblock übertragen, der diesen akzeptiert. (Dieses Verhalten ist vergleichbar mit `unbounded_buffer`).  
  
11. Definieren Sie die `protected`-Methode im `reserve_message`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]  
  
     Die `priority_buffer`-Klasse ermöglicht einem Zielblock, eine Nachricht zu reservieren, wenn der Bezeichner der bereitgestellten Nachricht mit dem Bezeichner der Nachricht übereinstimmt, die an erster Position in der Warteschlange steht. Anders ausgedrückt kann die Nachricht von einem Ziel reserviert werden, wenn vom `priority_buffer`-Objekt noch keine weitere Nachricht empfangen und die aktuelle Nachricht noch nicht weitergegeben wurde.  
  
12. Definieren Sie die `protected`-Methode im `consume_message`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]  
  
     Die `consume_message`-Methode wird von einem Zielblock aufgerufen, um den Besitz der reservierten Methode zu übertragen.  
  
13. Definieren Sie die `protected`-Methode im `release_message`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]  
  
     Die `release_message`-Methode wird von einem Zielblock aufgerufen, um die Reservierung einer Nachricht abzubrechen.  
  
14. Definieren Sie die `protected`-Methode im `resume_propagation`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]  
  
     Nachdem eine reservierte Nachricht von einem Zielblock verarbeitet oder freigegeben wurde, wird die `resume_propagation`-Methode von der Laufzeit aufgerufen. Diese Methode gibt alle Nachrichten weiter, die sich in der Ausgabewarteschlange befinden.  
  
15. Definieren Sie die `protected`-Methode im `link_target_notification`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]  
  
     Die Membervariable `_M_pReservedFor` wird von der Basisklasse `source_block` definiert. Diese Membervariable zeigt ggf. auf den Zielblock mit der Reservierung für die Nachricht, die sich an erster Stelle in der Warteschlange befindet. `link_target_notification` wird von der Laufzeit aufgerufen, wenn ein neues Ziel mit dem `priority_buffer`-Objekt verknüpft wird. Diese Methode gibt alle Nachrichten in der Ausgabewarteschlange weiter, wenn kein Ziel eine Reservierung aufweist.  
  
16. Definieren Sie die `private`-Methode im `propagate_priority_order`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]  
  
     Diese Methode gibt alle Nachrichten von der Ausgabewarteschlange weiter. Jede Nachricht in der Warteschlange wird für alle Zielblöcke bereitgestellt, bis einer der Zielblöcke die Meldung akzeptiert. Die `priority_buffer`-Klasse behält die Reihenfolge der ausgehenden Nachrichten bei. Daher muss die erste Nachricht in der Ausgabewarteschlange von einem Zielblock akzeptiert werden, bevor eine andere Meldung von dieser Methode für die Zielblöcke bereitgestellt wird.  
  
17. Definieren Sie die `protected`-Methode im `propagate_message`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]  
  
     Die `propagate_message`-Methode ermöglicht der `priority_buffer`-Klasse als Nachrichtenempfänger oder -ziel fungieren. Diese Methode empfängt die vom angegebenen Quellblock bereitgestellte Nachricht und fügt sie in die Prioritätswarteschlange ein. Anschließend werden alle Ausgabenachrichten von der `propagate_message`-Methode asynchron an die Zielblöcke gesendet.  
  

     Diese Methode wird von der Laufzeit aufgerufen, beim Aufrufen der [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) Funktion oder wenn der Nachrichtenblock mit anderen Nachrichtenblocks verbunden wird.  

  
18. Definieren Sie die `protected`-Methode im `send_message`-Abschnitt.  
  
 [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]  
  
     Die `send_message`-Methode ähnelt der `propagate_message`-Methode. Im Unterschied zu dieser sendet sie die Ausgabemeldungen jedoch synchron.  
  

     Die Common Language Runtime ruft diese Methode während eines synchronen Sendevorgangs, z. B. beim Aufrufen der [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion.  
  
 Die `priority_buffer`-Klasse enthält Konstruktorüberladungen, die in vielen Nachrichtenblocktypen verwendet werden. Einige Konstruktorüberladungen akzeptieren [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) oder [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekte, mit denen der Nachrichtenblock von einem bestimmten Aufgabenplaner verwaltet werden kann. Andere Konstruktorüberladungen übernehmen eine Filterfunktion. Filterfunktionen ermöglichen Nachrichtenblöcken das Annehmen oder Ablehnen von Nachrichten anhand der Nutzlast. Weitere Informationen zu Nachrichtenfilter, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md). Weitere Informationen zum Aufgabenplaner finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 Da die `priority_buffer` -Klasse ordnet die Nachrichten nach Priorität, und klicken Sie dann durch die Reihenfolge, in der Nachrichten empfangen werden, diese Klasse eignet sich am besten Wenn Nachrichten asynchron ausgeführt wird, z. B. beim Aufrufen der [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend)-Funktion oder wenn der Nachrichtenblock mit anderen Nachrichtenblocks verbunden wird.  
  
 [[Nach oben](#top)]  
  
##  <a name="complete"></a> Vollständiges Beispiel  
 Im folgenden Beispiel wird die vollständige Definition der `priority_buffer`-Klasse veranschaulicht.  
  
 [!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]  
  
 Im folgende Beispiel wird eine Reihe von `asend` und [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) Vorgänge für eine `priority_buffer` Objekt.  

  
 [!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
```Output  
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36  
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24  
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12  
```  
  
 Die `priority_buffer`-Klasse ordnet die Nachrichten zunächst nach der Priorität und anschließend nach der Reihenfolge ihres Empfangs. In diesem Beispiel werden Nachrichten mit höherer numerischer Priorität am Anfang der Warteschlange eingefügt.  
  
 [[Nach oben](#top)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie die Definition des der `priority_buffer` Klasse in einer Datei mit dem Namen `priority_buffer.h` und das Testprogramm in einer Datei mit dem Namen `priority_buffer.cpp` und führen Sie dann den folgenden Befehl an einer Visual Studio Im Eingabeaufforderungsfenster.  
  
 **CL.exe/EHsc / priority_buffer.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime Exemplarische Vorgehensweisen](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)
