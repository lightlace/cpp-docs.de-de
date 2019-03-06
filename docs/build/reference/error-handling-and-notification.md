---
title: Fehlerbehandlung und Benachrichtigung
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 7aae4d68b272a6c12233f283d4b263648062b7c1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418944"
---
# <a name="error-handling-and-notification"></a>Fehlerbehandlung und Benachrichtigung

Weitere Informationen zu Fehlerbehandlung und Benachrichtigung zu erhalten, finden Sie unter [die Hilfsfunktion](understanding-the-helper-function.md).

Weitere Informationen zu Hookfunktionen finden Sie unter [Struktur- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md).

Wenn Ihr Programm verzögert geladenen DLLs verwendet, müssen sie Laufzeitausnahmen da Fehler auftreten, während der Ausführung des Programms nicht behandelte Ausnahmen führen werden. Fehlerbehandlung besteht aus zwei Teilen:

Wiederherstellung über einen Hook.
Wenn Ihr Code muss wiederherzustellen, oder geben Sie eine alternative Bibliothek und/oder die Routine bei einem Fehler, kann ein Hook für die Hilfsfunktion bereitgestellt werden, die angeben oder das Problem beheben können. Die Routine Hook-Anforderungen einen geeigneten Wert zurückgegeben wird, damit die Verarbeitung können weiterhin (HINSTANCE oder FARPROC) oder 0, um anzugeben, dass eine Ausnahme ausgelöst werden soll. Auch ihre eigene Ausnahme auslösen oder **Longjmp** aus der Hook. Es gibt Benachrichtigungshooks und Fehlerhooks.

Meldung über eine Ausnahme aus.
Wenn alle, die für die Behandlung des Fehlers erforderlich ist, den Vorgang abzubrechen, ist kein Hook erforderlich, als der Code für die die Ausnahme behandeln kann.

Die folgenden Themen wird erläutert, Fehlerbehandlung und Benachrichtigung:

- [Benachrichtigungshooks](../../build/reference/notification-hooks.md)

- [Fehlerhooks](../../build/reference/failure-hooks.md)

- [Ausnahmen](../../build/reference/exceptions-c-cpp.md)

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)
