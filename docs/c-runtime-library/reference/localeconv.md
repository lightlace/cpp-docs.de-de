---
title: localeconv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: localeconv
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
f1_keywords: localeconv
dev_langs: C++
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cbd897b353f8a915fb4a29d61d0954b9b5a7f53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="localeconv"></a>localeconv
Ruft detaillierte Informationen über Gebietsschemaeinstellungen ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct lconv *localeconv( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `localeconv` gibt einen Zeiger auf ein ausgefülltes Objekt vom Typ [struct lconv](../../c-runtime-library/standard-types.md) zurück. Die in dem Objekt enthaltenen Werte aus den gebietsschemaeinstellungen im threadlokalen Speicher kopiert werden, und kann überschrieben werden, durch nachfolgende Aufrufe von `localeconv`. Zu den Werten in diesem Objekt vorgenommenen Änderungen ändern nicht die gebietsschemaeinstellungen. Aufrufe von [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) mit `category`-Werten von `LC_ALL`, `LC_MONETARY` oder `LC_NUMERIC` überschreiben den Inhalt der Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die `localeconv`-Funktion ruft detaillierte Informationen zur numerischen Formatierung für das aktuelle Gebietsschema ab. Diese Informationen werden in einer Struktur des Typs gespeichert `lconv`. Die `lconv` Struktur, die im GEBIETSSCHEMA definiert. H, enthält die folgenden Elemente:  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 Dezimaltrennzeichen für nichtmonetäre Mengen.  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 Zeichen, die Gruppen von Ziffern links vom Dezimaltrennzeichen für nichtmonetäre Mengen trennt.  
  
 `char *grouping`  
 Zeiger auf eine `char`-Größe ganze Zahl, die Größe der einzelnen Gruppen von Ziffern in nonmonetary Mengen enthält.  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 Das internationale Währungssymbol für das aktuelle Gebietsschema. Die ersten drei Zeichen geben das alphabetische internationale Währungssymbol an, wie im Standard *ISO 4217 – Codes für die Darstellung der Währung und Fonds* definiert. Das vierte Zeichen (unmittelbar vorausgehendes Zeichen NULL) trennt das internationale Währungssymbol von der monetären Menge.  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 Das lokale Währungssymbol für das aktuelle Gebietsschema.  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 Dezimaltrennzeichen für monetäre Mengen.  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 Trennzeichen für Gruppen von Ziffern links von der Dezimalstelle in monetären Mengen.  
  
 `char *mon_grouping`  
 Zeiger auf eine `char`-Größe ganze Zahl, die Größe der einzelnen Gruppen von Ziffern in monetäre Mengen enthält.  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 Die Zeichenfolge, die das Zeichen für nicht negative monetären Mengen angibt.  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 Die Zeichenfolge, die das Zeichen für negative monetären Mengen angibt.  
  
 `char int_frac_digits`  
 Die Anzahl der Ziffern rechts vom Dezimaltrennzeichen in international formatierten monetären Mengen.  
  
 `char frac_digits`  
 Die Anzahl der Ziffern rechts vom Dezimaltrennzeichen in formatierten monetären Mengen.  
  
 `char p_cs_precedes`  
 Auf 1 festgelegt, wenn dem Währungssymbol ein Wert für eine nicht negative, formatierte monetäre Menge vorangeht. Auf 0 festgelegt, wenn das Symbol einem Wert folgt.  
  
 `char p_sep_by_space`  
 Auf 1 festgelegt, wenn das Währungssymbol durch Leerzeichen von einem Wert für eine nicht negative, formatierte monetäre Menge getrennt ist. Auf 0 festgelegt, wenn es keine Leerzeichentrennung gibt.  
  
 `char n_cs_precedes`  
 Auf 1 festgelegt, wenn dem Währungssymbol ein Wert für eine negative, formatierte monetäre Menge vorangeht. Auf 0 festgelegt, wenn das Symbol einem Wert nachfolgt.  
  
 `char n_sep_by_space`  
 Auf 1 festgelegt, wenn das Währungssymbol durch Leerzeichen von einem Wert für eine negative, formatierte monetäre Menge getrennt ist. Auf 0 festgelegt, wenn es keine Leerzeichentrennung gibt.  
  
 `char p_sign_posn`  
 Die Position des positiven Vorzeichens in nicht negativen, formatierten monetären Mengen.  
  
 `char n_sign_posn`  
 Die Position des positiven Vorzeichens in negativen, formatierten monetären Mengen.  
  
Sofern angegeben, Mitglied der `lconv` -Struktur, die über `char *` und `wchar_t *` Versionen sind Zeiger auf Zeichenfolgen. Jeder von diesen, der gleich `""` (oder `L""` für `wchar_t *`) ist, hat entweder die Länge 0 oder wird nicht im aktuellen Gebietsschema unterstützt. Bitte beachten Sie, dass `decimal_point` und `_W_decimal_point` immer unterstützt werden, und dass deren Länge immer ungleich null ist.  
  
Die `char`-Member der Struktur sind kleine nicht negative Zahlen, keine Zeichen. Eines dieser, die gleich `CHAR_MAX` ist im aktuellen Gebietsschema nicht unterstützt.  
  
Die Werte der `grouping` und `mon_grouping` gemäß den folgenden Regeln interpretiert werden:  
  
- `CHAR_MAX`-Führen Sie nicht weiter gruppieren.  
  
- 0 – verwenden Sie vorangehenden Element für jede der verbleibenden Ziffern.  
  
- *n*-Anzahl der Ziffern, die aktuelle Gruppe bilden. Das nächste Element wird untersucht, um die Größe der nächsten Gruppe von Zeichen vor der aktuellen Gruppe zu bestimmen.  
  
Die Werte für `int_curr_symbol` gemäß den folgenden Regeln interpretiert werden:  
  
-   Die ersten drei Zeichen geben das alphabetische internationale Währungssymbol an, wie im Standard *ISO 4217 – Codes für die Darstellung der Währung und Fonds* definiert.  
  
-   Das vierte Zeichen (unmittelbar vorausgehendes Zeichen NULL) trennt das internationale Währungssymbol von der monetären Menge.  
  
Die Werte für `p_cs_precedes` und `n_cs_precedes` werden gemäß den folgenden Regeln interpretiert (die `n_cs_precedes` Regel wird in Klammern angegeben):  
  
- 0 – folgt Währungssymbol Wert für nicht negative (negativ) formatierte Währungswert an.  
  
- 1 - Währungssymbol vorangestellt Wert für nicht negative (negativ) formatierte Währungswert.  
  
Die Werte für `p_sep_by_space` und `n_sep_by_space` werden gemäß den folgenden Regeln interpretiert (die `n_sep_by_space` Regel wird in Klammern angegeben):  
  
- 0 - Währungssymbol vom Wert von Speicherplatz für nicht negative (negativ) formatierte Währungswert getrennt ist.  
  
- 1 – Es gibt keine Trennung Leerzeichen zwischen dem Währungssymbol und der Wert für nicht negative (negativ) formatierte Währungswert.  
  
Die Werte für `p_sign_posn` und `n_sign_posn` gemäß den folgenden Regeln interpretiert werden:  
  
- 0 – Klammern umgeben Menge und Currency Symbol.  
  
- 1 - Anmelde-Zeichenfolge ist die Menge und Currency Symbol vorangestellt.  
  
- 2 - Anmelde-Zeichenfolge folgt Menge und Currency Symbol.  
  
- 3 - Anmelde-Zeichenfolge ist sofort Währungssymbol vorangestellt.  
  
- 4 – Anmeldung Zeichenfolge unmittelbar folgt Währungssymbol.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`localeconv`|\<locale.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)