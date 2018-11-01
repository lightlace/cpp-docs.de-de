---
title: exit-Funktion
ms.date: 11/04/2016
f1_keywords:
- Exit
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
ms.openlocfilehash: 82c9d00a49c8a080d893a51052739a0265ad0860
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532560"
---
# <a name="exit-function"></a>exit-Funktion

Die **beenden** -Funktion, in der standardincludedatei deklariert \<stdlib.h >, beendet ein C++-Programm.

Der als Argument bereitgestellte Wert **beenden** an das Betriebssystem als des Programms Rückgabecode oder Exitcode zurückgegeben wird. Gemäß der Konvention bedeutet ein Rückgabecode von Null, dass das Programm erfolgreich abgeschlossen wurde.

> [!NOTE]
>  Sie können die Konstanten EXIT_FAILURE und EXIT_SUCCESS, definiert \<stdlib.h >, um den Erfolg oder Fehler des Programms anzugeben.

Ausgeben einer **zurückgeben** -Anweisung aus der `main` Funktion entspricht dem Aufrufen der **beenden** Funktion mit dem Rückgabewert als Argument.

Weitere Informationen finden Sie unter [beenden](../c-runtime-library/reference/exit-exit-exit.md) in die *Run-Time Library Reference*.

## <a name="see-also"></a>Siehe auch

[Programmbeendigung](../cpp/program-termination.md)