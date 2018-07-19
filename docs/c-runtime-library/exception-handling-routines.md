---
title: Ausnahmebehandlungsroutinen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eea92c5bfdb54b6c15ae2ae643b2d23b397a3bf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389074"
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
