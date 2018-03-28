---
title: strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsftime
- strftime
- wcsftime
- _strftime_l
- _wcsftime_l
dev_langs:
- C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc71dc09b6634e01b1ba78621344dfb5c589c8d5
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

Formatieren einer Zeitzeichenfolge

## <a name="syntax"></a>Syntax

```
size_t strftime(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr
);
size_t _strftime_l(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr,
   _locale_t locale
);
size_t wcsftime(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr
);
size_t _wcsftime_l(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*strDest*<br/>
Ausgabezeichenfolge.

*maxsize*<br/>
Größe der *StrDest* Puffer, gemessen in Zeichen (**Char** oder **Wchar_t**).

*format*<br/>
Formatsteuerzeichenfolge.

*timeptr*<br/>
**TM** Datenstruktur.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

`strftime` Gibt die Anzahl der Zeichen platziert *StrDest* und `wcsftime` gibt die entsprechende Anzahl von Breitzeichen zurück.

Ist die Gesamtzahl der Zeichen, z. B. das abschließende Null-Zeichen, mehr als *Maxsize*, beide `strftime` und `wcsftime` zurückgeben, 0 und den Inhalt der *StrDest* sind unbestimmt.

Die Anzahl der Zeichen in *StrDest* ist gleich der Anzahl von Literalzeichen in *Format* sowie alle Zeichen, die hinzugefügt werden können *Format* über Formatierungscodes. Das abschließende NULL-Zeichen einer Zeichenfolge wird nicht im Rückgabewert berücksichtigt.

## <a name="remarks"></a>Hinweise

Die `strftime` und `wcsftime` Formatieren der **tm** Zeitwert in *Timeptr* gemäß den angegebenen *Format* Argument und Speichern des Ergebnisses in der Puffer *StrDest*. Darf höchstens *Maxsize* Zeichen in der Zeichenfolge eingefügt werden. Eine Beschreibung der Felder in der *Timeptr* -Struktur, finden Sie unter [Asctime](../../c-runtime-library/reference/asctime-wasctime.md). `wcsftime` ist die Breitzeichenentsprechung von `strftime`; ihr Zeichenfolgenargument zeigt auf eine Breitzeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

> [!NOTE]
>  In Versionen vor Visual C++ 2005 ist die Dokumentation beschrieben die *Format* Parameter `wcsftime` mit dem Datentyp `const wchar_t *`, aber die tatsächliche Implementierung von der *Format* Daten Typ `const char *`. Die Implementierung der *Format* -Datentyp wurde aktualisiert, um die vorherige und aktuelle-Dokumentation, d. h. widerspiegeln `const wchar_t *`.

Diese Funktion überprüft ihre Parameter. Wenn *StrDest*, *Format*, oder *Timeptr* ein null-Zeiger ist oder wenn die **tm** Datenstruktur adressiert werden, indem *Timeptr* ist ungültig (z. B., wenn er außerhalb des gültigen Bereichswerte enthält, für das Datum oder Uhrzeit), oder wenn die *Format* enthält eine ungültige Formatierungscode, Handler für ungültige Parameter aufgerufen, wie beschrieben in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktion 0 zurück und stellt **Errno** auf **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|

Die *Format* -Argument besteht aus mindestens Codes; da in `printf`, Formatierungscodes vorangestellt werden, wird ein Prozentzeichen (**%**). Zeichen, die nicht mit beginnen **%** beim Übertragungsvorgang kopiert werden unverändert an den `strDest`. Die **LC_TIME** Kategorie des aktuellen Gebietsschemas wirkt sich auf die Formatierung der Ausgabe von `strftime`. (Weitere Informationen zu **LC_TIME**, finden Sie unter [Setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).) Die `strftime` und `wcsftime` Funktionen verwenden, die aktuell festgelegten Gebietsschema. Die `_strftime_l` und `_wcsftime_l` Versionen dieser Funktionen sind nahezu identisch, außer dass sie das Gebietsschema als Parameter übernehmen und, anstatt die aktuell festgelegten verwenden Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Die `strftime` Funktionen unterstützen diese Formatierungscodes:

|||
|-|-|
|Code|Ersetzungszeichenfolge|
|`%a`|Abgekürzten Wochentagsnamen im Gebietsschema|
|`%A`|Vollen Wochentagsnamen im Gebietsschema|
|`%b`|Abgekürzten Monatsnamen im Gebietsschema|
|`%B`|Vollständigen Monatsnamen im Gebietsschema|
|`%c`|Für das Gebietsschema geeignete Darstellung von Datum und Uhrzeit|
|`%C`|Das Jahr durch 100 dividiert, und als Dezimalzahl (00−99) auf eine ganze Zahl gekürzt werden.|
|`%d`|Tag des Monats als Dezimalzahl (01-31)|
|`%D`|Entspricht `%m/%d/%y`.|
|`%e`|Tag des Monats wird als Dezimalzahl (1-31), in denen einzelne Ziffern durch ein Leerzeichen vorangestellt sind|
|`%F`|Entspricht `%Y-%m-%d`.|
|`%g`|Die letzten 2 Ziffern des ISO 8601 Woche basierende Jahres als Dezimalzahl (00 - 99)|
|`%G`|Das Jahr mit ISO 8601 Woche als Dezimalzahl|
|`%h`|Abgekürzte Name des Monats (Äquivalent zu `%b`)|
|`%H`|Stundenangabe im 24-Stunden-Format (00 - 23)|
|`%I`|Stundenangabe im 12-Stunden-Format (01 bis 12)|
|`%j`|Tag des Jahres als Dezimalzahl (001-366)|
|`%m`|Monatsangabe als Dezimalzahl (01 bis 12)|
|`%M`|Minutenangabe als Dezimalzahl (00 - 59)|
|`%n`|Ein neue Zeilenumbruchzeichen (**\n**)|
|`%p`|Das Gebietsschema A.M./P.M.-Kennung. Indikator für 12-Stunden-Uhr|
|`%r`|Zeit für das Gebietsschema-12-Stunden-Format|
|`%R`|Entspricht `%H:%M`.|
|`%S`|Sekundenangabe als Dezimalzahl (00 - 59)|
|`%t`|Ein horizontales Tabstoppzeichen (**\t**)|
|`%T`|Entspricht `%H:%M:%S`, das ISO 8601-Uhrzeit-Format|
|`%u`|ISO 8601-Wochentags als Dezimalzahl (1-7. Montag ist 1)|
|`%U`|Anzahl der Woche des Jahres als Dezimalzahl (00 - 53), wobei die erste Sonntag den ersten Tag der Woche 1|
|`%V`|Nummer der ISO 8601-Woche als Dezimalzahl (00 - 53)|
|`%w`|Angabe des Wochentags als Dezimalzahl (0 - 6; Sonntag ist 0)|
|`%W`|Anzahl der Woche des Jahres als Dezimalzahl (00 - 53), wobei die erste Montag den ersten Tag der Woche 1|
|`%x`|Darstellung von Datum für das Gebietsschema|
|`%X`|Time-Darstellung für das Gebietsschema|
|`%y`|Jahresangabe ohne Jahrhundert als Dezimalzahl (00 - 99)|
|`%Y`|Jahresangabe mit Jahrhundert als Dezimalzahl|
|`%z`|Der Offset von UTC in ISO 8601-Format; keine Zeichen, wenn Zeitzone unbekannt ist.|
|`%Z`|Des Gebietsschemas Zeitzonenname oder Abkürzung der Zeitzone, je nach registrierungseinstellungen; keine Zeichen, wenn Zeitzone unbekannt ist.|
|`%%`|Prozentzeichen (%)|

Wie in der `printf`-Funktion, wird das `#`-Flag möglicherweise dem Formatierungscode vorangestellt. In diesem Fall wird die Bedeutung des Formatcodes wie folgt geändert.

|Formatcode|Bedeutung|
|-----------------|-------------|
|`%#a`, `%#A`, `%#b`, `%#B`, `%#g`, `%#G`, `%#h`, `%#n`, `%#p`, `%#t`, `%#u`, `%#w`, `%#X`, `%#z`, `%#Z`, `%#%`|`#`-Flag wird ignoriert.|
|`%#c`|Langes Datum und Uhrzeit Darstellung, für das Gebietsschema geeignet. Beispiel: „Dienstag, 14. März 1995, 12:41:29“.|
|`%#x`|Langes Datum Darstellung, für das Gebietsschema geeignet. Beispiel: „Dienstag, 14. März 1995“.|
|`%#d`, `%#D`, `%#e`, `%#F`, `%#H`, `%#I`, `%#j`, `%#m`, `%#M`, `%#r`, `%#R`, `%#S`, `%#T`, `%#U`, `%#V`, `%#W`, `%#y`, `%#Y`|Entfernen Sie führende Nullen oder Leerzeichen (sofern vorhanden).|

Das ISO 8601-Woche und das Jahr basierende Woche von erzeugten `%V`, `%g`, und `%G`, verwendet eine Woche, die am Montag beginnt, auf dem Woche 1 Woche, die 4. Januar enthält, die erste Woche, die über mindestens 4 Tage des Jahres enthält. Ist der erste Montag des Jahres das 2., gehören 3. und 4., die vorherigen Tagen der letzten Woche des vorherigen Jahrs. Für diese Tage `%V` Fassung 53, und beide `%g` und `%G` werden durch die Ziffern des Vorjahres ersetzt.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|`strftime`|\<time.h>|
|`wcsftime`|\<time.h> oder \<wchar.h>|
|`_strftime_l`|\<time.h>|
|`_wcsftime_l`|\<time.h> oder \<wchar.h>|

Die `_strftime_l` und `_wcsftime_l` Funktionen sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [time](../../c-runtime-library/reference/time-time32-time64.md).

## <a name="see-also"></a>Siehe auch

[Locale](../../c-runtime-library/locale.md) <br/>
[Uhrzeitverwaltung](../../c-runtime-library/time-management.md) <br/>
[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](../../c-runtime-library/reference/localeconv.md) <br/>
[setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) <br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
