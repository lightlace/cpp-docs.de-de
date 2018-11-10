---
title: Verschiebungen nach rechts
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: f39c1f2f49f5a8a1f3bb5eb3f21736eedf32077e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518208"
---
# <a name="right-shifts"></a>Verschiebungen nach rechts

Das Ergebnis einer Rechtsverschiebung eines Ganzzahltyps mit Vorzeichen mit negativem Wert

Das Verschieben eines negativen Werts nach rechts ergibt die Hälfte des absoluten Werts (abgerundet). Zum Beispiel ein signierter `short` Wert -253 (hexadezimal 0xFF03, Binärzahl 11111111 00000011) ein Bit nach rechts verschoben erzeugt -127 (hexadezimal 0xFF81, Binärzahl 11111111 10000001). Ein positiver nach rechts verschobener Wert 253 erzeugt + 126.

Rechtsverschiebungen behalten das signierte Bit des signierten Ganzzahltyps bei. Wenn eine ganze Zahl mit Vorzeichen nach rechts verschoben wird, bleibt das wichtigste Byte festgelegt. Wenn "0xF0000000" beispielsweise ein signierter `int` ist, ergibt eine Rechtsverschiebung den Wert "0xF8000000". Beim 32-maligen Verschieben eines negativen Werts `int` wird hierdurch "0xFFFFFFFF" erzeugt.

Bei der Rechtsverschiebung einer ganzen Zahl ohne Vorzeichen wird das wichtigste Byte gelöscht. Wenn "0xF000" nicht signiert ist, lautet das Ergebnis "0x7800". Beim 32-maligen Verschieben eines Werts `unsigned` oder positiven `int`-Werts wird hierdurch "0x00000000" erzeugt.

## <a name="see-also"></a>Siehe auch

[Ganze Zahlen](../c-language/integers.md)