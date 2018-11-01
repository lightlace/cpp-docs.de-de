---
title: Schreiben eines Ausnahmehandlers
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
ms.openlocfilehash: 6f1bcecf3aaed2bf2b7ebbe511f11cdb5ec1ca5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644781"
---
# <a name="writing-an-exception-handler"></a>Schreiben eines Ausnahmehandlers

Ausnahmehandler werden in der Regel verwendet, um auf bestimmte Fehler zu reagieren. Sie können die Syntax für die Ausnahmebehandlung nutzen, um alle Ausnahmen außer denen zu filtern, deren Behandlung bekannt ist. Andere Ausnahmen sollten an andere Handler übergeben werden (möglicherweise in der Laufzeitbibliothek oder im Betriebssystem), die geschrieben wurden, um nach diesen speziellen Ausnahmen zu suchen.

Ausnahmehandler verwenden die try-except-Anweisung.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Die Try-except-Anweisung](../cpp/try-except-statement.md)

- [Schreiben eines Ausnahmefilters](../cpp/writing-an-exception-filter.md)

- [Auslösen von Softwareausnahmen](../cpp/raising-software-exceptions.md)

- [Hardwareausnahmen](../cpp/hardware-exceptions.md)

- [Einschränkungen bei Ereignishandlern](../cpp/restrictions-on-exception-handlers.md)

## <a name="see-also"></a>Siehe auch

[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)