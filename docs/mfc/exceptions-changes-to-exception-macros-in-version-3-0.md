---
title: "Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 073715c72dfad83490b377b5d55e1169297be1ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0
Dies ist ein-Thema für fortgeschrittene.  
  
 In MFC, Version 3.0 und höher haben die Ausnahmebehandlung Makros geändert, um C++-Ausnahmen zu verwenden. Dieser Artikel beschreibt, wie sich diese Änderungen das Verhalten von vorhandenem Code auswirken können, die die Makros verwendet.  
  
 In diesem Artikel werden die folgenden Themen behandelt:  
  
-   [Ausnahmetypen und das CATCH-Makro](#_core_exception_types_and_the_catch_macro)  
  
-   [Erneut auslösen von Ausnahmen](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a>Ausnahmetypen und das CATCH-Makro  
 In früheren Versionen von MFC die **CATCH** Makro verwendet MFC-Laufzeit-Typinformationen, um eine Ausnahme zu bestimmen; Ausnahmetyps wird bestimmt, das heißt, an den Catch-Standort. Mit C++-Ausnahmen wird allerdings Ausnahmetyps immer am Standort Throw durch den Typ des Ausnahmeobjekts bestimmt, die ausgelöst wird. Dadurch wird Inkompatibilitäten in den seltenen Fällen verursacht, in denen der Typ des Zeigers auf das Objekt ausgelöst wird aus dem Typ des ausgelösten Objekts unterscheidet sich.  
  
 Das folgende Beispiel veranschaulicht die Folge von diesen Unterschied zwischen MFC-Version 3.0 und früheren Versionen:  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 Dieser Code verhält sich anders in Version 3.0 da immer die Steuerung an die erste übergibt **catch** Block mit einer übereinstimmenden Ausnahmedeklaration. Das Ergebnis des Ausdrucks throw  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 wird ausgelöst, als eine **CException\***, obwohl es als konstruiert wird eine **CCustomException**. Die **CATCH** Makro in MFC-Version 2.5 und früheren verwendet `CObject::IsKindOf` So testen Sie den Typ zur Laufzeit. Da der Ausdruck  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 ist "true", der ersten Catch-Block die Ausnahme abgefangen. Entspricht der zweiten Catch-Block in Version 3.0, die C++-Ausnahmen verwendet, um viele der Ausnahmebehandlung Makros implementieren, die ausgelösten `CException`.  
  
 Der Code wie folgt ist ungewöhnlich. Es in der Regel wird angezeigt, wenn ein Exception-Objekt an eine andere Funktion übergeben wird, das einen generischen akzeptiert **CException\***, führt die Verarbeitung durch "Pre Throw" und schließlich wird die Ausnahme ausgelöst.  
  
 Um dieses Problem zu umgehen, verschieben Sie die Throw-Ausdruck von der Funktion an den aufrufenden Code, und löst eine Ausnahme des aktuellen Typs an den Compiler zu dem Zeitpunkt, den die Ausnahme generiert hat, ist bekannt.  
  
##  <a name="_core_re.2d.throwing_exceptions"></a>Erneut auslösen von Ausnahmen  
 Ein Catch-Block kann keine derselbe Ausnahmezeiger auslösen, den sie abgefangen.  
  
 Beispielsweise diesen Code war in früheren Versionen gültig, aber hat unerwartete Ergebnisse mit der Version 3.0:  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 Mit **AUSLÖSEN** im Catch-Block verursacht den Zeiger `e` gelöscht werden soll, damit die äußeren Catch-Website einen ungültigen Zeiger erhält,. Verwendung `THROW_LAST` erneut auszulösende `e`.  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

