---
title: 'Ausnahmen: Freigeben von Objekten in Ausnahmen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21a63a55103cbefda2ba501c5609b772b2203166
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347827"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>Ausnahmen: Freigeben von Objekten in Ausnahmen
Dieser Artikel beschreibt die Notwendigkeit und die Methode zum Freigeben von Objekten aus, wenn eine Ausnahme auftritt. Folgende Themen werden behandelt:  
  
-   [Behandlung der Ausnahme lokal](#_core_handling_the_exception_locally)  
  
-   [Auslösen von Ausnahmen nach der Zerstörung von Objekten](#_core_throwing_exceptions_after_destroying_objects)  
  
 Ausnahmen, die vom Framework oder von Ihrer Anwendung Unterbrechung des normalen Programmablauf ausgelöst werden. Daher ist es sehr wichtig ist, Schließen von Objekten nachverfolgen, damit Sie ordnungsgemäß entfernt können für den Fall, dass eine Ausnahme ausgelöst wird.  
  
 Es gibt zwei primäre Methoden dazu.  
  
-   Behandeln von Ausnahmen, die lokal mithilfe der **versuchen** und **catch** Schlüsselwörter, entfernen Sie dann alle Objekte mit einer Anweisung.  
  
-   Zerstört ein Objekt in der **catch** Block vor dem Auslösen der Ausnahme außerhalb des Blocks für die weitere Verarbeitung.  
  
 Diese beiden Ansätze sind als Lösungen für die folgenden problematisch Beispiel wie folgt:  
  
 [!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]  
  
 Wie oben geschrieben `myPerson` wird nicht gelöscht werden, wenn eine Ausnahme ausgelöst wird, indem Sie `SomeFunc`. Die Ausführung springt direkt an den nächsten äußeren Ausnahmehandler, umgehen die normale Funktion beenden und den Code, der das Objekt wird gelöscht. Der Zeiger auf das Objekt den Gültigkeitsbereich verlässt, wenn die Ausnahme bewirkt, die Funktion dass und der vom Objekt belegte Arbeitsspeicher wird nicht wiederhergestellt werden, solange das Programm ausgeführt wird. Hierbei handelt es sich um einen Speicherverlust. Es wäre mithilfe der Speicherdiagnose erkannt werden.  
  
##  <a name="_core_handling_the_exception_locally"></a> Behandlung der Ausnahme lokal  
 Die **Try/Catch-** Paradigma bietet eine defensive Programmiermethode zur Vermeidung von Speicherverlusten und sicherstellen, dass die Objekte zerstört werden, wenn Ausnahmen auftreten. Im Beispiel weiter oben in diesem Artikel angezeigten könnte z. B. wie folgt umgeschrieben werden:  
  
 [!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]  
  
 Dieses neue Beispiel richtet einen Ausnahmehandler die Ausnahme abfangen und behandeln sie lokal. Klicken Sie dann die Funktion normal beendet, und das Objekt zerstört wird. Der wichtigste Aspekt dabei ist, dass ein Kontext zum Abfangen der Ausnahme mit eingerichtet ist die **Try/Catch-** blockiert. Ohne lokale Ausnahmen Frames würde die Funktion nie wissen, dass eine Ausnahme ausgelöst wurde, und die Möglichkeit, die normalerweise zu beenden und zerstören Sie das Objekt keine.  
  
##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> Auslösen von Ausnahmen nach der Zerstörung von Objekten  
 Eine weitere Möglichkeit zum Behandeln von Ausnahmen ist an den nächsten äußeren Ausnahmebehandlung Kontext übergeben. In Ihrem **catch** blockieren, können Sie einige Bereinigung Ausführen Ihrer lokal zugeordneten Objekte und lösen Sie die Ausnahme auf, für die weitere Verarbeitung.  
  
 Die auslösende Funktion kann oder keine Heap-Objekte freigeben müssen. Wenn die Funktion immer das heapobjekt vor der Rückgabe in die normale Situation freigegeben, und klicken Sie dann die Funktion auch das heapobjekt deallocate sollte vor dem Auslösen der Ausnahme. Andererseits, wenn die Funktion nicht normalerweise jedoch stattdessen das Aufheben der Zuordnung vor der Rückgabe in der Normalfall, müssen Sie auf Basis von Fall entscheiden, ob das heapobjekt freigegeben werden sollten.  
  
 Das folgende Beispiel zeigt, wie lokal zugewiesene Objekte können nicht bereinigt werden:  
  
 [!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]  
  
 Ausnahmemechanismus hebt automatisch Frame-Objekte; der Destruktor des Frameobjekts wird auch bezeichnet.  
  
 Wenn Sie Funktionen, die Ausnahmen auslösen kann aufrufen, können Sie **Try/Catch-** Blöcke, um sicherzustellen, dass die Ausnahmen abfangen und haben die Möglichkeit, Objekte zu zerstören Sie erstellt haben. Bedenken Sie insbesondere darauf, dass viele Funktionen von MFC-Ausnahmen auslösen können.  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

