---
title: _nolock-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _nolock functions
- nolock functions
ms.assetid: 7d651d87-38d2-4303-9897-fdb5f7a3e899
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5dca9fa9e0708e1fa8562fe2188362ac73c9be4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391573"
---
# <a name="nolock-functions"></a>_nolock Functions

Diese Funktionen führen keine Sperrungen durch. Sie sind für Benutzer bestimmt, die maximale Leistung fordern. Weitere Informationen siehe [Leistung von Multithreadbibliotheken](../c-runtime-library/multithreaded-libraries-performance.md).

 Verwenden Sie _nolock-Funktionen nur, wenn Ihr Programm tatsächlich ein Singlethread-Programm ist, oder wenn es seine eigene Sperrung durchführt.

## <a name="no-lock-routines"></a>Routinen ohne Sperre

 [_fclose_nolock](../c-runtime-library/reference/fclose-nolock.md)

 [_fflush_nolock](../c-runtime-library/reference/fflush-nolock.md)

 [_fgetc_nolock, _fgetwc_nolock](../c-runtime-library/reference/fgetc-nolock-fgetwc-nolock.md)

 [_fread_nolock](../c-runtime-library/reference/fread-nolock.md)

 [_fseek_nolock, _fseeki64_nolock](../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)

 [_ftell_nolock, _ftelli64_nolock](../c-runtime-library/reference/ftell-nolock-ftelli64-nolock.md)

 [_fwrite_nolock](../c-runtime-library/reference/fwrite-nolock.md)

 [_getc_nolock, _getwc_nolock](../c-runtime-library/reference/getc-nolock-getwc-nolock.md)

 [_getch_nolock, _getwch_nolock](../c-runtime-library/reference/getch-nolock-getwch-nolock.md)

 [_getchar_nolock, _getwchar_nolock](../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md)

 [_getche_nolock, _getwche_nolock](../c-runtime-library/reference/getche-nolock-getwche-nolock.md)

 [_getdcwd_nolock, _wgetdcwd_nolock](../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)

 [_putc_nolock, _putwc_nolock](../c-runtime-library/reference/putc-nolock-putwc-nolock.md)

 [_putch_nolock, _putwch_nolock](../c-runtime-library/reference/putch-nolock-putwch-nolock.md)

 [_putchar_nolock, _putwchar_nolock](../c-runtime-library/reference/putchar-nolock-putwchar-nolock.md)

 [_ungetc_nolock, _ungetwc_nolock](../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)

 [_ungetch_nolock, _ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)

## <a name="see-also"></a>Siehe auch

[Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)<br/>
 [Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
