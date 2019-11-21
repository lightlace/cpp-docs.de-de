---
title: Einschränkungen bei Beendigungshandlern
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 6c39407270037756c55dc42aed80e1d04616c9ee
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246386"
---
# <a name="restrictions-on-termination-handlers"></a>Einschränkungen bei Beendigungshandlern

You cannot use a **goto** statement to jump into a **__try** statement block or a **__finally** statement block. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. (You can, however, jump out of a **__try** statement block.) Also, you cannot nest an exception handler or termination handler inside a **__finally** block.

Darüber hinaus erzeugen einige in einem Beendigungshandler zulässige Arten von Code fragliche Ergebnisse. Daher sollten Sie diese, wenn überhaupt, mit Vorsicht verwenden. One is a **goto** statement that jumps out of a **__finally** statement block. Wenn der Block als Teil der normalen Beendigung ausgeführt wird, passiert nichts Ungewöhnliches. Aber wenn das System den Stapel entlädt, wird das Entladen gestoppt, und die aktuelle Funktion erhält die Steuerung,als ob keine nicht ordnungsgemäße Beendigung vorläge.

A **return** statement inside a **__finally** statement block presents roughly the same situation. Die Steuerung wird an den unmittelbaren Aufrufer der Funktion zurückgegeben, die den Beendigungshandler enthält. Wenn das System beim Entladen des Stapels war, wird dieser Prozess unterbrochen, und das Programm wird fortgesetzt, als wäre keine Ausnahme ausgelöst worden.

## <a name="see-also"></a>Siehe auch

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)