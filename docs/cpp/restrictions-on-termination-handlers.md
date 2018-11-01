---
title: Einschränkungen bei Beendigungshandlern
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 7b092ee8682dfeef0c8151c56544e36427f40da0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628227"
---
# <a name="restrictions-on-termination-handlers"></a>Einschränkungen bei Beendigungshandlern

Können keine **Goto** gesprungen-Anweisung eine **__try** Anweisungsblock oder ein **__finally** Anweisungsblock. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. (Sie können jedoch direkt von einem **__try** Anweisungsblock.) Darüber hinaus können nicht geschachtelt keinen Ausnahmehandler oder Beendigungshandler innerhalb einer **__finally** Block.

Darüber hinaus erzeugen einige in einem Beendigungshandler zulässige Arten von Code fragliche Ergebnisse. Daher sollten Sie diese, wenn überhaupt, mit Vorsicht verwenden. Eine ist ein **Goto** -Anweisung, die von springt eine **__finally** Anweisungsblock. Wenn der Block als Teil der normalen Beendigung ausgeführt wird, passiert nichts Ungewöhnliches. Aber wenn das System den Stapel entlädt, wird das Entladen gestoppt, und die aktuelle Funktion erhält die Steuerung,als ob keine nicht ordnungsgemäße Beendigung vorläge.

Ein **zurückgeben** -Anweisung innerhalb einer **__finally** -Anweisungsblocks stellt ungefähr die gleiche Situation. Die Steuerung wird an den unmittelbaren Aufrufer der Funktion zurückgegeben, die den Beendigungshandler enthält. Wenn das System beim Entladen des Stapels war, wird dieser Prozess unterbrochen, und das Programm wird fortgesetzt, als wäre keine Ausnahme ausgelöst worden.

## <a name="see-also"></a>Siehe auch

[Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)