---
title: 'Ausnahmen: Umwandeln von MFC-Ausnahmemakros'
ms.date: 08/27/2018
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
ms.openlocfilehash: 59b83438d5341fd6a139af64a2f365a739438741
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394506"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Ausnahmen: Umwandeln von MFC-Ausnahmemakros

Dies ist ein Thema für fortgeschrittene.

In diesem Artikel wird erläutert, wie zum Konvertieren von vorhandenem Codes, die mit Microsoft Foundation Class-Makros geschrieben – **versuchen Sie es**, **CATCH**, **AUSLÖSEN**und so weiter – verwenden Sie die C++-Ausnahmebehandlung Schlüsselwörter **versuchen**, **catch**, und **auslösen**. Folgende Themen werden behandelt:

- [Vorteile der Konvertierung](#_core_advantages_of_converting)

- [Konvertieren von Code mit von Ausnahmemakros zur Verwendung von C++-Ausnahmen](#_core_doing_the_conversion)

##  <a name="_core_advantages_of_converting"></a> Vorteile der Konvertierung

Sie müssen wahrscheinlich nicht zum Konvertieren von vorhandenem Code, obwohl der Unterschiede zwischen der Implementierung in früheren Versionen und die Makro-Implementierungen in MFC, Version 3.0 beachtet werden sollten. Die Unterschiede und nachfolgende Änderungen im Verhalten von Code finden Sie im [Ausnahmen: Änderungen an Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).

Die Hauptvorteile von konvertiert werden:

- Code, der C++-Schlüsselwörter für die Ausnahmebehandlung verwendet, die in einer etwas kleiner kompiliert werden. EXE-Datei oder. DLL.

- Die C++ Ausnahmebehandlung Schlüsselwörter sind vielseitiger: Sie können Behandeln von Ausnahmen eines beliebigen Datentyps, die kopiert werden können (**Int**, **"float"**, **Char**und so weiter), während die Makros, die Ausnahmen nur der-Klasse behandeln `CException` und davon abgeleitete Klassen.

Der Hauptunterschied zwischen die Makros und die Schlüsselwörter ist, dass Code mithilfe von "automatisch" die Makros, die eine abgefangene Ausnahme gelöscht, wenn die Ausnahme den Gültigkeitsbereich verlässt. Code mit den Schlüsselwörtern jedoch nicht, daher müssen Sie eine abgefangene Ausnahme explizit löschen. Weitere Informationen finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

Ein weiterer Unterschied ist die Syntax. Die Syntax für Schlüsselwörter und Makros unterscheidet sich in drei Hinsicht:

1. Makroargumente und Ausnahmedeklarationen:

   Ein **CATCH** Makroaufruf weist die folgende Syntax:

   **CATCH (** *Exception_class*, *Exception_object_pointer_name* **)**

   Beachten Sie das Komma zwischen den Klassennamen und die Zeiger zu verwendenden Objektnamen ein.

   Die Ausnahmedeklaration für die **catch** -Schlüsselwort verwendet diese Syntax:

   **catch(** *exception_type* *exception_name* **)**

   Diese Ausnahme-Declaration-Anweisung gibt den Typ der Ausnahme-Catch-Block behandelt.

2. Die Abgrenzung der Catch-Blöcken:

   Mit den Makros die **CATCH** Makros (mit den Argumenten) beginnt, den ersten Catch-Block: der **AND_CATCH** Makros beginnt nachfolgende Catch-Blöcke, und die **END_CATCH** Makro beendet die Reihenfolge der Catch-Blöcke.

   Mit den Schlüsselwörtern die **catch** Schlüsselwort (mit der Ausnahmedeklaration) beginnt jede Catch-Block. Es gibt keine Entsprechung, um die **END_CATCH** Makro; der Catch-block endet mit der schließenden geschweiften Klammer.

3. Der Throw-Ausdruck:

   Verwenden Sie die Makros **THROW_LAST** um die aktuelle Ausnahme erneut auszulösen. Die **auslösen** -Schlüsselwort, das ohne Argumente hat dieselbe Wirkung.

##  <a name="_core_doing_the_conversion"></a> Die Konvertierung

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>Konvertieren von Code mithilfe von Makros um zu verwenden, die Schlüsselwörter der C++-Ausnahmebehandlung

1. Suchen Sie alle Vorkommen von MFC-Makros **versuchen**, **CATCH**, **AND_CATCH**, **END_CATCH**, **AUSLÖSEN**, und **THROW_LAST**.

2. Ersetzen Sie oder löschen Sie alle Vorkommen der folgenden Makros:

   **Versuchen Sie es** (ersetzen Sie diese **versuchen**)

   **ABFANGEN** (ersetzen Sie diese **catch**)

   **AND_CATCH** (ersetzen Sie diese **catch**)

   **END_CATCH** (löschen)

   **LÖST** (ersetzen Sie diese **auslösen**)

   **THROW_LAST** (ersetzen Sie diese **auslösen**)

3. Ändern Sie die Makroargumente, sodass sie gültige Ausnahmedeklarationen bilden.

   Beispielsweise ändern

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   auf

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Ändern Sie den Code im Catch-Blöcken, sodass Exception-Objekte nach Bedarf wird gelöscht. Weitere Informationen finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

Hier ist ein Beispiel für Code zur Ausnahmebehandlung mithilfe von MFC-Ausnahmemakros. Beachten Sie, dass der Code im folgenden Beispiel die Makros, die die Ausnahme verwendet `e` automatisch gelöscht wird:

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

Der Code im nächsten Beispiel verwendet die C++-Ausnahmeschlüsselwörter aus, damit die Ausnahme explizit gelöscht werden muss:

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

Weitere Informationen finden Sie unter [Ausnahmen: Mithilfe von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)<br/>
