---
title: localeconv | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- localeconv
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- localeconv
dev_langs:
- C++
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe3cc75430dfa9bb2f4c5513f4b2ba5a2fd1c4c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405249"
---
# <a name="localeconv"></a>localeconv

Ruft detaillierte Informationen über Gebietsschemaeinstellungen ab.

## <a name="syntax"></a>Syntax

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>Rückgabewert

**Localeconv** gibt einen Zeiger auf ein ausgefüllt Objekt vom Typ [Struktur Lconv](../../c-runtime-library/standard-types.md). Die in dem Objekt enthaltenen Werte aus den gebietsschemaeinstellungen im threadlokalen Speicher kopiert werden, und kann überschrieben werden, durch nachfolgende Aufrufe **Localeconv**. Zu den Werten in diesem Objekt vorgenommenen Änderungen ändern nicht die gebietsschemaeinstellungen. Aufrufe von [Setlocale](setlocale-wsetlocale.md) mit *Kategorie* Werte **LC_ALL**, **LC_MONETARY**, oder **LC_NUMERIC** Überschreiben Sie den Inhalt der Struktur.

## <a name="remarks"></a>Hinweise

Die **Localeconv** Funktion ruft ausführliche Informationen zum Formatieren von numerischen Daten für das aktuelle Gebietsschema ab. Diese Informationen werden in einer Struktur des Typs **lconv** gespeichert. Die **lconv**-Struktur, die in LOCALE.H definiert ist, enthält die folgenden Member:

|Feld|Bedeutung|
|-|-|
Decimal_point,<br/>_W_decimal_point|Zeiger auf Zeichen für nonmonetary Mengen Dezimaltrennzeichen.
Thousands_sep,<br/>_W_thousands_sep|Zeiger auf ein Zeichen trennt Gruppen der Ziffern links vom Dezimaltrennzeichen für nonmonetary Mengen.
Gruppieren|Zeiger auf eine **Char**-Größe ganze Zahl, die Größe der einzelnen Gruppen von Ziffern in nonmonetary Mengen enthält.
Int_curr_symbol,<br/>_W_int_curr_symbol|Ein Zeiger auf den internationalen Währungssymbol für das aktuelle Gebietsschema. Die ersten drei Zeichen geben das alphabetische internationale Währungssymbol an, wie im Standard *ISO 4217 – Codes für die Darstellung der Währung und Fonds* definiert. Das vierte Zeichen (unmittelbar vorausgehendes Zeichen NULL) trennt das internationale Währungssymbol von der monetären Menge.
Currency_symbol,<br/>_W_currency_symbol|Ein Zeiger auf die lokale Währung-Symbol für das aktuelle Gebietsschema.
Mon_decimal_point,<br/>_W_mon_decimal_point|Zeiger auf Zeichen für finanzielle Mengen Dezimaltrennzeichen.
Mon_thousands_sep,<br/>_W_mon_thousands_sep|Ein Zeiger auf die Trennzeichen für Gruppen von Ziffern links vom Dezimaltrennzeichen in monetäre Mengen.
mon_grouping|Zeiger auf eine **Char**-Größe ganze Zahl, die Größe der einzelnen Gruppen von Ziffern in monetäre Mengen enthält.
Positive_sign,<br/>_W_positive_sign|Die Zeichenfolge, die das Zeichen für nicht negative monetären Mengen angibt.
Negative_sign,<br/>_W_negative_sign|Die Zeichenfolge, die das Zeichen für negative monetären Mengen angibt.
int_frac_digits|Die Anzahl der Ziffern rechts vom Dezimaltrennzeichen in international formatierten monetären Mengen.
frac_digits|Die Anzahl der Ziffern rechts vom Dezimaltrennzeichen in formatierten monetären Mengen.
p_cs_precedes|Auf 1 festgelegt, wenn dem Währungssymbol ein Wert für eine nicht negative, formatierte monetäre Menge vorangeht. Auf 0 festgelegt, wenn das Symbol einem Wert folgt.
p_sep_by_space|Auf 1 festgelegt, wenn das Währungssymbol durch Leerzeichen von einem Wert für eine nicht negative, formatierte monetäre Menge getrennt ist. Auf 0 festgelegt, wenn es keine Leerzeichentrennung gibt.
n_cs_precedes|Auf 1 festgelegt, wenn dem Währungssymbol ein Wert für eine negative, formatierte monetäre Menge vorangeht. Auf 0 festgelegt, wenn das Symbol einem Wert nachfolgt.
n_sep_by_space|Auf 1 festgelegt, wenn das Währungssymbol durch Leerzeichen von einem Wert für eine negative, formatierte monetäre Menge getrennt ist. Auf 0 festgelegt, wenn es keine Leerzeichentrennung gibt.
p_sign_posn|Die Position des positiven Vorzeichens in nicht negativen, formatierten monetären Mengen.
n_sign_posn|Die Position des positiven Vorzeichens in negativen, formatierten monetären Mengen.

Sofern angegeben, Mitglied der **Lconv** -Struktur, die über `char *` und `wchar_t *` Versionen sind Zeiger auf Zeichenfolgen. Eines dieser, die gleich **""** (oder **L ""** für **Wchar_t \*** ) ist entweder der Länge null oder nicht im aktuellen Gebietsschema unterstützt. Beachten Sie, dass **Decimal_point** und **_W_decimal_point** werden immer unterstützt und einer Länge ungleich NULL.

Die **Char** Member der Struktur sind kleine nicht negative Zahlen, nicht auf Zeichen. Jeder von diesen, der gleich **CHAR_MAX** ist, wird im aktuellen Gebietsschema nicht unterstützt.

Die Werte der **gruppieren** und **Mon_grouping** gemäß den folgenden Regeln interpretiert werden:

- **CHAR_MAX** -führen keine weiteren gruppieren.

- 0 – verwenden Sie vorangehenden Element für jede der verbleibenden Ziffern.

- *n* -Anzahl der Ziffern, die aktuelle Gruppe bilden. Das nächste Element wird untersucht, um die Größe der nächsten Gruppe von Zeichen vor der aktuellen Gruppe zu bestimmen.

Die Werte für **int_curr_symbol** werden gemäß den folgenden Regeln interpretiert:

- Die ersten drei Zeichen geben das alphabetische internationale Währungssymbol an, wie im Standard *ISO 4217 – Codes für die Darstellung der Währung und Fonds* definiert.

- Das vierte Zeichen (unmittelbar vorausgehendes Zeichen NULL) trennt das internationale Währungssymbol von der monetären Menge.

Die Werte für **p_cs_precedes** und **n_cs_precedes** werden gemäß den folgenden Regeln interpretiert (die **n_cs_precedes**-Regel wird in Klammern angegeben):

- 0 – folgt Währungssymbol Wert für nicht negative (negativ) formatierte Währungswert an.

- 1 - Währungssymbol vorangestellt Wert für nicht negative (negativ) formatierte Währungswert.

Die Werte für **p_sep_by_space** und **n_sep_by_space** werden gemäß den folgenden Regeln interpretiert (die **n_sep_by_space**-Regel wird in Klammern angegeben):

- 0 - Währungssymbol vom Wert von Speicherplatz für nicht negative (negativ) formatierte Währungswert getrennt ist.

- 1 – Es gibt keine Trennung Leerzeichen zwischen dem Währungssymbol und der Wert für nicht negative (negativ) formatierte Währungswert.

Die Werte für **p_sign_posn** und **n_sign_posn** werden gemäß den folgenden Regeln interpretiert:

- 0 – Klammern umgeben Menge und Currency Symbol.

- 1 - Anmelde-Zeichenfolge ist die Menge und Currency Symbol vorangestellt.

- 2 - Anmelde-Zeichenfolge folgt Menge und Currency Symbol.

- 3 - Anmelde-Zeichenfolge ist sofort Währungssymbol vorangestellt.

- 4 – Anmeldung Zeichenfolge unmittelbar folgt Währungssymbol.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**localeconv**|\<locale.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Locale](../../c-runtime-library/locale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
