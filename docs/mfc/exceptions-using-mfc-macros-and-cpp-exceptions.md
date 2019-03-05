---
title: 'Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen'
ms.date: 11/04/2016
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
ms.openlocfilehash: 00e88ddabf3a8e8b591bebae7ebc8ced0e1dc637
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297709"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen

Dieser Artikel behandelt die Überlegungen zum Schreiben von Code, der die Behandlung von Ausnahmen von MFC-Makros und der C++-Schlüsselwörter für die Ausnahmebehandlung verwendet.

In diesem Artikel werden die folgenden Themen behandelt:

- [Das Kombinieren von Ausnahmeschlüsselwörter und Makros](#_core_mixing_exception_keywords_and_macros)

- [Try-Blöcke innerhalb von Catch-Blöcken](#_core_try_blocks_inside_catch_blocks)

##  <a name="_core_mixing_exception_keywords_and_macros"></a> Das Kombinieren von Ausnahmeschlüsselwörter und Makros

Sie können MFC-Ausnahmemakros und C++-Ausnahmeschlüsselwörter im selben Programm kombinieren. Aber die MFC-Makros können nicht mit C++-Ausnahmeschlüsselwörter im selben Block gemischt werden, da die Makros, die Exception-Objekte automatisch gelöscht, wenn sie den gültigen Bereich verlassen, während Code mithilfe der Schlüsselwörter für die Ausnahmebehandlung nicht der Fall ist. Weitere Informationen finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

Der Hauptunterschied zwischen die Makros und die Schlüsselwörter ist, dass die Makros, die eine abgefangene Ausnahme "automatisch" löschen, wenn die Ausnahme den Gültigkeitsbereich verlässt. Code mit den Schlüsselwörtern nicht; Ausnahmen, die in einem Catch-Block abgefangen wird, müssen explizit gelöscht werden. Kombinieren von Makros und C++-Ausnahmeschlüsselwörter kann Speicherverluste verursachen, wenn ein Ausnahmeobjekt nicht gelöscht wird, oder zur Beschädigung des Heaps, wenn eine Ausnahme zweimal gelöscht wird.

Der folgende Code wird z. B. den Ausnahmezeiger ungültig:

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Das Problem tritt auf, weil `e` wird gelöscht, wenn die Ausführung aus der "inneren" gibt **CATCH** Block. Mithilfe der **THROW_LAST** -Makro anstelle von der **AUSLÖSEN** Anweisung führt dazu, dass der "äußeren" **CATCH** Block, um einen gültigen Zeiger zu erhalten:

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try-Blöcke innerhalb von Catch-Blöcken

Sie können nicht die aktuelle Ausnahme erneut auslösen, aus einer **versuchen Sie es** Block, der innerhalb einer **CATCH** Block. Im folgende Beispiel ist ungültig:

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Weitere Informationen finden Sie unter [Ausnahmen: Untersuchen von Ausnahmeinhalten](../mfc/exceptions-examining-exception-contents.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)
