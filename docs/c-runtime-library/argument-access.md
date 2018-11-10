---
title: Argumentzugriff
ms.date: 04/04/2018
f1_keywords:
- c.arguments
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
ms.openlocfilehash: 8107cffa6a2da41c38b116b2e3fe36adf6ac945f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470407"
---
# <a name="argument-access"></a>Argumentzugriff

Die Makros **va_arg**, **va_end** und **va_start** bieten Zugriff auf Funktionsargumente, wenn die Anzahl der Argumente variabel ist. Diese Makros sind in \<stdarg.h> für die Kompatibilität mit ANSI/ISO-C und in \<varargs.h> für die Kompatibilität mit UNIX System V definiert.

## <a name="argument-access-macros"></a>Makros für den Argumentzugriff

|Makro|Mit|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Argument aus der Liste abrufen|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Zeiger zurücksetzen|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Zeiger auf den Anfang der Liste der Argumente festlegen|

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
