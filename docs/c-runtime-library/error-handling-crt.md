---
title: Fehlerbehandlung (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.errors
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
ms.openlocfilehash: 7b3a5676c9297b1d7805f92b3a15cc71518ecd65
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551215"
---
# <a name="error-handling-crt"></a>Fehlerbehandlung (CRT)

Verwenden Sie diese Routinen, um Programmfehler zu behandeln.

## <a name="error-handling-routines"></a>Routinen zur Fehlerbehandlung

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|Makro [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Testet auf Fehler in der Programmierlogik; ist sowohl in den Release- als auch den Debugversionen der Laufzeitbibliothek verfügbar.|
|Makros [_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Ähnelt **assert**, ist aber nur in den Debugversionen der Laufzeitbibliothek verfügbar.|
|[clearerr](../c-runtime-library/reference/clearerr.md)|Setzt den Fehlerindikator zurück. Das Aufrufen von **rewind** oder das Schließen eines Streams setzt den Fehlerindikator ebenfalls zurück.|
|[_eof](../c-runtime-library/reference/eof.md)|Prüft das Dateiende in E/A auf niedriger Ebene.|
|[feof](../c-runtime-library/reference/feof.md)|Prüft das Dateiende. Das Dateiende wird auch angezeigt, wenn **_read** 0 zurückgibt.|
|[ferror](../c-runtime-library/reference/ferror.md)|Prüft auf E/A-Fehler im Stream.|
|Makros [_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Generiert einen Bericht ähnlich wie bei **printf**, ist aber nur in den Debugversionen der Laufzeitbibliothek verfügbar.|
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Ändert **__error_mode**, um einen nicht standardmäßigen Speicherort zu bestimmen, in dem die C-Laufzeit eine Fehlermeldung für einen Fehler schreibt, der das Programm möglicherweise beendet.|
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Legt den Handler für einen rein virtuellen Funktionsaufruf fest.|

## <a name="see-also"></a>Siehe auch

- [Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
