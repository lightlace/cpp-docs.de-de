---
title: 'Ausnahmen: Abfangen und Löschen von Ausnahmen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3527dabab96fe8f2832430f928a922941178ea97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Ausnahmen: Abfangen und Löschen von Ausnahmen
Die folgenden Anweisungen und Beispiele zeigen, wie auf Ausnahmen abfangen und löschen. Weitere Informationen zu den **versuchen**, **catch**, und `throw` Schlüsselwörter finden Sie unter [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).  
  
 Fehler beim Löschen der Ausnahme einen Speicherverlust verursacht, wenn der Code eine Ausnahme abgefangen, müssen Ihre Ausnahmehandler Ausnahmeobjekte, die sie behandeln möchten, die löschen.  
  
 Ihre **catch** Block eine Ausnahme muss löschen, wenn:  
  
-   Die **catch** Block löst eine neue Ausnahme aus.  
  
     Natürlich müssen Sie die Ausnahme nicht löschen, wenn Sie die gleiche Ausnahme erneut auslösen:  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   Ausführung zurückgegeben wird, innerhalb der **catch** Block.  
  
> [!NOTE]
>  Beim Löschen einer `CException`, verwenden die **löschen** Memberfunktion zum Löschen der Ausnahme. Verwenden Sie nicht die **löschen** -Schlüsselwort, da es auftreten kann, wenn die Ausnahme nicht auf dem Heap befindet.  
  
#### <a name="to-catch-and-delete-exceptions"></a>Abfangen und Löschen von Ausnahmen  
  
1.  Verwenden der **versuchen** Schlüsselwort zum Einrichten einer **versuchen** Block. Führen Sie alle programmanweisungen, die eine Ausnahme auslösen könnte eine **versuchen** Block.  
  
     Verwenden der **catch** Schlüsselwort zum Einrichten einer **catch** Block. Platzieren Sie Ausnahmebehandlungscode in einem **catch** Block. Den Code in der **catch** Block wird nur ausgeführt, wenn der Code innerhalb der **versuchen** Block eine Ausnahme des Typs im angegebenen der **catch** Anweisung.  
  
     Das folgende Skelett zeigt wie **versuchen** und **catch** Blöcke normalerweise angeordnet sind:  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     Wenn eine Ausnahme ausgelöst wird, wird die Steuerung an die erste **catch** blockieren, deren Exception-Deklaration mit dem Typ der Ausnahme übereinstimmt. Sie können verschiedene Arten von Ausnahmen mit sequenziellen selektiv behandeln **catch** blockiert wird, wie im folgenden aufgeführt:  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Umwandeln von MFC-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

