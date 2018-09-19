---
title: Schreiben eines Beendigungshandlers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85241d9dde87e929b02328a6e7d0c75b5ce068ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116229"
---
# <a name="writing-a-termination-handler"></a>Schreiben eines Beendigungshandlers

Im Gegensatz zu einem Ausnahmehandler wird ein Beendigungshandler immer ausgeführt, unabhängig davon, ob der geschützte Codeblock ordnungsgemäß beendet wurde. Der Beendigungshandler sollte nur sicherstellen, dass Ressourcen, wie Arbeitsspeicher, Handles und Dateien ordnungsgemäß geschlossen werden, unabhängig davon, wie die Ausführung eines Codeabschnitts beendet wird.

Beendigungshandler verwenden die try-finally-Anweisung.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Try-finally-Anweisung](../cpp/try-finally-statement.md)

- [Bereinigen von Ressourcen](../cpp/cleaning-up-resources.md)

- [Zeitliche Steuerung von Aktionen in der Ausnahmebehandlung](../cpp/timing-of-exception-handling-a-summary.md)

- [Einschränkungen bei beendigungshandlern](../cpp/restrictions-on-termination-handlers.md)

## <a name="see-also"></a>Siehe auch

[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)