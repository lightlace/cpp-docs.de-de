---
title: abort-Funktion
ms.date: 12/01/2017
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
ms.openlocfilehash: 7c87cb4fe7349a0d623c765c20e7e213a8454571
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385101"
---
# <a name="abort-function"></a>abort-Funktion

Die **Abbrechen** -Funktion, auch in der standardincludedatei deklariert \<stdlib.h >, beendet ein C++-Programm. Der Unterschied zwischen `exit` und **Abbrechen** ist, die `exit` ermöglicht die Verarbeitung der C++-Laufzeit-Beendigung durchzuführen (globale Objekt Destruktoren aufgerufen werden), während **Abbrechen** das Programm beendet sofort. Weitere Informationen finden Sie unter [Abbrechen](../c-runtime-library/reference/abort.md) in die *Run-Time Library Reference*.

## <a name="see-also"></a>Siehe auch

[Programmbeendigung](../cpp/program-termination.md)