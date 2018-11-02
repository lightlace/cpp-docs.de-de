---
title: C++-Ausnahmebehandlung
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
ms.openlocfilehash: b4eaab7d5bb352cccc612dd950572464b82b67e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614746"
---
# <a name="c-exception-handling"></a>C++-Ausnahmebehandlung

Die Programmiersprache C++ bietet integrierte Unterstützung für das Auslösen und Abfangen von Ausnahmen. Beim Programmieren in C++ sollten Sie fast immer die in diesem Abschnitt beschriebene integrierte C++-Ausnahmeunterstützung verwenden.

Verwenden Sie zum Aktivieren von C++-Ausnahmebehandlung in Ihrem Code [/EHsc](../build/reference/eh-exception-handling-model.md).

## <a name="in-this-section"></a>In diesem Abschnitt

Diese Diskussion zur C++-Ausnahmebehandlung umfasst Folgendes:

- [Die try-, catch- und throw-Anweisungen](../cpp/try-throw-and-catch-statements-cpp.md)

- [Auswerten von Catch-Blöcken](../cpp/how-catch-blocks-are-evaluated-cpp.md)

- [Ausnahmen und Stapelentladung](../cpp/exceptions-and-stack-unwinding-in-cpp.md)

- [Ausnahmespezifikationen](../cpp/exception-specifications-throw-cpp.md)

- [noexcept](../cpp/noexcept-cpp.md)

- [Nicht behandelte C++-Ausnahmen](../cpp/unhandled-cpp-exceptions.md)

- [Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)

## <a name="support-for-earlier-mfc-exceptions"></a>Unterstützung für ältere MFC-Ausnahmen

Ab Version 4.0 begann MFC den C++-Mechanismus zur Ausnahmebehandlung zu verwenden. Obwohl Sie zum Verwenden der C++-Ausnahmebehandlung im neuen Code ermutigt werden, werden die Makros aus früheren MFC-Versionen in MFC-Version 4.0 sowie höheren Versionen beibehalten, sodass alter Code nicht unterbrochen wird. Die Makros und der neue Mechanismus können ebenfalls kombiniert werden. Informationen zum Kombinieren von Makros und C++-Ausnahmebehandlung und zum Konvertieren alten Codes, um den neuen Mechanismus verwenden, finden Sie in den Artikeln [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) und [Ausnahmen: Konvertierung von MFC Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md). Bei älteren MFC-Ausnahmemakros, sofern Sie diese noch verwenden, werden C++-Ausnahmeschlüsselwörter ausgewertet. Finden Sie unter [Ausnahmen: Änderungen an Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)