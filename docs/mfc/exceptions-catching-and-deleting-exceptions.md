---
title: 'Ausnahmen: Abfangen und Löschen von Ausnahmen'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 511850c3c17a4eb70529202f4b0c2b36132fc8ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173274"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Ausnahmen: Abfangen und Löschen von Ausnahmen

Die folgenden Anweisungen und Beispiele gezeigt, wie auf Ausnahmen abfangen und löschen. Weitere Informationen zu den **versuchen Sie es**, **catch**, und **auslösen** Schlüsselwörtern finden Sie unter [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).

Ihre Ausnahmehandler müssen Exception-Objekte, die sie bearbeiten, die löschen, weil sich die Ausnahme nicht löschen einen Speicherverlust verursacht, wenn dieser Code eine Ausnahme auffängt.

Ihre **catch** Block eine Ausnahme muss löschen, wenn:

- Die **catch** Block löst eine neue Ausnahme aus.

   Natürlich müssen Sie die Ausnahme nicht löschen, wenn Sie die gleiche Ausnahme erneut auslösen:

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Ausführung zurückgegeben wird, innerhalb der **catch** Block.

> [!NOTE]
>  Beim Löschen einer `CException`, verwenden die `Delete` Memberfunktion versucht, die die Ausnahme zu löschen. Verwenden Sie nicht die **löschen** -Schlüsselwort, da es möglich, wenn die Ausnahme nicht auf dem Heap ist.

#### <a name="to-catch-and-delete-exceptions"></a>Zum Abfangen und Löschen von Ausnahmen

1. Verwenden der **versuchen Sie es** Schlüsselwort zum Einrichten einer **versuchen** Block. Führen Sie alle programmanweisungen, die möglicherweise eine Ausnahme auslösen einer **versuchen** Block.

   Verwenden der **catch** Schlüsselwort zum Einrichten einer **catch** Block. Platzieren Sie Code zur Ausnahmebehandlung in einem **catch** Block. Der Code in die **catch** Block wird nur ausgeführt, wenn der Code innerhalb der **versuchen Sie es** Block eine Ausnahme des Typs im angegebenen die **catch** Anweisung.

   Das folgende Gerüst zeigt wie **versuchen** und **catch** Blöcke normalerweise angeordnet sind:

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   Wenn eine Ausnahme ausgelöst wird, wird die Steuerung auf das erste **catch** blockieren, deren Exception-Deklaration mit dem Typ der Ausnahme übereinstimmt. Sie können verschiedene Arten von Ausnahmen, die mit sequenziellen selektiv behandeln **catch** blockiert wird, wie im folgenden aufgeführt:

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Weitere Informationen finden Sie unter [Ausnahmen: Umwandeln von MFC-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)
