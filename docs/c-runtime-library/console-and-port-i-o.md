---
title: Konsole und Port-E/A | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- routines, console and port I/O
- routines
- ports, I/O routines
- I/O [CRT], console
- I/O [CRT], port
- I/O routines, console and port I/O
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4d46582266234b4208a768fc7b2045af824349
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="console-and-port-io"></a>Konsole und Port-E/A

Diese Routinen lesen und schreiben Daten in Ihre Konsole oder an den angegebenen Port. Die E/A-Routinen der Konsole sind nicht mit Stream-E/A oder E/A-Bibliotheksroutinen niedrigerer Ebenen kompatibel. Die Konsole oder der Port muss vor der Ausführung von E/A nicht geöffnet oder geschlossen werden, weshalb es in dieser Kategorie keine Routinen zum Öffnen oder Schließen gibt. In den Windows-Betriebssystemen wird die Ausgabe dieser Funktionen immer an die Konsole weitergeleitet und kann nicht umgeleitet werden.

## <a name="console-and-port-io-routines"></a>Konsolen- und Port-E/A-Routinen

|-Routine zurückgegebener Wert|Mit|
|-------------|---------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md), [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Zeichenfolge aus der Konsole lesen|
|[_cprintf, _cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Formatierte Daten in Konsole schreiben|
|[_cputs](../c-runtime-library/reference/cputs-cputws.md)|Zeichenfolge in Konsole schreiben|
|[_cscanf, _cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Formatierte Daten aus Konsole lesen|
|[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)|Zeichen aus Konsole lesen|
|[_getche, _getwche](../c-runtime-library/reference/getch-getwch.md)|Zeichen aus Konsole lesen und wiederholen|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|Ein Byte aus dem angegebenen E/A-Port lesen|
|[_inpd](../c-runtime-library/inp-inpw-inpd.md)|Doppelwort aus dem angegebenen E/A-Port lesen|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|2-Byte-Wort aus dem angegebenen E/A-Port lesen|
|[_kbhit](../c-runtime-library/reference/kbhit.md)|Tastatureingabe bei der Konsole überprüfen; vor Sie Lesen aus der Konsole verwenden|
|[_outp](../c-runtime-library/outp-outpw-outpd.md)|Ein Byte an den angegebenen E/A-Port schreiben|
|[_outpd](../c-runtime-library/outp-outpw-outpd.md)|Doppelwort an den angegebenen E/A-Port schreiben|
|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|Wort an den angegebenen E/A-Port schreiben|
|[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)|Zeichen in Konsole schreiben|
|[_ungetch, _ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|Letztes Zeichen von „Unget“ aus der Konsole lesen, damit das nächste Zeichen gelesen wird|

## <a name="see-also"></a>Siehe auch

[Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)<br/>
 [Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>