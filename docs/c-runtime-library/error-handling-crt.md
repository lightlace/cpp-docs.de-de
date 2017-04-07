---
title: Fehlerbehandlung (CRT) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.errors
dev_langs:
- C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: ad3844e5d57081b1a9638e197231479b7a03a337
ms.lasthandoff: 03/29/2017

---
# <a name="error-handling-crt"></a>Fehlerbehandlung (CRT)
Verwenden Sie diese Routinen, um Programmfehler zu behandeln.  
  
### <a name="error-handling-routines"></a>Routinen zur Fehlerbehandlung  
  
|Routine|Verwendung|  
|-------------|---------|  
|Makro [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Testet auf Fehler in der Programmierlogik; ist sowohl in den Release- als auch den Debugversionen der Laufzeitbibliothek verfügbar.|  
|Makros [_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Entspricht `assert`, ist aber nur in den Debugversionen der Laufzeitbibliothek verfügbar.|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Setzt den Fehlerindikator zurück. Das Aufrufen von `rewind` oder das Schließen eines Streams setzt den Fehlerindikator ebenfalls zurück.|  
|[_eof](../c-runtime-library/reference/eof.md)|Prüft das Dateiende in E/A auf niedriger Ebene.|  
|[feof](../c-runtime-library/reference/feof.md)|Prüft das Dateiende. Das Dateiende wird auch angezeigt, wenn `_read` 0 zurückgibt.|  
|[ferror](../c-runtime-library/reference/ferror.md)|Prüft auf E/A-Fehler im Stream.|  
|Makros [_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Generiert einen Bericht ähnlich wie bei `printf`, ist aber nur in den Debugversionen der Laufzeitbibliothek verfügbar.|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Ändert `__error_mode`, um einen nicht standardmäßigen Speicherort zu bestimmen, in dem die C-Laufzeit eine Fehlermeldung für einen Fehler schreibt, der das Programm möglicherweise beendet.|  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Legt den Handler für einen rein virtuellen Funktionsaufruf fest.|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
