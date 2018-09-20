---
title: 'Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Nachrichtenblocks | Microsoft-Dokumentation'
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
ms.openlocfilehash: f9391d99f75bdb5ac2191a65e525ce989aefcd6b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421283"
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

Nachrichtenblöcke sind am Senden und Empfangen von Nachrichten beteiligt. Ein Nachrichtenblock, der Nachrichten sendet, wird als bezeichnet ein *Quellblock*. Ein Nachrichtenblock, der Nachrichten empfängt, wird als bezeichnet ein *Zielblock*. Ein Nachrichtenblock, der sowohl Nachrichten sendet und empfängt, wird als bezeichnet ein *Weitergabeblock*. Die Agents Library verwendet die abstrakte Klasse [Concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) zur Darstellung von Quellblöcke und der abstrakten Klasse [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) um Zielblöcke darzustellen. Nachrichtenblocktypen, die als Quelle dienen, werden von der `ISource`-Klasse abgeleitet, während Nachrichtenblocktypen, die als Ziel dienen, von der `ITarget`-Klasse abgeleitet werden.

Der Nachrichtenblocktyp kann prinzipiell unmittelbar von `ISource` und `ITarget` abgeleitet werden. Die Agents Library definiert jedoch drei Basisklassen, deren Funktionalität weitestgehend der aller Nachrichtenblocktypen entspricht. Beispiel: parallelitätssicheres Behandeln von Fehlern und parallelitätssicheres Verbinden von Nachrichtenblöcken. Die [Concurrency:: source_block](../../parallel/concrt/reference/source-block-class.md) Klasse leitet sich von `ISource` und sendet Nachrichten an andere Blöcke. Die [Concurrency:: target_block](../../parallel/concrt/reference/target-block-class.md) Klasse leitet sich von `ITarget` und empfängt Nachrichten von anderen Blöcken. Die [Concurrency:: propagator_block](../../parallel/concrt/reference/propagator-block-class.md) Klasse leitet sich von `ISource` und `ITarget` und sendet Nachrichten an andere Blöcke und empfängt Nachrichten von anderen Blöcken. Es wird empfohlen, Infrastrukturdetails mit diesen drei Basisklassen zu behandeln, sodass Sie sich auf das Verhalten des Nachrichtenblocks konzentrieren können.

Die Klassen `source_block`, `target_block` und `propagator_block` sind Vorlagen, die auf der Grundlage eines Typs parametrisiert werden, der die Verbindungen oder Links zwischen Quell- und Zielblöcken verwaltet, sowie auf Grundlage eines Typs, der die Verarbeitung von Nachrichten verwaltet. Die Agents Library definiert zwei Typen, die linkverwaltung [Concurrency:: single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) und [Concurrency:: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). Die `single_link_registry`-Klasse ermöglicht das Verknüpfen eines Nachrichtenblocks mit einer Quelle oder einem Ziel. Die `multi_link_registry`-Klasse ermöglicht das Verknüpfen eines Nachrichtenblocks mit mehreren Quellen oder mehreren Zielen. Die Agents Library definiert eine Klasse, die Verwaltung von Nachrichten [Concurrency:: ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). Die `ordered_message_processor`-Klasse ermöglicht Nachrichtenblöcken die Verarbeitung von Nachrichten in der Reihenfolge ihres Empfangs.

Im folgenden Beispiel wird die Beziehung zwischen Nachrichtenblöcken sowie Quellen und Zielen veranschaulicht. Dieses Beispiel zeigt die Deklaration der [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) Klasse.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

Die `transformer`-Klasse wird von `propagator_block` abgeleitet und fungiert daher als Quell- sowie als Zielblock. Sie akzeptiert Nachrichten vom Typ `_Input` und sendet Nachrichten vom Typ `_Output`. Die `transformer`-Klasse gibt `single_link_registry` als Link-Manager für alle Zielblöcke und `multi_link_registry` als Link-Manager für alle Quellblöcke an. Aus diesem Grund kann ein `transformer`-Objekt ein Ziel sowie eine unbegrenzte Anzahl von Quellen haben.

Eine abgeleitete Klasse `source_block` muss sechs Methoden implementieren: [Propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [Accept_message](reference/source-block-class.md#accept_message), [Reserve_message](reference/source-block-class.md#reserve_message), [ Consume_message](reference/source-block-class.md#consume_message), [Release_message](reference/source-block-class.md#release_message), und [Resume_propagation](reference/source-block-class.md#resume_propagation). Eine abgeleitete Klasse `target_block` müssen implementieren die [Propagate_message](reference/propagator-block-class.md#propagate_message) Methode implementieren und kann die [Send_message](reference/propagator-block-class.md#send_message) Methode. Ableitungen von `propagator_block` sowie von `source_block` und `target_block` sind funktional äquivalent.

Die `propagate_to_any_targets`-Methode wird von der Laufzeit aufgerufen, um alle eingehenden Nachrichten synchron oder asynchron zu verarbeiten und alle ausgehenden Nachrichten weiterzugeben. Die `accept_message`-Methode wird von Zielblöcken aufgerufen, um Nachrichten zu akzeptieren. Viele Nachrichtenblocktypen wie `unbounded_buffer` senden Nachrichten nur an das erste Ziel, das diese empfangen würde. Daher wird der Besitz der Nachricht auf das Ziel übertragen. Andere Nachrichtenblocktypen wie z. B. [Concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), bieten Nachrichten für alle entsprechenden Zielblöcke. `overwrite_buffer` erstellt daher eine Kopie der Nachricht für alle diesbezüglichen Ziele.

Mit den Methoden `reserve_message`, `consume_message`, `release_message` und `resume_propagation` können Nachrichtenblöcke an der Reservierung von Nachrichten teilnehmen. Zielblöcke rufen die `reserve_message`-Methode auf, wenn eine Nachricht für sie bereitgestellt wird, die zur späteren Verwendung reserviert werden muss. Nach dem Reservieren einer Nachricht durch den Zielblock kann dieser die `consume_message`-Methode aufrufen, um die Nachricht zu verarbeiten, oder die `release_message`-Methode, um die Reservierung abzubrechen. Analog zur `accept_message`-Methode kann die Implementierung von `consume_message` den Besitz der Nachricht übertragen oder eine Kopie der Nachricht zurückgeben. Nachdem eine reservierte Nachricht von einem Zielblock verarbeitet oder freigegeben wurde, wird die `resume_propagation`-Methode von der Laufzeit aufgerufen. Diese Methode setzt die Nachrichtenweitergabe i. d. R. mit der nächsten Nachricht in der Warteschlange fort.

Die `propagate_message`-Methode wird von der Laufzeit aufgerufen, um eine Nachricht asynchron von einem anderen Block zum aktuellen zu übertragen. Die `send_message`-Methode ähnelt der `propagate_message`-Methode, sendet die Nachrichten im Unterschied zu dieser jedoch synchron an die Zielblöcke. Die Standardimplementierung von `send_message` weist alle eingehenden Nachrichten zurück. Die Laufzeit ruft keine der Methoden auf, wenn von der Nachricht nicht die optionale Filterfunktion übergeben wird, die dem Zielblock zugeordnet ist. Weitere Informationen zu Nachrichtenfiltern finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).

[[Nach oben](#top)]

##  <a name="class"></a> Definieren der Priority_buffer-Klasse

Die `priority_buffer`-Klasse ist ein benutzerdefinierter Nachrichtenblocktyp, der eingehende Meldungen zunächst nach der Priorität und anschließend nach der Reihenfolge ihres Empfangs sortiert. Die `priority_buffer` -Klasse ähnelt der [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) Klasse, da es sich um eine Warteschlange Nachrichten enthält und auch daran, dass sie sowohl eine Quelle als auch als Zielnachrichtenblock fungiert und können mehrere Quellen sowie mehrere Ziele. `unbounded_buffer` legt als Kriterium für die Weitergabe von Nachrichten jedoch nur die Reihenfolge ihres Empfangs aus den Quellen zugrunde.

Die `priority_buffer` -Klasse empfängt Nachrichten vom Typ std::[Tupel](../../standard-library/tuple-class.md) enthalten `PriorityType` und `Type` Elemente. `PriorityType` verweist auf den Typ, der die Priorität einer Nachricht angibt; `Type` verweist auf den Datenteil der Nachricht. Die `priority_buffer`-Klasse sendet Nachrichten vom Typ `Type`. Die `priority_buffer` Klasse verwaltet auch zwei Nachrichtenwarteschlangen: ein [Std:: priority_queue](../../standard-library/priority-queue-class.md) Objekt für eingehende Nachrichten und eine std::[Warteschlange](../../standard-library/queue-class.md) Objekt für ausgehende Nachrichten. Das Sortieren von Nachrichten nach der Priorität ist hilfreich, wenn ein `priority_buffer`-Objekt mehrere Nachrichten gleichzeitig oder bevor diese von Consumern gelesen werden empfängt.

Zusätzlich zu den sieben Methoden, die von einer Klasse implementiert werden müssen, die von `propagator_block` abgeleitet wird, überschreibt die `priority_buffer`-Klasse die noch die `link_target_notification`-Methode und die `send_message`-Methode. Die `priority_buffer`-Klasse definiert außerdem zwei öffentliche Hilfsmethoden (, `enqueue` und `dequeue`) sowie eine private Hilfsmethode ( `propagate_priority_order`).

Im folgenden Verfahren wird beschrieben, wie die `priority_buffer`-Klasse implementiert wird.

#### <a name="to-define-the-prioritybuffer-class"></a>So definieren Sie die priority_buffer-Klasse

1. Erstellen eine C++-Header-Datei und nennen sie `priority_buffer.h`. Sie können auch eine bestehende Headerdatei verwenden, die Teil Ihres Projekts ist.

1. In `priority_buffer.h`, fügen Sie den folgenden Code hinzu.

[!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. In der `std` -Namespace definiert spezialisierungen von [Std:: less](../../standard-library/less-struct.md) und [Std:: Greater](../../standard-library/greater-struct.md) , fungieren, in der Concurrency::[Nachricht](../../parallel/concrt/reference/message-class.md) Objekte.

[!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

     The `priority_buffer` class stores `message` objects in a `priority_queue` object. These type specializations enable the priority queue to sort messages according to their priority. The priority is the first element of the `tuple` object.

1. Deklarieren Sie die `concurrencyex`-Klasse im `priority_buffer`-Namespace.

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

     The `priority_buffer` class derives from `propagator_block`. Therefore, it can both send and receive messages. The `priority_buffer` class can have multiple targets that receive messages of type `Type`. It can also have multiple sources that send messages of type `tuple<PriorityType, Type>`.

1. Fügen Sie im `private`-Abschnitt der `priority_buffer`-Klasse die folgenden Membervariablen hinzu.

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

     The `priority_queue` object holds incoming messages; the `queue` object holds outgoing messages. A `priority_buffer` object can receive multiple messages simultaneously; the `critical_section` object synchronizes access to the queue of input messages.

1. Definieren Sie den Kopierkonstruktor und den Zuweisungsoperator im Abschnitt `private`. Dadurch wird verhindert, dass `priority_queue`-Objekte zugewiesen werden können.

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. Definieren Sie im `public`-Abschnitt die Konstruktoren, die in zahlreichen Nachrichtenblocktypen verwendet werden. Definieren Sie auch den Destruktor.

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. Definieren Sie im `public`-Abschnitt die `enqueue`-Methode und die `dequeue`-Methode. Diese Hilfsmethoden bieten eine alternative Möglichkeit, Nachrichten an ein `priority_buffer`-Objekt zu senden und von diesem zu empfangen.

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. Definieren Sie die `protected`-Methode im `propagate_to_any_targets`-Abschnitt.

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

     The `propagate_to_any_targets` method transfers the message that is at the front of the input queue to the output queue and propagates out all messages in the output queue.

10. Definieren Sie die `protected`-Methode im `accept_message`-Abschnitt.

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

     When a target block calls the `accept_message` method, the `priority_buffer` class transfers ownership of the message to the first target block that accepts it. (This resembles the behavior of `unbounded_buffer`.)

11. Definieren Sie die `protected`-Methode im `reserve_message`-Abschnitt.

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

     The `priority_buffer` class permits a target block to reserve a message when the provided message identifier matches the identifier of the message that is at the front of the queue. In other words, a target can reserve the message if the `priority_buffer` object has not yet received an additional message and has not yet  propagated out the current one.

12. Definieren Sie die `protected`-Methode im `consume_message`-Abschnitt.

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

     A target block calls `consume_message` to transfer ownership of the message that it reserved.

13. Definieren Sie die `protected`-Methode im `release_message`-Abschnitt.

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

     A target block calls `release_message` to cancel its reservation to a message.

14. Definieren Sie die `protected`-Methode im `resume_propagation`-Abschnitt.

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

     The runtime calls `resume_propagation` after a target block either consumes or releases a reserved message. This method propagates out any messages that are in the output queue.

15. Definieren Sie die `protected`-Methode im `link_target_notification`-Abschnitt.

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

     The `_M_pReservedFor` member variable is defined by the base class, `source_block`. This member variable points to the target block, if any, that is holding a reservation to the message that is at the front of the output queue. The runtime calls `link_target_notification` when a new target is linked to the `priority_buffer` object. This method propagates out any messages that are in the output queue if no target is holding a reservation.

16. Definieren Sie die `private`-Methode im `propagate_priority_order`-Abschnitt.

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

     This method propagates out all messages from the output queue. Every message in the queue is offered to every target block until one of the target blocks accepts the message. The `priority_buffer` class preserves the order of the outgoing messages. Therefore, the first message in the output queue must be accepted by a target block before this method offers any other message to the target blocks.

17. Definieren Sie die `protected`-Methode im `propagate_message`-Abschnitt.

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

     The `propagate_message` method enables the `priority_buffer` class to act as a message receiver, or target. This method receives the message that is offered by the provided source block and inserts that message into the priority queue. The `propagate_message` method then asynchronously sends all output messages to the target blocks.

     The runtime calls this method when you call the [concurrency::asend](reference/concurrency-namespace-functions.md#asend) function or when the message block is connected to other message blocks.

18. Definieren Sie die `protected`-Methode im `send_message`-Abschnitt.

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

     The `send_message` method resembles `propagate_message`. However it sends the output messages synchronously instead of asynchronously.

     The runtime calls this method during a synchronous send operation, such as when you call the [concurrency::send](reference/concurrency-namespace-functions.md#send) function.

Die `priority_buffer`-Klasse enthält Konstruktorüberladungen, die in vielen Nachrichtenblocktypen verwendet werden. Einige Konstruktorüberladungen akzeptieren [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) oder [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Objekte, denen die Nachrichtenblock von einem bestimmten Aufgabenplaner verwaltet werden können. Andere Konstruktorüberladungen übernehmen eine Filterfunktion. Filterfunktionen ermöglichen Nachrichtenblöcken das Annehmen oder Ablehnen von Nachrichten anhand der Nutzlast. Weitere Informationen zu Nachrichtenfiltern finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md). Weitere Informationen zum Aufgabenplaner finden Sie unter [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Da die `priority_buffer` -Klasse ordnet die Nachrichten nach Priorität, und klicken Sie dann durch die Reihenfolge, in dem Nachrichten empfangen werden, diese Klasse eignet sich am besten, wenn Nachrichten asynchron, z. B. beim Aufrufen Erhalt der [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend)Funktion oder wenn die Nachrichtenblock mit anderen Nachrichtenblocks verbunden wird.

[[Nach oben](#top)]

##  <a name="complete"></a> Das vollständige Beispiel

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

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, bzw. Fügen Sie die Definition der `priority_buffer` Klasse in einer Datei mit dem Namen `priority_buffer.h` und das Testprogramm in einer Datei mit dem Namen `priority_buffer.cpp` und führen Sie dann den folgenden Befehl in einer Visual Studio Eingabeaufforderungsfenster.

**CL.exe/EHsc priority_buffer.cpp**

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)
