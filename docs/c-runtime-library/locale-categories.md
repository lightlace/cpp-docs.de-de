---
title: Gebietsschemakategorien
ms.date: 11/04/2016
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
ms.openlocfilehash: 4c46f4803c7b6ff226fc41ddce7f8e4493b0db40
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521349"
---
# <a name="locale-categories"></a>Gebietsschemakategorien

## <a name="syntax"></a>Syntax

```

#include <locale.h>
```

## <a name="remarks"></a>Hinweise

Gebietsschemakategorien sind Manifestkonstanten, die von den Lokalisierungsroutinen verwendet werden, um anzugeben, welcher Teil der Gebietsschemainformationen eines Programms verwendet wird. Das Gebietsschema verweist auf den Ort (oder Land/Region), für den Sie bestimmte Aspekte des Programms anpassen können. Vom Gebietsschema abhängige Bereiche umfassen u.a. die Formatierung von Daten oder das Anzeigeformat für monetäre Werte.

|Gebietsschemakategorie|Teile des betroffenen Programms|
|---------------------|-------------------------------|
|`LC_ALL`|Alle gebietsschemaspezifischen Verhalten (alle Kategorien)|
|`LC_COLLATE`|Verhalten der `strcoll`- und `strxfrm`-Funktion|
|`LC_CTYPE`|Das Verhalten von Funktionen zur Zeichenbehandlung (außer **isdigit**, `isxdigit`, `mbstowcs` und `mbtowc`, die nicht betroffen sind)|
|`LC_MAX`|Identisch mit `LC_TIME`|
|`LC_MIN`|Identisch mit `LC_ALL`|
|`LC_MONETARY`|Durch die `localeconv`-Funktion zurückgegebene Informationen zur Währungsformatierung|
|`LC_NUMERIC`|Dezimaltrennzeichen für formatierte Ausgaberoutinen (z.B. `printf`), Datenkonvertierungsroutinen und nicht monetäre Formatierungsinformationen, die von der `localeconv`-Funktion zurückgegeben werden|
|`LC_TIME`|Verhalten der `strftime`-Funktion|

Ein Beispiel finden Sie unter [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).

## <a name="see-also"></a>Siehe auch

[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcoll-Funktionen](../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)