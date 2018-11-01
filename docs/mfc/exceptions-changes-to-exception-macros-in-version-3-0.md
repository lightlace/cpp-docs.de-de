---
title: 'Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8829c018e51b81c0997092312e3e058d3086665b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417032"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0

Dies ist ein Thema für fortgeschrittene.

In MFC, Version 3.0 und höher verfügen die Makros, die für die Ausnahmebehandlung geändert, um C++-Ausnahmen verwenden. Dieser Artikel beschreibt, wie diese Änderungen das Verhalten von vorhandenem Code beeinträchtigen können, die die Makros, die verwendet wird.

In diesem Artikel werden die folgenden Themen behandelt:

- [Ausnahmetypen und der CATCH-Makro](#_core_exception_types_and_the_catch_macro)

- [Erneutes Auslösen von Ausnahmen](#_core_re.2d.throwing_exceptions)

##  <a name="_core_exception_types_and_the_catch_macro"></a> Ausnahmetypen und der CATCH-Makro

In früheren Versionen von MFC die **CATCH** -Makro verwendet MFC-Laufzeit-Typinformationen um zu einer Ausnahme zu bestimmen, die den Typ der Ausnahme festgelegt wurde, das heißt, an die Catch-Standort. Mit C++-Ausnahmen ist jedoch den Typ der Ausnahme immer am Standort Throw durch den Typ des Ausnahmeobjekts bestimmt, die ausgelöst wird. Inkompatibilitäten wird in dem seltenen Fall dadurch der Typ des Objekts wird ausgelöst, in denen der Typ des Zeigers auf das ausgelöste Objekt unterscheidet.

Das folgende Beispiel veranschaulicht die Folge dieser Differenz zwischen MFC-Version 3.0 und früheren Versionen:

[!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

Dieser Code verhält sich anders Version 3.0, da immer die Steuerung an die erste übergibt **catch** Block mit einer übereinstimmenden Exception-Deklaration. Das Ergebnis des Throw-Ausdrucks

[!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

wird ausgelöst, als eine `CException*`, auch wenn es als konstruiert wird eine `CCustomException`. Die **CATCH** Makro in MFC-Version 2.5 und früher verwendet `CObject::IsKindOf` um den Typ zur Laufzeit zu testen. Da der Ausdruck

[!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

ist "true", der ersten Catch-Block die Ausnahme abgefangen. In Version 3.0, die C++-Ausnahmen, die zum Implementieren vieler die Makros, die für die Ausnahmebehandlung verwendet werden, entspricht der zweite Catch-Block die ausgelösten `CException`.

Code ist ungewöhnlich. Es in der Regel angezeigt wird, wenn ein Exception-Objekt an eine andere Funktion übergeben wird, die einen generischen akzeptiert `CException*`, führt die Verarbeitung von "Pre-Throw" und schließlich wird die Ausnahme ausgelöst.

Um dieses Problem zu umgehen, verschieben Sie die Throw-Ausdrucks von der Funktion an den aufrufenden Code, und löst eine Ausnahme des aktuellen Typs an den Compiler bekannt, zu dem Zeitpunkt, der die Ausnahme generiert wird.

##  <a name="_core_re.2d.throwing_exceptions"></a> Erneutes Auslösen von Ausnahmen

Ein Catch-Block kann nicht den gleichen Ausnahmezeiger ausgelöst, den sie abgefangen werden.

Angenommen, dieser Code war in früheren Versionen gültig, jedoch hat unerwartete Ergebnisse mit der Version 3.0:

[!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

Mithilfe von **AUSLÖSEN** im Catch-Block wird den Zeiger `e` gelöscht werden, damit die äußeren Catch-Website einen ungültigen Zeiger erhält,. Verwendung **THROW_LAST** erneut auszulösende `e`.

Weitere Informationen finden Sie unter [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

