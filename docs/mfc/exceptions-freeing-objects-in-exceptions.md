---
title: 'Ausnahmen: Freigeben von Objekten in Ausnahmen'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], freeing objects in exceptions
- local exception handling
- memory leaks, caused by exception
- try-catch exception handling [MFC], destroying objects
- destroying objects [MFC]
- freeing objects [MFC]
- throwing exceptions [MFC], after destroying
- exception handling [MFC], destroying objects
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
ms.openlocfilehash: 6e03d46a2600458f3107efa6e0b6b0d643c9b160
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442470"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>Ausnahmen: Freigeben von Objekten in Ausnahmen

Dieser Artikel beschreibt die Notwendigkeit und die-Methode der Objekte freigeben, wenn eine Ausnahme auftritt. Folgende Themen werden behandelt:

- [Behandlung der Ausnahme lokal](#_core_handling_the_exception_locally)

- [Auslösen von Ausnahmen nach dem Zerstören von Objekten](#_core_throwing_exceptions_after_destroying_objects)

Ausnahmen ausgelöst werden, indem Sie das Framework oder Ihrer Anwendung Unterbrechung des normalen Programmablauf. Daher ist es sehr wichtig, das Schließen von Objekten nachzuverfolgen, damit Sie ordnungsgemäß entfernt können für den Fall, dass eine Ausnahme ausgelöst wird.

Es gibt zwei Hauptmethoden, um dies zu tun.

- Behandeln von Ausnahmen, die lokal mithilfe der **versuchen** und **catch** Schlüsselwörter, zerstören Sie anschließend alle Objekte mit einer Anweisung.

- Löschen Sie ein Objekt in der **catch** Block vor dem Auslösen der Ausnahme außerhalb des Blocks für die weitere Verarbeitung.

Diese beiden Ansätze werden im folgenden als Lösungen, die im folgenden Beispiel für die problematische dargestellt:

[!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

Wie oben beschrieben eingeben, `myPerson` wird nicht gelöscht werden, wenn eine Ausnahme, indem ausgelöst wird `SomeFunc`. Springt direkt an den nächsten äußeren Ausnahme-Handler, umgehen die normale Funktion beenden und den Code, der das Objekt wird gelöscht. Der Zeiger auf das Objekt den Gültigkeitsbereich verlässt, wenn die Ausnahme bewirkt, die Funktion dass, und der vom Objekt belegte Arbeitsspeicher wird nie wiederhergestellt werden, solange das Programm ausgeführt wird. Hierbei handelt es sich um einen Speicherverlust. Sie würden die Speicherdiagnose mit erkannt werden.

##  <a name="_core_handling_the_exception_locally"></a> Behandlung der Ausnahme lokal

Die **Try/Catch-** Paradigma bietet eine defensive Programmierung-Methode für die Speicherverluste zu vermeiden und sicherzustellen, dass Ihre Objekte zerstört werden, wenn Ausnahmen auftreten. Im Beispiel weiter oben in diesem Artikel vorgestellte könnte beispielsweise wie folgt umgeschrieben werden:

[!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

Dieses neue Beispiel richtet einen Ausnahmehandler, der die Ausnahme abfangen und behandeln ihn lokal aus. Klicken Sie dann die Funktion normalerweise beendet, und das Objekt zerstört wird. Der wichtigste Aspekt dieses Beispiels ist, dass ein Kontext, der die Ausnahme abfangen eingerichtet wird, mit der **Try/Catch-** Blöcke. Ohne einen Frame mit Ausnahme der lokalen, würde die Funktion nie wissen, dass eine Ausnahme ausgelöst wurde und die Möglichkeit, normal beendet, und zerstört das Objekt keine.

##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> Auslösen von Ausnahmen nach dem Zerstören von Objekten

Eine weitere Möglichkeit, Ausnahmen zu behandeln ist an den nächsten äußeren Ausnahmebehandlung-Kontext übergeben. In Ihrer **catch** blockieren, die Ihnen einige Bereinigungsschritte der lokal zugeordneten Objekte und dann auf die Ausnahme auslöst, zur weiteren Verarbeitung.

Die auslösende Funktion kann oder nicht Heap-Objekte freigeben müssen. Wenn die Funktion immer das heapobjekt vor der Rückgabe im Normalfall, Zuordnung, und klicken Sie dann die Funktion auch das heapobjekt Aufheben der Zuordnung sollte vor dem Auslösen der Ausnahme. Auf der anderen Seite, wenn die Funktion nicht normalerweise das Objekt heben die Zuordnung vor der Rückgabe im Normalfall müssen Sie auf von Fall zu Fall entscheiden, ob das heapobjekt aufgehoben werden soll.

Das folgende Beispiel zeigt, wie lokal zugewiesene Objekte können bereinigt werden:

[!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

Der Ausnahmemechanismus wird automatisch die Keyframe-Objekte; der Destruktor des Frameobjekts wird auch bezeichnet.

Wenn Sie Funktionen, die Ausnahmen auslösen kann aufrufen, können Sie **Try/Catch-** Blöcke, um sicherzustellen, dass Sie die Ausnahmen abfangen und haben die Möglichkeit, Objekte zu zerstören Sie erstellt haben. Bedenken Sie insbesondere darauf, dass viele Funktionen von MFC-Ausnahmen auslösen können.

Weitere Informationen finden Sie unter [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

