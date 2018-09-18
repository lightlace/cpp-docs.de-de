---
title: Exit-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71bff42495c4b6b7bf4016f0f08e7127c2b278ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075175"
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