---
title: Ausnahmebehandlungsroutinen
ms.date: 11/04/2016
f1_keywords:
- c.exceptions
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
ms.openlocfilehash: 09d58e49d3c9dc9b4b8ef40f725e927603e3e47c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507457"
---
# <a name="exception-handling-routines"></a>Ausnahmebehandlungsroutinen

Verwenden Sie die C++-Ausnahmebehandlungsfunktionen, um nach unerwarteten Ereignissen während der Programmausführung eine Wiederherstellung durchzuführen.

## <a name="exception-handling-functions"></a>Ausnahmebehandlungsfunktionen

|Funktion|Mit|
|--------------|---------|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Behandelt Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installiert Ihre eigene Beendigungsroutine, die von **terminate** aufgerufen werden soll|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installiert Ihre eigene Beendigungsfunktion, die von **unexpected** aufgerufen werden soll|
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Wird nach dem Auslösen einer Ausnahme unter bestimmten Umständen automatisch aufgerufen. Die **terminate**-Funktion ruft **abort** oder eine Funktion auf, die Sie mithilfe von **set_terminate** festlegen können.|
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Ruft **terminate** oder eine Funktion auf, die Sie mithilfe von **set_unexpected** festlegen können. Die Funktion **unexpected** wird in der aktuellen Microsoft C++-Ausnahmebehandlungsimplementierung nicht verwendet.|

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
