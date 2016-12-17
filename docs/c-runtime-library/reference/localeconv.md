---
title: "localeconv"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "localeconv"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "localeconv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "lconv-Typ"
  - "localeconv-Funktion"
  - "Gebietsschemas, Abrufen von Informationen zu"
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# localeconv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Informationen über Gebietsschema ab.  
  
## Syntax  
  
```  
  
struct lconv *localeconv( void );  
```  
  
## Rückgabewert  
 `localeconv` gibt einen Zeiger auf dem soliden Objekt des Typs [Struktur lconv](../../c-runtime-library/standard-types.md) zurück.  Die Werte, die im Objekt enthalten sind, können durch nachfolgende Aufrufe an `localeconv` überschrieben und nicht direkt ändern das Objekt.  Aufrufe von [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) mit `category`\-Werte von `LC_ALL`, `LC_MONETARY` oder `LC_NUMERIC` überschreiben den Inhalt der Struktur.  
  
## Hinweise  
 Die `localeconv`\-Funktion ruft ausführliche Informationen zur Formatierung für numerische das aktuelle Gebietsschema ab.  Diese Informationen werden in einer Struktur des Typs **lconv** gespeichert.  Die **lconv**\-Struktur, die in LOCALE.H, enthält die folgenden Member:  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 Dezimaltrennzeichenzeichen für nicht\-monetäre Mengen.  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 Zeichen, das Gruppen Ziffern links des Dezimaltrennzeichens für nicht\-monetäre Mengen trennt.  
  
 `char *grouping`  
 Größe der Gruppe Ziffern in den nicht\-monetären Mengen.  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 Internationales Währungssymbol für aktuelle Gebietsschema.  Erste drei Zeichen geben alphabetischem internationalem Währungssymbol an, wie in den *Code ISO 4217 für die Darstellung der Währung und der Kapitalien* definiert, die Standard sind.  Viertes Zeichen \(unmittelbar vor NULL\-Zeichen\) trennt internationales Währungssymbol vom Währungsbetrag.  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 Währungssymbol für aktuelle Gebietsschema.  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 Dezimaltrennzeichenzeichen für Währungsbeträge.  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 Trennzeichen für Zahlengruppen links Dezimalstelle der in den Währungsbeträgen.  
  
 `char *mon_grouping`  
 Größe der Gruppe Ziffern in den Währungsbeträgen.  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 Zeichenfolge, die Zeichen für nicht negative Währungsbeträge bezeichnet.  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 Zeichenfolge, die Zeichen für negative Währungsbeträge bezeichnet.  
  
 `char int_frac_digits`  
 Die Anzahl von Ziffern rechts des Dezimaltrennzeichens in für die internationale Programmierung formatierten Währungsbeträgen.  
  
 `char frac_digits`  
 Die Anzahl von Ziffern rechts des Dezimaltrennzeichens im formatierten Währungsbeträgen.  
  
 `char p_cs_precedes`  
 Wird auf 1 festgelegt, wenn Währungssymbol Wert für nicht negative Währungsbetrag formatierten vorausgeht.  Wird auf 0 festgelegt, wenn Symbol Wert folgt.  
  
 `char p_sep_by_space`  
 Wird auf 1 festgelegt, wenn Währungssymbol durch Leerzeichen vom Wert für nicht negative Währungsbetrag formatierten getrennt wird.  Wird auf 0 festgelegt, wenn keine Leerzeichentrennung gibt.  
  
 `char n_cs_precedes`  
 Wird auf 1 festgelegt, wenn Währungssymbol für formatierten Wert negativ Währungsbetrag vorausgeht.  Wird auf 0 festgelegt, wenn Symbol Wert folgt.  
  
 `char n_sep_by_space`  
 Wird auf 1 festgelegt, wenn Währungssymbol durch Leerzeichen vom Wert negativ für formatierten Währungsbetrag getrennt wird.  Wird auf 0 festgelegt, wenn keine Leerzeichentrennung gibt.  
  
 `char p_sign_posn`  
 Position des Vorzeichens positiven in nicht negative formatierten Währungsbeträgen.  
  
 `char n_sign_posn`  
 Position des Vorzeichens positiven in den formatierten Währungsbeträgen negativ.  
  
 Member der Struktur, der `char` `*` und `wchar_t *`\-Versionen besitzen, sind Zeiger auf Zeichenfolgen.  Irgendwelches dieses gleich `""` \(oder `L""` für `wchar_t *`\) ist entweder von der Länge 0 oder unterstützt nicht im aktuellen Gebietsschema.  Beachten Sie, dass `decimal_point` und `_W_decimal_point` immer und Länge der ungleich 0 \(null\) unterstützt werden.  
  
 Die Member `char` der Struktur sind kleine nicht negative Zahlen, keine Zeichen.  Irgendwelches dieses gleich **CHAR\_MAX** wird nicht in das aktuelle Gebietsschema unterstützt.  
  
 Die Elemente aus **grouping** und **mon\_grouping** werden entsprechend den folgenden Regeln interpretiert.  
  
 **CHAR\_MAX**  
 Führen Sie keine weitere Gruppieren aus.  
  
 0  
 Verwenden Sie wenn für jede der verbleibenden Ziffern.  
  
 *n*  
 Zahl Ziffern, die aktuelle Gruppe besteht.  Folgendes Element wird überprüft, um Größe der folgenden Gruppe Ziffern zu bestimmen, bevor aktuell, gruppieren.  
  
 Die Werte für **int\_curr\_symbol** werden entsprechend den folgenden Regeln interpretiert:  
  
-   Die ersten drei Zeichen geben den internationalen alphabetischen Währungssymbol an, wie in den *Code ISO 4217 für die Darstellung der Währung und der Kapitalien* definiert, die Standard sind.  
  
-   Das vierte Zeichen \(direkt vor das Nullzeichen\) trennt das internationale Währungssymbol vom Währungsbetrag.  
  
 Die Werte für **p\_cs\_precedes** und **n\_cs\_precedes** werden entsprechend den folgenden Regeln interpretiert \(die **n\_cs\_precedes** Regel ist in Klammern\):  
  
 0  
 Währungssymbol folgt Wert für nicht negative \(negative\) formatierten Währungswert.  
  
 1  
 Währungssymbol geht Wert für nicht negative \(negative\) formatierten Währungswert voran.  
  
 Die Werte für **p\_sep\_by\_space** und **n\_sep\_by\_space** werden entsprechend den folgenden Regeln interpretiert \(die **n\_sep\_by\_space** Regel ist in Klammern\):  
  
 0  
 Währungssymbol wird vom Wert von Speicher für nicht negative \(negative\) formatierten Währungswert getrennt.  
  
 1  
 Es gibt keine Leerzeichentrennung zwischen Währungssymbol und Wert für nicht negative \(negative\) formatierten Währungswert.  
  
 Die Werte für **p\_sign\_posn** und **n\_sign\_posn** werden entsprechend den folgenden Regeln interpretiert:  
  
 0  
 Klammereinfassungsmenge und \-Währungssymbol.  
  
 1  
 Zeichenzeichenfolge geht Menge und Währungssymbol voran.  
  
 2  
 Zeichenzeichenfolge folgt Menge und Währungssymbol.  
  
 3  
 Zeichenzeichenfolge wechselt sofort Währungssymbol voran.  
  
 4  
 Zeichenzeichenfolge folgt direkt Währungssymbol.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`localeconv`|\<locale.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Siehe auch  
 [Locale](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)