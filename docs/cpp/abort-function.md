---
title: abort-Funktion
ms.date: 12/01/2017
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
ms.openlocfilehash: 7c87cb4fe7349a0d623c765c20e7e213a8454571
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451232"
---
# <a name="abort-function"></a>abort-Funktion

Die **Abbrechen** -Funktion, auch in der standardincludedatei deklariert \<stdlib.h >, beendet ein C++-Programm. Der Unterschied zwischen `exit` und **Abbrechen** ist, die `exit` ermöglicht die Verarbeitung der C++-Laufzeit-Beendigung durchzuführen (globale Objekt Destruktoren aufgerufen werden), während **Abbrechen** das Programm beendet sofort. Weitere Informationen finden Sie unter [Abbrechen](../c-runtime-library/reference/abort.md) in die *Run-Time Library Reference*.

## <a name="see-also"></a>Siehe auch

[Programmbeendigung](../cpp/program-termination.md)