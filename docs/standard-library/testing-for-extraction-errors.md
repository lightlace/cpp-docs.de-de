---
title: Überprüfen von Extraktionen
ms.date: 11/04/2016
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
ms.openlocfilehash: 62d9c94f366ec666acf2179803c62e4a3ccd7e6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629228"
---
# <a name="testing-for-extraction-errors"></a>Überprüfen von Extraktionen

Verarbeitungsfunktionen für Ausgabefehler, die unter [Fehlerverarbeitende Funktionen](../standard-library/output-file-stream-member-functions.md) erörtert wurden, sind für Eingabestreams relevant. Das Testen auf Fehler ist während der Extraktion wichtig. Berücksichtigen Sie Folgendes:

```cpp
cin>> n;
```

Wenn `n` eine Ganzzahl mit Vorzeichen ist, legt ein Wert größer als 32.767 (der maximal zulässige Wert oder MAX_INT) das `fail`-Bit des Streams fest, und das `cin`-Objekt kann nicht mehr verwendet werden. Alle nachfolgenden Extraktionen führen zu einer sofortigen Rückgabe ohne gespeicherten Wert.

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
