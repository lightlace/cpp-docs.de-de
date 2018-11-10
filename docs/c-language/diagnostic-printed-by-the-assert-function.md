---
title: Diagnose von der assert-Funktion gedruckt
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: 330c694b53957cab2e44da7cb8b52031c33fb5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549044"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Diagnose von der assert-Funktion gedruckt

**ANSI 4.2** Die von der **assert**-Funktion ausgegebene Diagnose und das Abbruchverhalten dieser Funktion

Die **assert**-Funktion gibt eine Diagnosemeldung aus und ruft die **abort**-Routine auf, wenn der Ausdruck „false“ (0) ist. Die Diagnosemeldung hat die Form

> **Assertionsfehler**: <em>Ausdruck</em>**, Datei** <em>Dateiname</em>**, Zeile** *Zeilennummer*

Dabei steht *filename* für den Namen der Quelldatei und *linenumber* für die Zeilennummer der Assertion, die in der Quelldatei einen Fehler aufweist. Es werden keine Aktionen ausgeführt, wenn der *Ausdruck* TRUE ist (ungleich Null).

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)