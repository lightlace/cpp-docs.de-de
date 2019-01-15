---
title: EOF, WEOF
ms.date: 11/04/2016
f1_keywords:
- EOF
helpviewer_keywords:
- EOF function
- WEOF function
- end of file
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
ms.openlocfilehash: c4c35518130fc233afd055133704bcb0abaccca8
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220724"
---
# <a name="eof-weof"></a>EOF, WEOF

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Hinweise

EOF wird von einer E/A-Routine zurückgegeben, wenn das Ende der Datei (oder in einigen Fällen ein Fehler) vorgefunden wird.

WEOF liefert den Rückgabewert vom Typ **wint_t**, mit dem das Ende eines breiten Streams signalisiert oder ein Fehler gemeldet wird.

## <a name="see-also"></a>Siehe auch

[putc, putwc](../c-runtime-library/reference/putc-putwc.md)<br/>
[ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[fflush](../c-runtime-library/reference/fflush.md)<br/>
[fclose, _fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)<br/>
[isascii, __isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
